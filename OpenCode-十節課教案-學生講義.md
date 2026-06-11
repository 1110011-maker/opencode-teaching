---
title: 'AI 助教 OpenCode — 十節課學生講義'
date: '2026-06-10'
version: v1.0
status: 初版
tags:
  - OpenCode
  - 學生講義
  - 國中
  - 資訊科技
---

# AI 助教 OpenCode — 十節課學生講義

> 你的名字：__________  班級：__________  座號：____

---

## 第一課：AI 與 OpenCode 初體驗

### 本課目標
- [ ] 能說出 AI 是什麼
- [ ] 能說出 OpenCode 能做什麼
- [ ] 對 AI 助教產生興趣

### 活動一：暖身討論（5 分鐘）

**想一想，跟隔壁同學討論：**

1. 你聽過哪些 AI 產品或服務？
   _________________________________

2. 你用過哪些？用來做什麼？
   _________________________________

3. 你覺得 AI 最厲害的地方是什麼？
   _________________________________

### 活動二：認識 AI（10 分鐘）

**AI = Artificial Intelligence（人工智慧）**

簡單說：**讓電腦像人一樣思考、學習、解決問題的技術。**

生活中到處都有 AI：
- 手機人臉解鎖 → AI 辨識你的臉
- YouTube 推薦影片 → AI 分析你喜歡看什麼
- Gmail 垃圾郵件過濾 → AI 判斷哪些是垃圾信
- ChatGPT / OpenCode → AI 理解和生成文字

**AI 能做到的事：**
| 能力 | 說明 | 例子 |
|------|------|------|
| 理解語言 | 讀懂你寫的字 | 問 AI 問題 |
| 生成文字 | 寫出文章、程式碼 | 請 AI 寫一篇短文 |
| 分析資料 | 從大量資訊中找重點 | 請 AI 整理一堆資料 |
| 解決問題 | 一步一步推理 | 請 AI 解數學題 |

**AI 做不到的事（很重要）：**
- AI 沒有「自己的想法」— 它只是根據學過的資料來回答
- AI 可能會出錯 — 所以要自己判斷答案對不對
- AI 不會代替你思考 — 它是「輔助工具」，不是「作弊工具」

### 活動三：OpenCode 是什麼？（10 分鐘）

**OpenCode 是一個 AI 程式設計助教。**

你可以把它想像成一個：
- **很會寫程式的同學** — 坐在你旁邊，隨時幫你
- **很會整理筆記的助教** — 幫你把複雜的東西變簡單
- **24 小時不下班的老師** — 隨時回答你的問題

**OpenCode 可以幫你做這些事：**
- 解釋程式碼：「這段程式在做什麼？」
- 寫程式：「幫我寫一個計算機程式」
- 找 bug：「我的程式為什麼跑不起來？」
- 整理資料：「幫我把這篇文章整理成三點重點」
- 操作其他工具：「幫我把這份資料做成簡報」

### 活動四：老師示範（15 分鐘）

仔細看老師的操作，把你的觀察寫下來：

**老師示範了什麼？**
_________________________________

**你最想用 OpenCode 做什麼？**
_________________________________

### 本課重點

1. AI 是讓電腦像人一樣思考的技術
2. AI 在生活中無所不在
3. OpenCode 是你的 AI 程式設計助教
4. AI 是輔助工具，不是作弊工具
5. **下週開始，你將親自安裝 OpenCode！**

---

## 第二課：安裝 OpenCode 與第一次對話

### 本課目標
- [ ] 能下載並安裝 OpenCode 桌面版
- [ ] 能取得 API Key
- [ ] 能與 OpenCode 對話

### 步驟一：下載 OpenCode 桌面版（15 分鐘）

> 💡 需要更詳細的步驟說明？可以參考 [`00-新手安裝指南.md`](./00-新手安裝指南.md)（從零開始的完整圖文引導）

跟著以下步驟操作：

**① 打開瀏覽器，輸入網址：**
```
https://opencode.ai
```

**② 點擊「Download」或「下載」按鈕**
- 選擇 Windows 版本（.exe 安裝檔）

**③ 執行安裝程式**
- 雙擊下載的安裝檔
- 按照畫面指示完成安裝（一直按「下一步」即可）
- 安裝完成後，桌面應該會出現 OpenCode 的圖示

**④ 開啟 OpenCode**
- 雙擊桌面圖示開啟
- 第一次開啟可能需要等待一下

**檢查點 □** OpenCode 安裝完成並成功開啟

### 步驟二：取得 API Key（10 分鐘）

OpenCode 需要一個「API Key」才能連接 AI 模型。我們用 OpenRouter 來取得：

**① 打開瀏覽器，前往：**
```
https://openrouter.ai
```

**② 註冊帳號**
- 點「Sign Up」
- 可以用 Google 帳號快速註冊

**③ 建立 API Key**
- 登入後，點右上角頭像 →「Keys」
- 點「Create Key」
- 為你的 Key 取一個名字（例如「我的OpenCode」）
- 複製出現的 Key（一串很長的文字）

**④ 將 API Key 貼入 OpenCode**
- 在 OpenCode 中，找到設定（Settings）→ Provider 設定
- 選擇 OpenRouter
- 貼上你的 API Key
- 儲存設定

⚠️ **API Key 就像你的密碼，不要傳給別人！**

**檢查點 □** API Key 設定完成

### 步驟三：第一次對話（10 分鐘）

在 OpenCode 的對話框中輸入以下內容，看看它怎麼回應：

**練習 1：**
```
Hello OpenCode！我是（你的名字），請多多指教！
```

**練習 2：**
```
1+1 等於多少？
```

**練習 3：**
```
請用簡單的話解釋什麼是「演算法」
```

把 OpenCode 的回答記錄下來：

**練習 1 的回答：**
_________________________________

**練習 2 的回答：**
_________________________________

**練習 3 的回答：**
_________________________________

### 本課重點

1. OpenCode 桌面版可以從官網下載安裝
2. 需要 API Key 才能使用 → 用 OpenRouter 申請
3. API Key 要保密，不要給別人
4. 你成功了！你已經跟 AI 對話過了！

---

## 第三課：提示技巧入門

### 本課目標
- [ ] 能分辨好問題和壞問題
- [ ] 能寫出具體的提示詞
- [ ] 能完成三種提示練習

### 什麼是「提示」？

提示（Prompt）就是你對 AI 說的話。**同樣的意思，不同的說法，AI 的回答品質差很多！**

### 好問題 vs 壞問題（10 分鐘）

**壞問題 ❌：**
| 問題 | 為什麼不好？ |
|------|------------|
| 「幫我寫程式」 | 太模糊，AI 不知道你要寫什麼 |
| 「解釋這個」 | 沒有說要解釋什麼 |
| 「告訴我歷史」 | 範圍太大，AI 不知道從哪開始 |
| 「好不好？」 | 封閉式問題，AI 只能回「好」或「不好」 |

**好問題 ✅：**
| 問題 | 為什麼好？ |
|------|-----------|
| 「幫我用 Python 寫一個加法計算機」 | 具體：語言 + 功能 |
| 「請用國中生聽得懂的話解釋光合作用」 | 有對象 + 有範圍 |
| 「幫我整理這三段文字的重點，用三點條列式」 | 有格式要求 |
| 「秦始皇的焚書坑儒有哪些正反評價？」 | 有具體事件 + 要求多角度 |

**好問題公式：**
> **角色 + 任務 + 細節 + 格式**

例如：「你是國中老師（角色），解釋 for 迴圈（任務），用生活例子（細節），用條列式（格式）」

### 練習一：作業輔助（10 分鐘）

**任務：** 請 OpenCode 幫你解釋一個上課聽不懂的觀念。

**範例問題：**
```
我是一個國中生，請用簡單的話解釋什麼是「變數」，
舉一個生活例子，最後用一句話總結。
```

**你的問題：**
_________________________________

**OpenCode 的回答摘要：**
_________________________________

### 練習二：資料整理（10 分鐘）

**任務：** 任意找一段課本內容或網路文章，請 OpenCode 整理重點。

**老師提供的文章：**
> 臺灣位處於板塊交界帶，地質活動頻繁，因此擁有豐富的溫泉資源。全臺從北到南都有溫泉分布，如北投溫泉、烏來溫泉、關子嶺溫泉、知本溫泉等。溫泉的種類也很多樣，有碳酸氫鈉泉、硫磺泉、食鹽泉等不同類型。溫泉不僅可以泡湯放鬆，也成為臺灣重要的觀光資源。

**你的提示詞：**
```
請幫我整理上面這段文章的重點，用三點條列式，
每一點不超過 20 個字。
```

**OpenCode 的回答：**
_________________________________

### 練習三：創意發想（5 分鐘）

**任務：** 請 OpenCode 給你想不出來的靈感。

**範例問題：**
```
我想做一個關於環保的專題報告，請給我 5 個有創意的方向，
每個方向用一句話說明可以做什麼。
```

**你的問題（自訂主題）：**
_________________________________

**OpenCode 的回答：**
_________________________________

### 好問題的三個原則

1. **具體** — 不要模糊，說清楚要什麼
2. **有格式** — 告訴 AI 你希望答案長怎樣
3. **給範圍** — 限制長度、對象、角度

---

## 第四課：懶人包 #00 環境建置（上）

### 本課目標
- [ ] 能說出 Git、gh、uv 各是做什麼的
- [ ] 能完成環境檢查
- [ ] 能安裝 Git

### 為什麼要裝這些工具？

| 工具 | 用途 | 比喻 |
|------|------|------|
| **Git** | 版本控管 — 記錄檔案每一次的修改 | 像電玩的「存檔」功能 |
| **GitHub CLI (gh)** | 讓你的電腦跟 GitHub 雲端溝通 | 像遙控器，操控雲端倉庫 |
| **uv** | Python 套件管理，未來裝 AI 工具會用到 | 像 App Store 但給 Python 用 |

### 步驟零：環境檢查（15 分鐘）

**請打開 PowerShell（按鍵盤 Win + R → 輸入 `powershell` → Enter）**

依序執行以下指令，檢查你的電腦已經裝了哪些工具：

**檢查項目 1：作業系統**
```powershell
[System.Environment]::OSVersion.VersionString
```

**檢查項目 2：網路連線**
```powershell
ping google.com
```
> 如果有回應（顯示時間）→ 網路正常
> 如果顯示「找不到主機」→ 檢查網路連線

**檢查項目 3：Git**
```powershell
git --version
```
> 有顯示版本號 → ✅ 已安裝
> 顯示無法辨識 → ❌ 未安裝（步驟一會裝）

**檢查項目 4：GitHub CLI**
```powershell
gh --version
```
> 有顯示版本號 → ✅ 已安裝
> 顯示無法辨識 → ❌ 未安裝（下週裝）

**檢查項目 5：uv**
```powershell
uv --version
```
> 有顯示版本號 → ✅ 已安裝
> 顯示無法辨識 → ❌ 未安裝（下週裝）

**檢查項目 6：winget（Windows 限定）**
```powershell
winget --version
```
> 有顯示版本號 → ✅ 已安裝
> 顯示無法辨識 → ❌ 未安裝（老師協助）

**環境檢查表（打勾 ✅ 或 打叉 ❌）：**

| 項目 | 狀態 | 備註 |
|------|------|------|
| 作業系統確認 | □ | |
| 網路連線 | □ | |
| Git | □ | |
| GitHub CLI (gh) | □ | |
| uv | □ | |
| winget | □ | |

### 步驟零之一：安裝 winget（5 分鐘，如有需要）

> **⚠️ 只有上一步檢查 winget 未安裝的人才需要做這一步！**

如果你的 Windows 沒有 winget：
1. 打開瀏覽器，前往 https://aka.ms/winget-cli
2. 下載 `.msixbundle` 檔案
3. 雙擊執行安裝
4. 完成後在 PowerShell 中確認：
```powershell
winget --version
```

### 步驟一：安裝 Git（15 分鐘）

> **⚠️ 只有環境檢查時 Git 未安裝的人才需要做這一步！**

在 PowerShell 中輸入：

```powershell
winget install --id Git.Git --accept-source-agreements --accept-package-agreements
```

安裝過程中會出現進度條，請等待它跑完。

**安裝完成後，確認版本：**
```powershell
git --version
```

你應該看到類似這樣的畫面：
```
git version 2.4x.x.windows.x
```

**檢查點 □** Git 安裝完成，版本號顯示成功

### 本課重點

1. Git 是版本控管工具（像存檔功能）
2. gh 讓你的電腦跟 GitHub 溝通
3. uv 是 Python 套件管理器
4. 環境檢查要先做，才知道哪些裝過了
5. **下週完成 gh 和 uv 的安裝！**

---

## 第五課：懶人包 #00 環境建置（下）

### 本課目標
- [ ] 能安裝 GitHub CLI（gh）
- [ ] 能安裝 uv
- [ ] 能完成最終驗證

### 回顧（3 分鐘）

上週你裝了哪個工具？還沒裝哪個？

**已安裝：** □ Git  □ winget
**待安裝：** □ GitHub CLI (gh)  □ uv

### 步驟二：安裝 GitHub CLI（12 分鐘）

> **⚠️ 只有環境檢查時 gh 未安裝的人才需要做這一步！**

在 PowerShell 中輸入：

```powershell
winget install --id GitHub.cli --accept-source-agreements --accept-package-agreements
```

等待安裝完成。

**確認版本：**
```powershell
gh --version
```

你應該看到類似這樣的畫面：
```
gh version x.x.x
```

**檢查點 □** GitHub CLI 安裝完成

### 步驟三：安裝 uv（12 分鐘）

> **⚠️ 只有環境檢查時 uv 未安裝的人才需要做這一步！**

在 PowerShell 中輸入：

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

安裝完成後，**關閉 PowerShell 再重新開啟**，然後確認版本：

```powershell
uv --version
```

你應該看到類似這樣的畫面：
```
uv x.x.x
```

**檢查點 □** uv 安裝完成

### 步驟四：最終驗證（13 分鐘）

依序執行以下四個指令，**全部都要正確顯示版本號才算是完成！**

```powershell
git --version
```
版本：_________________

```powershell
gh --version
```
版本：_________________

```powershell
uv --version
```
版本：_________________


```powershell
winget --version
```
版本：_________________

**全部過關了嗎？** □ 是 → ✅ 懶人包 #00 完成！
□ 否 → 請舉手問老師

### 懶人包 #00 完成確認

| 工具 | 版本號 | 狀態 |
|------|--------|------|
| Git | | ✅ |
| GitHub CLI | | ✅ |
| uv | | ✅ |
| winget | | ✅ |

簽名：__________  日期：__________

---

## 第六課：懶人包 #01 連接 NotebookLM（上）

### 本課目標
- [ ] 能說出 NotebookLM 是什麼
- [ ] 能說出三角關係的三個角色
- [ ] 能安裝 nlm

### 什麼是 NotebookLM？（5 分鐘）

**NotebookLM** 是 Google 推出的 AI 研究助理。

**跟 ChatGPT 有什麼不同？**

| | ChatGPT | NotebookLM |
|--|---------|------------|
| 知識來源 | 網路上學到的資料 | **你給它的資料** |
| 會出錯嗎？ | 可能會亂掰 | 只根據你給的資料回答 |
| 適合做什麼 | 一般問答、創作 | 研究、分析你的文件 |

**簡單說：** NotebookLM 像一個「只讀你給它的課本來回答問題的超級助教」。

### 三角關係與 MCP 原理（10 分鐘）

```
你 ← 講中文 → OpenCode ← MCP 協定 → nlm ← Google 登入 → NotebookLM
```

**三個角色：**
1. **OpenCode** — 你的 AI 助教，聽得懂中文
2. **nlm** （翻譯官）— 負責把 OpenCode 的指令轉給 NotebookLM
3. **NotebookLM** — Google 的 AI 研究助理

**為什麼需要 nlm 翻譯官？**
- NotebookLM 沒有提供「官方程式接口」
- nlm 用「模擬瀏覽器操作」的方式，假裝是人在操作網頁
- 就像你有一個機器人幫你自動點滑鼠

**MCP 是什麼？**
- MCP = Model Context Protocol
- 是 OpenCode 跟外部工具溝通的「標準接口」
- 比喻：像 USB-C 接口，只要工具支援就能插上去用

**一句話記住：**
> 你跟 OpenCode 講中文，OpenCode 叫 nlm 去操作 NotebookLM，成品自動存到你電腦裡。

### 步驟零：環境檢查（10 分鐘）

打開 PowerShell，檢查以下項目：

**確認 uv 已安裝（上週裝好了嗎？）：**
```powershell
uv --version
```
□ 已安裝（繼續） □ 未安裝（舉手請老師幫忙）

**確認網路連線：**
```powershell
ping google.com
```
□ 正常

**確認 OpenCode 版本：**
```powershell
opencode --version
```
□ 顯示版本號

### 步驟一：安裝 notebooklm-mcp-cli（15 分鐘）

**先檢查是否已經裝過：**
```powershell
uv tool list
```
如果看到 `notebooklm-mcp-cli` 在清單中 → 跳過安裝

如果沒有 → 執行安裝：

```powershell
uv tool install notebooklm-mcp-cli
```

等候安裝完成（可能需要幾分鐘）。

**確認安裝成功：**
```powershell
nlm --version
```

應該看到類似：
```
nlm x.x.x
```

**檢查點 □** nlm 安裝成功

### 本課重點

1. NotebookLM 是以你的資料為基礎的 AI 助理
2. 三角關係：OpenCode → nlm → NotebookLM
3. MCP 是 OpenCode 跟工具溝通的標準接口
4. nlm 用 `uv tool install` 安裝
5. **下週要登入 Google 並連上 NotebookLM！**

---

## 第七課：懶人包 #01 連接 NotebookLM（下）

### 本課目標
- [ ] 能完成 Google 登入認證
- [ ] 能設定 MCP 連接
- [ ] 能測試連接成功

### 步驟二：登入 Google 帳號（12 分鐘）

**① 先檢查是否已經登入過：**
```powershell
nlm doctor
```

如果顯示 `Authentication valid!` → ✅ 已登入，跳到步驟三
如果顯示未認證 → 繼續以下步驟

**② 登入 Google：**
```powershell
nlm login
```

執行後，瀏覽器會自動開啟 Google 登入頁面。

**③ 在瀏覽器中：**
1. 選擇或輸入你的 Google 帳號
2. 輸入密碼
3. 按允許授權

**④ 回到 PowerShell，確認登入成功：**
```powershell
nlm doctor
```

應該顯示：
```
Authentication valid!
```

**檢查點 □** Google 帳號登入成功

### 步驟三：設定 MCP 連接（10 分鐘）

**① 先檢查是否已經設定過：**
```powershell
nlm setup list
```

如果看到 `opencode` 在清單中 → ✅ 已設定，跳到步驟四

**② 設定 MCP：**
```powershell
nlm setup add opencode
```

**③ 確認設定成功：**
```powershell
nlm setup list
```

應該能看到 `opencode` 在清單中。

**檢查點 □** MCP 連接設定完成

### 步驟四：建立本地資料夾（5 分鐘）

在 PowerShell 中執行：

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\slides"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\infographics"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\audio"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\video"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\docs"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\sheets"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\mindmaps"
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\Documents\NotebookLM\quizzes"
```

**檢查點 □** 資料夾建立完成

### 步驟五～六：重啟 OpenCode 並測試（10 分鐘）

**① 完全關閉 OpenCode**（不是縮小，要真的關掉）

**② 重新開啟 OpenCode**

**③ 測試連線 — 對 OpenCode 說：**
```
請幫我建立一個名為「測試筆記本」的 NotebookLM notebook
```

**④ 確認成功後，再請 OpenCode 刪除它：**
```
請刪除剛剛建立的「測試筆記本」
```

**⑤ 如果都成功 → ✅ 懶人包 #01 完成！**

**檢查點 □** 測試 notebook 建立成功
**檢查點 □** 測試 notebook 刪除成功

### 懶人包 #01 完成確認

| 項目 | 狀態 |
|------|------|
| nlm 已安裝 | □ |
| Google 已登入 | □ |
| MCP 已設定 | □ |
| 資料夾已建立 | □ |
| 測試成功 | □ |

簽名：__________  日期：__________

---

## 第八課：NotebookLM 實戰應用

### 本課目標
- [ ] 能建立 notebook 並上傳資料
- [ ] 能產出 slide deck
- [ ] 能產出 mind map 和 infographic

### 活動一：建立 notebook + 上傳資料（10 分鐘）

**步驟 1：對 OpenCode 說：**
```
請幫我建立一個名為「（你的主題）」的 NotebookLM notebook
```
> 主題建議：自然科學某一章、社會課某主題、你有興趣的任何題目

**步驟 2：準備要上傳的資料**
- 在電腦中準備一段文字內容（可以是課本內容、網路文章、自己的筆記）
- 對 OpenCode 說：
```
請把我剛剛準備的內容加入剛剛建立的 notebook
```

**檢查點 □** notebook 建立成功 + 資料已上傳

### 活動二：產出簡報（10 分鐘）

對 OpenCode 說：
```
請幫我從這個 notebook 產生一份 slide deck 簡報，語言用繁體中文
```

等候 NotebookLM 生成簡報（可能需要 1–2 分鐘）。

**簡報產出後，下載到本機：**
對 OpenCode 說：
```
請幫我把這份簡報下載到 Documents/NotebookLM/slides/
```

**檢查點 □** 簡報產出並下載成功

### 活動三：產出心智圖 + 資訊圖表（7 分鐘）

**心智圖：**
對 OpenCode 說：
```
請幫我從這個 notebook 產生一份 mind map
```

**資訊圖表：**
對 OpenCode 說：
```
請幫我從這個 notebook 產生一張 infographic，方向用橫向（landscape），繁體中文
```

**檢查點 □** 心智圖產出成功
**檢查點 □** 資訊圖表產出成功

### 活動四：自由探索（12 分鐘）

試試看以下變化：

**嘗試不同的產出組合：**
- 產出 quiz 測驗題
- 產出 flashcards 閃卡
- 產出 briefing doc 報告

**嘗試不同主題：**
- 換一個主題再試一次

**記錄你最滿意的產出：**
_________________________________
_________________________________

### 本課重點

1. NotebookLM 可以產出多種形式的內容
2. 簡報、心智圖、資訊圖表都能一鍵生成
3. 產出的檔案可以下載到本機
4. **下週要裝最後一個懶人包 #08！**

---

## 第九課：懶人包 #08 安裝 FB 頻道摘要 Skill

### 本課目標
- [ ] 能說出什麼是 OpenCode Skill
- [ ] 能安裝 fb-notebooklm Skill
- [ ] 能測試 Skill 正常運作

### 什麼是 OpenCode Skill？（5 分鐘）

**Skill 是 OpenCode 的擴充功能。**

就像手機可以安裝 App 來增加功能一樣，OpenCode 可以安裝 Skill 來增加能力。

**比喻：**
| 手機 | OpenCode |
|------|---------|
| 手機本身可以打電話、傳訊息 | OpenCode 本身可以對話、寫程式 |
| 安裝 LINE App → 可以傳即時訊息 | 安裝 fb-notebooklm Skill → 可以做 FB 摘要 |
| 安裝 Google Maps → 可以導航 | 安裝其他 Skill → 有其他功能 |

**fb-notebooklm Skill 能做到的事：**
- 把 FB 粉專的貼文內容餵給 NotebookLM
- 自動產出：摘要記事、報告、簡報、資訊圖表、無障礙網頁
- 全部批次完成，一次搞定

### 步驟一：確認認證（5 分鐘）

打開 PowerShell，確認 NotebookLM 連線正常：

```powershell
nlm doctor
```

應該顯示：
```
Authentication valid!  (以及你的筆記本數量)
```

□ 認證正常 → 繼續
□ 未認證 → 執行 `nlm login` 重新登入

### 步驟二：安裝 Skill 檔案（15 分鐘）

**① 請打開記事本（或 VS Code），準備貼入以下內容：**

**② 建立 SKILL.md 檔案**

在記事本中，貼入下方的完整內容。這是 SKILL.md 的內容，**要全部複製貼上**：

> ⚠️ 以下內容很長，請仔細複製，不要漏掉任何部分！

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
- (1) 手動貼上 → 請使用者直接貼上貼文內容（含發文日期），收到後繼續
- (2) 粉專網址 → 先嘗試自動抓取；失敗則告知使用者手動貼上
- (3) 從檔案讀取 → 讀取使用者指定的檔案

## 步驟二：詢問 NotebookLM 筆記本

詢問要用哪本筆記本：(1) 選擇現有 (2) 新建一本

## 步驟三：將內容加入 NotebookLM

使用 notebooklm_source_add 將 FB 內容加入選定的筆記本。

## 步驟四：詢問要產出哪些內容

讓使用者複選：
- 📓 更新摘要記事（NotebookLM Note）
- 📄 報告 + 匯出 Google 文件（Briefing Doc）
- 📊 簡報（Slide Deck）
- 🖼️ 資訊圖表（16:9 繁體中文）
- 🌐 無障礙網頁（WCAG 2.2 AAA HTML）

## 步驟五：執行批次產出

依序執行勾選的項目，每項完成後記錄結果再進行下一項。

## 步驟六：產出結果報告

產出完成後，回報給使用者完成報告（含專案、產出項目、檔案路徑）。
```

**③ 在 PowerShell 中執行（請先複製整段指令貼上）：**

```powershell
# 建立技能資料夾
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.config\opencode\skills\fb-notebooklm"

# 確認資料夾已建立
Test-Path "$env:USERPROFILE\.config\opencode\skills\fb-notebooklm"
```
應該顯示 `True`

**④ 回到記事本，按 Ctrl+A 全選 → Ctrl+C 複製 → 關閉記事本**

**⑤ 建立 SKILL.md 檔案（在 PowerShell 中執行）：**

把剛剛複製的內容貼到以下指令的引號中間（或請老師協助）：

> 從「開始」功能表搜尋「Windows PowerShell」，以滑鼠右鍵選擇「以系統管理員身分執行」

或者更簡單的方法：在檔案總管中前往以下路徑，手動建立檔案：
```
%USERPROFILE%\.config\opencode\skills\fb-notebooklm\
```
在該資料夾中新增一個文字檔案，命名為 `SKILL.md`，然後把記事本中的內容貼進去儲存。

**檢查點 □** SKILL.md 已存在於正確路徑

### 步驟三：重啟 OpenCode（5 分鐘）

**完全關閉 OpenCode**（不是縮小），然後重新開啟。

**檢查點 □** OpenCode 已重啟

### 步驟四：測試 Skill（12 分鐘）

對 OpenCode 說：

```
FB 摘要
```

OpenCode 應該會載入 fb-notebooklm Skill，然後依序詢問你：

1. FB 內容來源 → 選擇「手動貼上」，貼上一段文字
2. NotebookLM 筆記本 → 選擇「新建一本」
3. 要產出哪些內容 → 選擇至少一項
4. 等待執行完成

**如果成功看到互動問答流程 → ✅ 懶人包 #08 完成！**

**檢查點 □** Skill 測試成功

### 懶人包 #08 完成確認

| 項目 | 狀態 |
|------|------|
| nlm doctor 認證正常 | □ |
| SKILL.md 已安裝 | □ |
| OpenCode 重啟 | □ |
| 測試「FB 摘要」成功 | □ |

簽名：__________  日期：__________

---

## 第十課：整合應用 + 成果展示

### 本課目標
- [ ] 能串聯三個懶人包完成一個專題
- [ ] 能展示自己的作品
- [ ] 能說出使用 AI 時要注意什麼

### 活動一：完整工作流程回顧（5 分鐘）

```
#00 環境建置          #01 連接 NotebookLM      #08 安裝 Skill
  ├─ Git                  ├─ nlm 安裝              ├─ SKILL.md
  ├─ GitHub CLI (gh)      ├─ Google 登入           ├─ 互動測試
  ├─ uv                   ├─ MCP 設定
  └─ 驗證通過              └─ 測試連線
                              │
                              ▼
                       ┌─────────────┐
                       │  開始使用！ │
                       │  NotebookLM │
                       └─────────────┘
```

### 活動二：選題與規劃（5 分鐘）

選一個你有興趣的主題，規劃如何使用 OpenCode + NotebookLM 來完成。

**我的主題：**
_________________________________

**我要用到的 OpenCode 功能：**
□ 對話問答
□ 整理重點
□ NotebookLM 筆記本
□ 產出簡報
□ 產出心智圖
□ 產出資訊圖表
□ 其他：__________

**我的計畫步驟：**
1. ________________________________
2. ________________________________
3. ________________________________
4. ________________________________

### 活動三：實作時間（20 分鐘）

開始動手做！以下是一些方向供參考：

**主題建議：**
- 用 OpenCode 幫你規劃讀書計畫
- 用 NotebookLM 整理一課重點並產出簡報
- 用 OpenCode 幫你寫程式
- 用 NotebookLM 分析一篇文章

**實作記錄：**
_________________________________

_________________________________

_________________________________

### 活動四：成果分享（10 分鐘）

準備 1 分鐘向大家介紹你的作品：

**我的作品名稱：**
_________________________________

**我用了哪些工具：**
_________________________________

**我最滿意的成果：**
_________________________________

**遇到的困難：**
_________________________________

**如何解決的：**
_________________________________

### 活動五：AI 素養（5 分鐘）

**使用 AI 時一定要注意的事：**

**✅ 可以做的事：**
- 用 AI 幫你理解不懂的觀念
- 用 AI 幫你整理重點
- 用 AI 給你靈感和方向
- 用 NotebookLM 分析你自己的資料

**❌ 不可以做的事：**
- 直接複製 AI 的回答交作業（那是抄襲！）
- 把個人資料（姓名、電話、地址）給 AI
- 完全相信 AI 說的話（它也會出錯）
- 用 AI 做傷害別人的事

**記得：AI 是工具，你才是主人！**

### 課程總結

**這十節課你學到了：**

1. ✅ AI 是什麼、OpenCode 能做什麼
2. ✅ 安裝 OpenCode 並與它對話
3. ✅ 好的提示技巧
4. ✅ 環境建置（Git、gh、uv）
5. ✅ 連接 NotebookLM
6. ✅ NotebookLM 實戰應用
7. ✅ 安裝 FB 頻道摘要 Skill
8. ✅ 整合運用

**你最喜歡的課程：**
_________________________________

**你覺得最難的部分：**
_________________________________

**你想繼續學什麼：**
_________________________________

---

### 期末檢查清單

| 課次 | 完成？ | 備註 |
|------|--------|------|
| 1 — AI 與 OpenCode 初體驗 | □ | |
| 2 — 安裝 OpenCode | □ | |
| 3 — 提示技巧 | □ | |
| 4 — 環境建置（上）Git | □ | |
| 5 — 環境建置（下）gh + uv | □ | |
| 6 — 連接 NotebookLM（上）nlm | □ | |
| 7 — 連接 NotebookLM（下）登入 + 測試 | □ | |
| 8 — NotebookLM 實戰 | □ | |
| 9 — FB 頻道摘要 Skill | □ | |
| 10 — 整合應用 + 成果 | □ | |
