---
title: 'OpenCode 懶人包 #08：FB 頻道摘要自動化 Skill'
date: '2026-06-09'
type: 懶人包
version: v0.5
status: 強化版
tags:
  - OpenCode
  - 懶人包
  - FB
  - NotebookLM
  - Skill
  - 頻道摘要
---

# OpenCode 懶人包 #08：FB 頻道摘要自動化 Skill

> 版本：v0.5
> 更新日期：2026-06-10
> 先備條件：已完成懶人包 #01（NotebookLM MCP 已連接）或 nlm 已安裝

> 📌 **本懶人包可獨立執行**：只要 OpenCode 和 NotebookLM MCP 已就緒就可以開始。完成後你對 OpenCode 說「FB 摘要」，即可互動式批次產出報告、簡報、資訊圖表與無障礙網頁。

---

## 這個懶人包會幫你做什麼？

在你的 OpenCode 中安裝一個**互動式 Skill**，讓你能將 FB 粉專內容自動餵入 NotebookLM，批次產出：

| 產出項目 | 格式 | 說明 |
|---------|------|------|
| 📓 更新摘要記事 | NotebookLM Note | AI 整理條列式摘要 |
| 📄 報告 + Google 文件 | Briefing Doc → Google Doc | 分析報告並匯出 |
| 📊 簡報 | Slide Deck → PDF | 詳細或精簡版 |
| 🖼️ 資訊圖表 | PNG（16:9） | 手繪 / 專業 / 教材風格 |
| 🌐 無障礙網頁 | WCAG 2.2 AAA HTML | 新聞稿形式，可貼入 XOOPS CKEditor |

---

## 先備條件

在使用這個懶人包之前，請確認：

- [ ] OpenCode 桌面版或 CLI 版已安裝
- [ ] NotebookLM MCP 已連接（參考 #01）
- [ ] `nlm login` 認證有效（執行 `nlm doctor` 確認）

---

## 請 OpenCode 幫我執行以下步驟

> ⚠️ 以下內容是給 OpenCode 讀的操作指令。
> 如果無法自動執行，請手動依照步驟操作。

---

### 步驟一：確認認證

> 🔁 **重複執行安全檢查**：如果已經完成認證且有效，此步驟會被跳過。

開始之前，先確認 NotebookLM 可以正常使用：

```bash
nlm doctor
```

> 應該顯示 `Authentication valid!` 以及 Notebooks found 數量。
> 如果顯示未認證，請執行 `nlm login` 重新登入。
> 如果 `nlm doctor` 指令不存在，表示尚未安裝，請先參考 #01 安裝 NotebookLM MCP。

---

### 步驟二：安裝 Skill 檔案

> 🔁 **重複執行安全檢查**：如果目標位置已有 `SKILL.md`，會詢問是保留、更新或跳過。

OpenCode 請依以下順序處理：

0. 🔁 **檢查是否已安裝**：檢查 `$env:USERPROFILE\.config\opencode\skills\fb-notebooklm\SKILL.md` 是否存在
   - **若不存在** → 繼續安裝
   - **若已存在** → 比較內容差異，詢問使用者：
     - (a) 保留現有檔案，跳過安裝
     - (b) 備份現有檔案後覆寫
     - (c) 直接覆寫

1. **檢查**目前工作目錄是否有 `fb-notebooklm-SKILL.md`（或 `fb-notebooklm-skill.md`）檔案
2. **若有**該檔案 → 直接讀取內容，建立到目標位置
3. **若無**該檔案 → 直接讀取本頁下方「附錄一」的程式碼區塊內容，作為 SKILL.md 的內容

無論哪種來源，最終執行安裝：

```bash
# 建立技能資料夾
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.config\opencode\skills\fb-notebooklm"

# 寫入 SKILL.md
Set-Content -Path "$env:USERPROFILE\.config\opencode\skills\fb-notebooklm\SKILL.md" -Value "<SKILL.md 內容>"
```

> 如果無法自動執行，請手動從「附錄一」複製完整內容，貼入 `$env:USERPROFILE\.config\opencode\skills\fb-notebooklm\SKILL.md`。

---

### 步驟三：重啟 OpenCode

> 🖐️ **需要手動操作**：請完全關閉 OpenCode，然後重新開啟。

重啟後，OpenCode 會自動掃描技能清單，你可以在可用技能中看到 `fb-notebooklm`。

---

### 步驟四：測試 Skill

對 OpenCode 說：

> 「FB 摘要」

OpenCode 會引導你依序選擇：
1. FB 內容來源（手動貼上 / 提供網址 / 從檔案讀取）
2. NotebookLM 筆記本（現有 / 新建）
3. 要產出的項目（可複選）
4. 風格偏好（簡報長度、圖表風格）
5. 自動批次產出

---

## 完成！接下來你可以這樣用

安裝完成後，對 OpenCode 說「FB 摘要」即可開始。以下是 20 個實際使用範例，分成四大類：

> 💡 **每個範例都是一句對 OpenCode 說的話**，FB 摘要 Skill 會自動引導你完成後續選擇。

### 🎯 類別一：不同來源類型（5 個範例）

| # | 你說的話 | 運作方式 | 適用時機 |
|---|---------|---------|---------|
| 1 | 「幫我摘要這篇 FB 貼文：\[貼上內容\]」 | 手動貼上 → 自動分析 → 產出摘要記事 | 看到一篇想整理的貼文時 |
| 2 | 「幫我去抓這個粉專的最新貼文 https://facebook.com/...」 | 自動抓取 → 餵入 NotebookLM → 批次產出 | 粉專有公開內容時 |
| 3 | 「從我桌面的 `fb-posts.md` 讀取這週的貼文來做摘要」 | 讀取 Markdown 檔案 → 加入 NotebookLM | 已預先收集多篇貼文 |
| 4 | 「讀取 `D:\raw\notes.txt` 裡的 FB 內容做摘要」 | 讀取純文字檔 → 加入 NotebookLM | 內容在純文字紀錄中 |
| 5 | 「我有三篇貼文要整理，兩篇手動貼上，一篇從網址抓」 | 分次提供 → 合併至同一筆記本 | 混合來源的靈活場景 |

### ⚙️ 類別二：不同產出組合（5 個範例）

| # | 你說的話 | 產出項目 | 適用時機 |
|---|---------|---------|---------|
| 6 | 「幫我條列式整理這篇貼文的重點就好」 | 📓 僅摘要記事 | 快速了解，不需完整報告 |
| 7 | 「幫我整理這篇 FB，要摘要 + 報告 + 簡報」 | 📓📄📊 三項 | 標準產出組合，一次到位 |
| 8 | 「這篇粉專內容幫我一次產出全部五項」 | 📓📄📊🖼️🌐 五項全開 | 需要完整素材庫時 |
| 9 | 「只要幫我做成資訊圖表和無障礙網頁」 | 🖼️🌐 兩項 | 視覺化 + 發布用 HTML |
| 10 | 「幫我產出報告並匯出到 Google Docs」 | 📄 報告 → Google Docs | 需要分享給團隊協作 |

### 🎨 類別三：不同風格設定（5 個範例）

| # | 你說的話 | 設定組合 | 適用時機 |
|---|---------|---------|---------|
| 11 | 「幫我做一張手繪風格的資訊圖表」 | 資訊圖表：手繪風 | 社群媒體發布，活潑生動 |
| 12 | 「幫我產出專業風的資訊圖表 + 精簡版簡報」 | 資訊圖表：專業風；簡報：精簡 | 正式會議或對外報告 |
| 13 | 「幫我做教材風格的資訊圖表 + 詳細簡報」 | 資訊圖表：教材風；簡報：詳細 | 教學場景或課堂教材 |
| 14 | 「幫我產出詳細版簡報（含 speaker notes）」 | 簡報：詳細版（detailed_deck） | 需要完整逐頁說明 |
| 15 | 「幫我產出精簡版簡報，5 頁就好」 | 簡報：精簡版（presenter_slides） | 快速簡報或摘要分享 |

### 🚀 類別四：進階場景（5 個範例）

| # | 你說的話 | 流程說明 | 適用時機 |
|---|---------|---------|---------|
| 16 | 「我每週都要追蹤這個粉專，幫我開固定筆記本」 | 建立專屬筆記本 → 每次產出累積在同一本 | 長期追蹤特定粉專 |
| 17 | 「幫我比較 A 粉專和 B 粉專這週的摘要」 | 兩本筆記本交叉查詢 → 統整對照表 | 競品分析或市場研究 |
| 18 | 「幫我把這篇 FB 摘要同時存進 Obsidian 第二大腦」 | 產出摘要後用 Obsidian 工具寫入 vault | 知識庫建檔與回顧 |
| 19 | 「把這篇 FB 摘要做成教材」 | 產出報告 → 用 book-to-skill 轉成可重複使用的技能 | 將時事轉為教學素材 |
| 20 | 「設定每週一自動跑 FB 摘要」 | 結合 startup/shutdown 觸發 → 排程批次產出 | 習慣自動化，減少手動作業 |

這 20 個範例涵蓋了從入門到進階的所有使用場景。隨著你對 FB 摘要 Skill 越來越熟悉，還可以自由組合不同的來源、產出和風格設定。

---

## 附錄一：SKILL.md 完整內容

如果無法自動下載，請手動建立 `$env:USERPROFILE\.config\opencode\skills\fb-notebooklm\SKILL.md`，內容如下：

```markdown
---
name: fb-notebooklm
description: FB 頻道更新摘要 — 說「FB 摘要」「頻道更新」「粉專摘要」時載入
---

當使用者說「FB 摘要」「頻道更新」「粉專摘要」或類似意思時，依序執行以下步驟。

## 步驟一：詢問 FB 內容來源

使用 `question` 工具詢問使用者：

```
FB 內容要怎麼提供？
(1) 手動貼上貼文內容
(2) 提供粉專網址（嘗試自動抓取）
(3) 從 .md / .txt 檔案讀取
```

依使用者選擇處理：
- **(1) 手動貼上** → 請使用者直接貼上貼文內容（含發文日期），收到後繼續
- **(2) 粉專網址** → 先嘗試 `webfetch` 抓取公開內容；失敗則告知使用者手動貼上
- **(3) 從檔案讀取** → 用 `read` 工具讀取使用者指定的檔案路徑

## 步驟二：詢問 NotebookLM 筆記本

使用 `question` 工具詢問：

```
要用哪本筆記本？
(1) 選擇現有筆記本
(2) 新建一本
```

- **(1) 現有** → 先呼叫 `notebooklm_notebook_list` 列出所有筆記本，讓使用者從中選擇
- **(2) 新建** → 使用 `notebooklm_notebook_create` 建立新筆記本，預設名稱為「FB頻道摘要」

## 步驟三：將內容加入 NotebookLM

使用 `notebooklm_source_add` 將 FB 內容以 `source_type=text` 加入選定的筆記本，設定 `wait=true`。

## 步驟四：詢問要產出哪些內容

使用 `question` 工具，設定 `multiple=true`，讓使用者複選：

```
要產出哪些內容？
☐ 📓 更新摘要記事（存成 NotebookLM Note）
☐ 📄 報告 + 匯出 Google 文件（Briefing Doc → Google Docs）
☐ 📊 簡報（Slide Deck）
☐ 🖼️ 資訊圖表（16:9 繁體中文）
☐ 🌐 無障礙網頁（WCAG 2.2 AAA 合規 HTML）
```

### 步驟四之一：風格偏好（根據勾選項目詢問）

使用 `question` 工具詢問：

- 如果有勾選**簡報** → 簡報長度：`詳細` / `精簡`
- 如果有勾選**資訊圖表** → 圖表風格：`手繪風` / `專業風` / `教材風`
- 如果有勾選**無障礙網頁** → 內容來源使用 NotebookLM 報告內容

## 步驟五：執行批次產出

依序執行勾選的項目，每項完成後記錄結果再進行下一項。

### 5-1：更新摘要記事

1. 使用 `notebooklm_notebook_query` 查詢 AI 整理摘要
   - query: "請用繁體中文條列式整理這篇 FB 貼文的摘要，包含發文日期、活動名稱、參與對象、活動流程、學習目標、重點特色"
2. 使用 `notebooklm_note` 將摘要結果存成記事
   - title: "FB 頻道更新摘要 (YYYY-MM-DD)"

### 5-2：報告 + Google 文件

1. 使用 `notebooklm_studio_create` 產生報告，`report_format="Briefing Doc"`, `language="zh-TW"`
2. 輪詢 `notebooklm_studio_status` 直到狀態為 `completed`
3. 使用 `notebooklm_export_artifact` 匯出到 Google Docs
4. 可選：用 `notebooklm_download_artifact` 下載 Markdown 備份到本機

### 5-3：簡報

1. 使用 `notebooklm_studio_create` 產生簡報，`artifact_type="slide_deck"`
   - 依風格選擇設定 `slide_format`：詳細用 `detailed_deck`，精簡用 `presenter_slides`
   - `language="zh-TW"`
2. 輪詢 `notebooklm_studio_status` 直到 `completed`
3. 用 `notebooklm_download_artifact` 下載 PDF

### 5-4：資訊圖表

1. 使用 `notebooklm_studio_create` 產生資訊圖表，`artifact_type="infographic"`
   - `orientation="landscape"`, `language="zh-TW"`
   - 依風格選擇設定 `visual_style`：手繪風=`sketch_note`，專業風=`professional`，教材風=`instructional`
   - `detail_level="concise"`
2. 輪詢 `notebooklm_studio_status` 直到 `completed`
3. 用 `notebooklm_download_artifact` 下載 PNG

### 5-5：無障礙網頁（新聞稿形式 × WCAG 2.2 AAA）

1. 確保 5-2 的報告已產生完成且已下載 Markdown
2. 讀取下載的報告 Markdown 內容
3. 使用以下 Prompt 將報告內容改寫為新聞稿，再轉為 WCAG 2.2 AAA 合規 HTML：

   > **你必須同時扮演兩個角色，嚴格依序執行：**
   >
   > **第一角色：資深新聞記者**
   >
   > 將以下內容改寫為一篇中立、客觀、具新聞價值的新聞稿。寫作規範：
   > - 標題簡潔有力，能抓住核心事件
   > - 導言段（Lead）涵蓋 5W1H（人、事、時、地、為何、如何）
   > - 內文依重要性遞減排列（倒金字塔結構）
   > - 適度加入受訪者引述（使用引號），增加臨場感
   > - 結尾可加入活動意義或後續展望
   > - 語氣中立、客觀，不添加個人評論
   >
   > **第二角色：資深 Web 無障礙工程師**
   >
   > 將上方的新聞稿轉換為完全符合 WCAG 2.2 AAA 規範的 HTML 片段，確保能直接貼入 XOOPS 系統的 CKEditor 中使用。
   >
   > Execution Rules:
   > 1. 結構與標題層級：一律從 `<h3>` 開始向下遞增。禁用 `<h1>` 與 `<h2>`。純視覺美化請用 Bootstrap 5 字級類別（如 `<span class="fs-4 fw-bold">`），禁止濫用標題標籤。
   > 2. 連結處理：嚴禁直接將網址字串作為超連結文字。title 屬性僅用於提示特殊行為（如「另開新視窗」），且 target 不為 _blank 時不得寫入。不得增減連結數量，Email 嚴禁加上連結。
   > 3. 圖片與表格：所有 `<img>` 加入 `.img-fluid`。嚴禁在 style 中寫死寬高。提供精確 alt 描述，裝飾性圖片用 `alt=""`。圖片含表格/文字需在下方產生對應 HTML 表格或語意化摘要。表格 caption 用 `style="caption-side: top;"`.
   > 4. 色彩與樣式：自訂色彩對比度須符合 WCAG 2.2 AAA 7:1。優先使用 Bootstrap 5 類別。最小化 inline CSS。
   > 5. 內容忠實：不得自行增減原始內容中的連結或檔案數量。
> 6. 字元編碼：在 `<head>` 中加入 `<meta charset="utf-8">`，確保中文字在 GitHub Pages 上正確顯示。
   >
   > Output: 僅輸出純 HTML 程式碼片段，包裝在單一 ```html 區塊中。禁止任何問候、解釋或結語。
   >
   > ---
   >
   > [在此插入報告 Markdown 內容]

4. 將轉換後的 HTML 存成 `.html` 檔案在本機
5. 告知使用者 HTML 已存檔，可貼入 XOOPS CKEditor

## 步驟六：產出結果報告

產出完成後，依以下格式回報給使用者：

```
═══════════════════════════════════
  FB 頻道更新摘要 — 完成報告
═══════════════════════════════════

📁 來源：<內容來源摘要>
📓 筆記本：<筆記本名稱>

📋 產出項目：
  ✅ 更新摘要記事
  ✅ 報告 → Google Docs：<連結>
  ✅ 簡報：<檔案路徑>
  ✅ 資訊圖表：<檔案路徑>
  ✅ 無障礙網頁：<檔案路徑>

🔗 筆記本連結：<NotebookLM URL>
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## 錯誤處理

| 狀況 | 處理方式 |
|------|---------|
| FB 網址無法抓取（webfetch 失敗） | 告知使用者「無法自動抓取 FB 內容」，請使用者手動貼上 |
| NotebookLM auth 失敗 | 提示使用者執行 `nlm login` 重新認證 |
| Studio 產出逾時（超過 3 分鐘） | 告知使用者仍在生成中，提供 NotebookLM 連結讓使用者自行查看進度 |
| 無障礙網頁轉換時報告內容為空 | 跳過此項，告知使用者「報告尚未完成，無法轉換」 |
```

## 常見問題

| 問題 | 解法 |
|------|------|
| 說「FB 摘要」沒反應 | 確認 SKILL.md 已放在正確路徑，並重啟 OpenCode |
| NotebookLM 認證過期 | 執行 `nlm login` 重新登入 |
| FB 網址無法自動抓取 | 選擇「手動貼上貼文內容」，直接複製貼文 |
| Studio 產出逾時 | NotebookLM 生成中，提供連結讓你自己查看進度 |
| 無障礙網頁內容空白 | 先執行「報告」產出，再單獨執行無障礙網頁 |
| 可以一次處理多篇貼文嗎？ | 可以。將多篇貼文整理成一份 .md 或 .txt 檔案選擇「從檔案讀取」即可 |
| 能指定產出的語言嗎？ | 可以。在詢問風格偏好時告知語言偏好，或直接在步驟四選擇對應參數 |
| 產出的檔案存在哪裡？ | 摘要記事存在 NotebookLM 內；下載的檔案存在工作目錄或你指定的路徑 |
| 如何更新 Skill 到新版本？ | 重新執行此懶人包，🔁 檢查會詢問是否要更新現有 SKILL.md |
| 粉專設為不公開能抓嗎？ | 不能。不公開貼文請選擇「手動貼上貼文內容」 |
| 可以跟 Obsidian 搭配嗎？ | 可以。先產出摘要，再對 OpenCode 說「把這篇摘要存入 Obsidian」 |
| 產出到一半中斷怎麼辦？ | 重新說「FB 摘要」，選擇同一本筆記本，已存在的資料不會重複 |

---

## 更新紀錄

| 日期 | 版本 | 更新內容 |
|------|------|---------|
| 2026-06-10 | v0.5 | 深度擴充：20 個使用範例（4 類）、12 題常見問題、🔁 重複執行檢查、FAQ 擴充 |
| 2026-06-09 | v0.1 | 初版 |

---

## 相關連結

- [NotebookLM MCP CLI](https://github.com/jacob-bd/notebooklm-mcp-cli)
- [📋 OpenCode 懶人包索引](./README.md)
