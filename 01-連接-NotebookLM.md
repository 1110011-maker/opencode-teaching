---
title: 'OpenCode 懶人包 #01：連接 NotebookLM'
date: '2026-06-10'
type: 懶人包
version: v0.5
status: 強化版
tags:
  - OpenCode
  - 懶人包
  - NotebookLM
  - MCP
---
# OpenCode 懶人包 #01：連接 Google NotebookLM

> 版本：v0.5
> 更新日期：2026-06-10

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

> 🔁 **重複執行安全檢查**：如果所有環境條件都符合，此步驟直接跳過。

請 OpenCode 在開始安裝前，先自動確認以下所有項目。
如果有任何一項不符合，請先告知使用者問題所在，並引導解決後再繼續。
**不要跳過任何一項檢查，不要假設環境正常。**

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

> 🔁 **重複執行安全檢查**：如果目標資料夾結構已存在，此步驟直接跳過。

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

連接成功後，你隨時可以在 OpenCode 裡用自然語言操控 NotebookLM。以下是 20 個實際使用範例：

### 📥 類別一：內容來源（5 個範例）

| # | 你說的話 | NotebookLM 會做的事 | 適用時機 |
|---|---------|-------------------|---------|
| 1 | 「幫我用這份 PDF 建一個 notebook」 | 建立 notebook + 上傳 PDF 作為資料來源 | 拿到教材 PDF 時 |
| 2 | 「幫我把這個 YouTube 影片加到 notebook」 | 新增 YouTube URL 來源，自動轉錄 | 教學影片分析 |
| 3 | 「幫我把這個網頁內容加入 notebook」 | 新增網頁 URL 來源，自動抓取內容 | 參考文章整理 |
| 4 | 「幫我把這段文字貼進 notebook」 | 以文字 source 加入 notebook | 手動複製的內容 |
| 5 | 「幫我把 Google Doc 加入 notebook」 | 以 Drive 文件加入 notebook | 團隊共筆文件分析 |

### 🎨 類別二：產出類型（5 個範例）

| # | 你說的話 | NotebookLM 會做的事 | 存放位置 |
|---|---------|-------------------|---------|
| 6 | 「幫我產生教學簡報」 | 生成 Slide Deck（可匯出 .pptx） | slides/ |
| 7 | 「幫我做一張資訊圖表」 | 生成 Infographic（手繪/專業/教材風） | infographics/ |
| 8 | 「幫我產出 Podcast 音檔」 | 生成 Audio Overview | audio/ |
| 9 | 「幫我產出報告並匯出 Google 文件」 | 生成 Briefing Doc，自動匯出 Google Docs | docs/ |
| 10 | 「幫我出 10 題測驗卷」 | 生成 Quiz / Flashcards | quizzes/ |

### 📚 類別三：跨筆記本操作（5 個範例）

| # | 你說的話 | 運作方式 | 適用時機 |
|---|---------|---------|---------|
| 11 | 「幫我查詢上週那本筆記本的內容」 | 跨 notebook 查詢，列出所有筆記本 | 需要回顧舊資料 |
| 12 | 「幫我把這三份資料合併到同一本 notebook」 | 將多個 source 加入同一 notebook | 主題資料彙整 |
| 13 | 「幫我幫筆記本加上標籤分類」 | 使用 label 工具分類 sources | 大量資料管理 |
| 14 | 「幫我一次產出全部五種成品」 | 批次產出簡報+圖表+Podcast+報告+影片 | 完整素材產出 |
| 15 | 「幫我比較這兩本 notebook 的內容差異」 | 交叉查詢兩本 notebook 並統整結果 | 版本比較或對照 |

### 🔗 類別四：進階整合（5 個範例）

| # | 你說的話 | 流程說明 | 適用時機 |
|---|---------|---------|---------|
| 16 | 「幫我把 FB 摘要存到 NotebookLM 再產出簡報」 | 先用 FB 摘要 Skill → 自動餵入 NotebookLM → 產出簡報 | #08 FB 摘要進階用法 |
| 17 | 「把這本書轉成技能後，再用 NotebookLM 加強分析」 | Book-to-Skill 萃取 → 書本內容餵入 NotebookLM 分析 | #05 Book-to-Skill 混搭 |
| 18 | 「幫我把 NotebookLM 的摘要存進 Obsidian」 | NotebookLM 產出 → 用 Obsidian 工具寫入 vault | #03/#04 第二大腦整合 |
| 19 | 「設定每天早上自動摘要我的筆記本」 | 結合 startup/shutdown → 排程批次產出 | 習慣自動化 |
| 20 | 「幫我開共享筆記本讓團隊協作」 | 建立 notebook → 邀請協作者加入 | 團隊協同研究 |

這 20 個範例涵蓋了從單一操作到跨工具整合的所有使用場景。隨著你對 NotebookLM 越來越熟悉，還可以將 NotebookLM 與 Obsidian、GitHub、FB 摘要等其他懶人包自由組合。

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
| Studio 產出很慢或逾時 | NotebookLM 生成需要時間，可提供連結讓使用者自行查看 |
| 一個 notebook 能加多少 source？ | 每本 notebook 最多 50 個 source，每個 source 最多 50 萬字 |
| 可以產出英文以外的內容嗎？ | 可以。在產出時指定 `language="zh-TW"` 或其他語言參數 |
| 下載的檔案放在哪裡？ | 預設在 `Documents/NotebookLM/` 下對應子資料夾 |
| 如何刪除 notebook？ | 對 OpenCode 說：「幫我刪除測試筆記本」 |
| 登錯 Google 帳號怎麼辦？ | 執行 `nlm logout` 清除登入狀態，再重新 `nlm login` |

---

## 更新紀錄

| 日期 | 版本 | 更新內容 |
|------|------|---------|
| 2026-04-04 | v0.1 | 初版，根據官方文件建立基本流程 |
| 2026-04-04 | v0.2 | 加入環境檢查、復原機制、跨平台支援、常見問題擴充 |
| 2026-06-06 | v0.3 | 全面更新 Claude Code → OpenCode |
| 2026-06-10 | v0.5 | 深度擴充：20 個使用範例（4 類）、🔁 重複執行檢查（步驟零、四）、FAQ 6→12 題 |

---

## 相關連結

- [notebooklm-mcp-cli GitHub](https://github.com/jacob-bd/notebooklm-mcp-cli)
- [NotebookLM Downloader MCP](https://lobehub.com/mcp/pmane-notebooklm-downloader)
- [📋 OpenCode 懶人包索引](./README.md)
