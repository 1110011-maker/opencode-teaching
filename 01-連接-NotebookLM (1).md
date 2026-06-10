---
title: 'OpenCode 懶人包 #01：連接 NotebookLM'
date: '2026-04-04'
type: 懶人包
version: v0.3
status: 初版（實作後更新）
tags:
  - OpenCode
  - 懶人包
  - NotebookLM
  - MCP
---
# OpenCode 懶人包 #01：連接 Google NotebookLM

> 版本：v0.3
> 更新日期：2026-06-06

> 📌 **本懶人包可獨立執行**：會自動檢查並安裝所需工具，不需要先看過其他懶人包。你只要確認下方「先備條件」即可開始。

---

## 這個懶人包會幫你做什麼？

讓你的 OpenCode 桌面版能夠直接操控 Google NotebookLM，包括：
- 建立 notebook、上傳資料來源
- 產生教學簡報（Slide Deck）
- 產生資訊圖表（Infographic）
- 所有成品自動下載到電腦裡的指定資料夾

---

## 原理說明：這個懶人包在做什麼？

**三角關係圖**：

```
OpenCode ←(MCP 協定)→ nlm (翻譯官) ←(Google 登入)→ NotebookLM
```

這個懶人包會在你的電腦裡裝一個叫 `nlm` 的「翻譯官」，讓 OpenCode 能透過它去操控 NotebookLM。

- **為什麼需要翻譯官？**
  NotebookLM 沒有官方 API，Google 沒開放程式直接呼叫。`nlm` 是用「模擬瀏覽器操作」的方式，假裝是你在點網頁。

- **什麼是 MCP？**
  MCP（Model Context Protocol）是 OpenCode 跟外部工具溝通的標準接口，就像手機的 USB-C——只要工具支援 MCP，OpenCode 就能插上去用。

- **為什麼要登入 Google？**
  `nlm` 需要你的 Google 通行證，才能幫你去操作 NotebookLM。

**一句話記住**：你跟 OpenCode 講中文，OpenCode 叫 `nlm` 去幫你點 NotebookLM 的網頁，成品自動下載到你電腦的資料夾。

---

## 先備條件

在使用這個懶人包之前，請確認：

- [ ] OpenCode 桌面版已安裝且能正常使用
- [ ] 你有 Google 帳號（用來登入 NotebookLM）
- [ ] 電腦有網路連線

---

## 請 OpenCode 幫我執行以下步驟

> ⚠️ 以下內容是給 OpenCode 讀的操作指令。
> 你只需要把這整份 MD 檔丟給 OpenCode 桌面版的 Code 分頁，它會自動開始執行。
> 遇到需要你手動操作的地方，它會暫停並告訴你該怎麼做。
>
> **所有安裝與設定都在 OpenCode 桌面版內完成，不需要另外打開 PowerShell 或命令提示字元。**
> 如果 OpenCode 桌面版無法執行某個指令，才會引導你到終端機操作。
> 進階使用者也可以直接使用 OpenCode CLI 版本來執行本懶人包。

---

### 步驟零：環境檢查

> 請 OpenCode 在開始安裝前，先自動確認以下所有項目。
> 如果有任何一項不符合，請先告知使用者問題所在，並引導解決後再繼續。
> **不要跳過任何一項檢查，不要假設環境正常。**

1. **確認作業系統**：執行系統指令確認是 Windows / macOS / Linux，後續所有指令請根據實際的作業系統選擇正確版本執行
2. **確認 uv 已安裝**：執行 `uv --version`，如果未安裝，步驟一會自動安裝
3. **確認網路連線正常**：嘗試 ping 一個外部網站
4. **確認 OpenCode 的版本**：執行 `opencode --version`，確認版本為 v1.0.0 以上；如果版本過舊，請引導使用者重新安裝

> 全部通過後，告知使用者：「環境檢查完成，所有條件都符合，開始安裝。」
> 如果有不通過的項目，列出問題清單並逐一引導解決。

---

### 步驟一：安裝 NotebookLM MCP CLI 工具

如果步驟零確認 `uv` 尚未安裝，請先安裝：

**Windows（PowerShell）**：
```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**macOS / Linux**：
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

安裝完 uv 後（或已有 uv），安裝 NotebookLM MCP CLI：

> 🔁 **重複執行檢查**：請先執行 `uv tool list` 檢查 `notebooklm-mcp-cli` 是否已安裝。
> - 如果**已安裝** → 跳過安裝步驟，直接執行後續確認
> - 如果**未安裝** → 繼續執行以下指令

```bash
uv tool install notebooklm-mcp-cli
```

安裝完成後（或已存在時），確認指令可用：

```bash
nlm --version
```

> 如果出現 `nlm: command not found`，請重開終端機再試一次。
> 如果仍然失敗，請告知使用者可能需要手動將 uv 的路徑加入系統 PATH。

---

### 步驟二：登入 Google 帳號

> 🔁 **重複執行檢查**：請先執行 `nlm doctor` 確認是否已登入認證。
> - 如果顯示 `authenticated` 或類似已認證訊息 → 跳過此步驟，告知使用者「Google 帳號已登入」
> - 如果顯示未認證 → 繼續執行以下步驟

請執行以下指令，會自動開啟瀏覽器讓使用者登入 Google：

```bash
nlm login
```

> 🖐️ **需要手動操作**：瀏覽器會開啟 Google 登入頁面，請使用者登入他的 Google 帳號。登入成功後，CLI 會自動擷取認證資訊。

登入成功後，確認狀態：

```bash
nlm doctor
```

> 如果 `nlm doctor` 顯示未認證，請重新執行 `nlm login`。
> 如果瀏覽器沒有自動開啟，請手動開啟瀏覽器到 Google 登入頁面，登入後再回到終端機。

---

### 步驟三：設定 OpenCode 的 MCP 連接

> 🔁 **重複執行檢查**：請先執行 `nlm setup list` 確認 `opencode` 是否已在清單中。
> - 如果**已在清單中** → 跳過此步驟，告知使用者「MCP 連接已設定」
> - 如果**不在清單中** → 繼續執行以下步驟

請執行以下指令，自動完成 MCP 設定（不需要手動編輯 JSON）：

```bash
nlm setup add opencode
```

確認設定成功：

```bash
nlm setup list
```

> 應該能看到 `opencode` 出現在已設定的客戶端清單中。

---

### 步驟四：建立本地資料夾

請根據使用者的作業系統，在文件資料夾下建立以下目錄結構：

```
Documents/
  └── NotebookLM/
      ├── slides/          ← 簡報（Slide Deck，可匯出 .pptx）
      ├── infographics/    ← 資訊圖表（多種風格可選）
      ├── audio/           ← 音訊概覽（Audio Overview）
      ├── video/           ← 影片概覽（Video Overview，含 Cinematic / Explainer / Brief）
      ├── docs/            ← Google 文件匯出（Reports、Notes 等）
      ├── sheets/          ← Google 試算表匯出（Data Tables）
      ├── mindmaps/        ← 心智圖（Mind Map）
      └── quizzes/         ← 測驗與閃卡（Quiz、Flashcards）
```

建立完成後，告知使用者資料夾的完整路徑。

---

### 步驟五：重啟 OpenCode 並驗證連接

> 🖐️ **需要手動操作**：請使用者完全關閉 OpenCode 桌面版，然後重新開啟。

重新開啟後，測試 NotebookLM 連接是否成功：
1. 列出 OpenCode 目前所有可用的 MCP 工具（`tools/list`），找到 NotebookLM 相關的 list/read 工具
2. 使用該工具列出使用者的 NotebookLM 筆記本清單
3. 如果成功顯示清單（即使是空的），代表連接成功

---

### 步驟六：功能測試

連接成功後，請執行一個簡單的測試：
1. 使用 NotebookLM MCP 的 create notebook 工具，建立一個名稱為「測試筆記本」的新 notebook
2. 確認建立成功（應回傳 notebook ID）
3. 建立成功後，使用 delete notebook 工具刪除這個測試筆記本
4. 告知使用者：「✅ 全部完成！你的 OpenCode 已成功連接 NotebookLM。」

---

## 完成！接下來你可以這樣用

連接成功後，你隨時可以在 OpenCode 裡用自然語言操控 NotebookLM：

| 你說的話 | NotebookLM 會做的事 | 存放位置 |
|----------|-------------------|---------|
| 「幫我用這份 PDF 建一個 notebook」 | 建立 notebook + 上傳 PDF 作為資料來源 | — |
| 「幫我產生教學簡報」 | 生成 Slide Deck（可匯出 .pptx） | slides/ |
| 「幫我做一張資訊圖表」 | 生成 Infographic（多種風格可選） | infographics/ |
| 「幫我產生音訊概覽（Podcast）」 | 生成 Audio Overview | audio/ |
| 「幫我產生影片概覽」 | 生成 Video Overview（Cinematic / Explainer / Brief） | video/ |
| 「幫我產生報告並匯出成文件」 | 生成 Report，匯出為 Google Docs | docs/ |
| 「幫我做數據表格並匯出試算表」 | 生成 Data Table，匯出為 Google Sheets | sheets/ |
| 「幫我產生心智圖」 | 生成 Mind Map | mindmaps/ |
| 「幫我出測驗題 / 閃卡」 | 生成 Quiz / Flashcards | quizzes/ |

---

## 如果安裝失敗，如何重來

> 如果執行過程中遇到錯誤，不用緊張。
> 對 OpenCode 說以下這段話，它會幫你清除之前的設定，從頭再來：

**請對 OpenCode 說：**
「上次 NotebookLM 懶人包執行失敗了，幫我清除之前的設定，重新跑一次。」

**OpenCode 會自動執行以下復原步驟：**

1. 移除 MCP 設定：`nlm setup remove opencode`
2. 移除 notebooklm-mcp-cli：`uv tool uninstall notebooklm-mcp-cli`
3. 清除登入狀態：`nlm logout`
4. 確認環境乾淨後，從步驟零重新開始

---

## 常見問題

| 問題 | 解法 |
|------|------|
| `nlm: command not found` | 重開終端機，或確認 uv 安裝路徑已加入 PATH |
| `uv: command not found` | Windows 需重開 PowerShell；macOS/Linux 需執行 `source ~/.bashrc` 或 `source ~/.zshrc` |
| 登入後 `nlm doctor` 顯示未認證 | 重新執行 `nlm login`，確認瀏覽器登入成功 |
| 瀏覽器沒有自動開啟 | 手動開啟瀏覽器登入 Google，或嘗試 `nlm login --manual` |
| OpenCode 看不到 NotebookLM 工具 | 確認有執行 `nlm setup add opencode`，並完全關閉再重啟 OpenCode |
| Windows 上指令格式錯誤 | 確認使用 PowerShell 而非 CMD，或改用 Git Bash |
| （實作後持續補充） | |

---

## 更新紀錄

| 日期 | 版本 | 更新內容 |
|------|------|---------|
| 2026-04-04 | v0.1 | 初版，根據官方文件建立基本流程 |
| 2026-04-04 | v0.2 | 加入環境檢查、復原機制、跨平台支援、常見問題擴充 |
| 2026-06-06 | v0.3 | 全面更新 Claude Code → OpenCode |
| — | v1.0（預定） | 待經多人實測後發布穩定版本 |

---

## 相關連結

- [notebooklm-mcp-cli GitHub](https://github.com/jacob-bd/notebooklm-mcp-cli)
- [NotebookLM Downloader MCP](https://lobehub.com/mcp/pmane-notebooklm-downloader)
- [📋 OpenCode 懶人包索引](./README.md)
