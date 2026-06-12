---
title: 'OpenCode 懶人包 #02：連接 GitHub'
date: '2026-06-07'
type: 懶人包
version: v0.6
status: 強化版
tags:
  - OpenCode
  - 懶人包
  - GitHub
  - GitHub-Pages
---
# OpenCode 懶人包 #02：連接 GitHub

> 版本：v0.6
> 更新日期：2026-06-11

> 📌 **本懶人包可獨立執行**：會自動檢查並安裝所需工具，不需要先看過其他懶人包。你只要確認下方「先備條件」即可開始。

---

## 這個懶人包會幫你做什麼？

讓你的 OpenCode 桌面版能夠直接操控 GitHub，包括：
- 建立 GitHub 儲存庫（repo）
- 把 OpenCode 做好的網頁、遊戲、教材推送上線
- 開啟 GitHub Pages，讓學生掃 QR Code 就能開啟
- 以後每次做好新教材，一句話就能上線

---

## 先備條件

在使用這個懶人包之前，請確認：

- [ ] OpenCode 桌面版已安裝且能正常使用
- [ ] 有可用的 email 信箱（如果還沒 GitHub 帳號，懶人包會引導你註冊）
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

> 🔁 **重複執行安全檢查**：如果所有工具都已安裝且設定完整，此步驟直接跳過。

請 OpenCode 在開始前，先自動確認以下所有項目。
> 如果有任何一項不符合，請先告知使用者問題所在，並引導解決後再繼續。
> **不要跳過任何一項檢查，不要假設環境正常。**

1. **確認作業系統**：執行系統指令確認是 Windows / macOS / Linux，後續所有指令請根據實際的作業系統選擇正確版本執行
2. **確認網路連線正常**：嘗試 ping 一個外部網站
3. **檢查 Git 是否已安裝**：執行 `git --version`，如果未安裝：
   - Windows：`winget install --id Git.Git --accept-source-agreements --accept-package-agreements`
   - macOS：`xcode-select --install`
   - Linux：`sudo apt update && sudo apt install git -y`
4. **檢查 GitHub CLI 是否已安裝**：執行 `gh --version`，如果未安裝：
   - Windows：`winget install --id GitHub.cli --accept-source-agreements --accept-package-agreements`
   - macOS：`brew install gh`
5. **檢查 Git 使用者資訊是否已設定**：執行 `git config --global user.name` 和 `git config --global user.email`

> 全部通過後，告知使用者：「環境檢查完成，所有條件都符合，開始設定。」
> 如果有不通過的項目，列出問題清單並逐一引導解決。
> 安裝完工具後如果指令找不到，請提醒使用者可能需要重啟 OpenCode 桌面版。

---

### 步驟零.五：確認使用者有 GitHub 帳號（如果還沒有,幫忙註冊）

> 🖐️ **需要手動操作**：請 OpenCode **先詢問使用者**：「你有 GitHub 帳號了嗎?」
>
> - **已有帳號** → 跳到步驟一
> - **還沒有** → 請 OpenCode 依照以下流程引導使用者註冊（約 3 分鐘）

#### 註冊 GitHub 帳號引導流程

**Step 1：打開註冊頁面**

請使用者在瀏覽器開啟：https://github.com/signup

**Step 2：填寫註冊資料（OpenCode 逐步引導）**

依序詢問使用者並提醒填寫：

| 欄位 | 說明 | 老師建議 |
|------|------|---------|
| **Email** | 常用的 email | 用學校 email 或個人常用 email |
| **Password** | 至少 15 字元 或 8 字元含數字+小寫 | 建議寫下來或存到密碼管理器 |
| **Username** | 全站唯一,之後網址會用到 | **建議用英文+數字,不要中文**。例如 `mathteacher2026`、`wang-math` |
| **Email preferences** | 是否接收電子報 | 可以取消勾選（N） |

> ⚠️ **Username 一旦決定就不好改**（GitHub Pages 網址會變），請慎重。
> 建議用「科目+姓名」或「暱稱」這種容易記的英文。

**Step 3：通過驗證**

- GitHub 會出現一個拼圖驗證（verify your account）
- 請使用者完成拼圖
- 完成後點「Create account」

**Step 4：Email 驗證**

- GitHub 會寄驗證碼到使用者 email
- 請使用者打開 email,複製 8 位數驗證碼
- 回到 GitHub 頁面貼上驗證碼

**Step 5：基本設定（可跳過）**

- 會出現「How many team members?」等問卷 → **可以直接捲到最下方點 Skip 跳過**
- 選擇 **Free 方案**（免費即可,不要選付費）

**Step 6：確認註冊成功**

- 登入後會看到 GitHub 首頁（Dashboard）
- 告知使用者：「✅ GitHub 帳號註冊完成!接下來幫你連接 OpenCode。」

> 🖐️ **常見註冊問題**：
> | 問題 | 解法 |
> |------|------|
> | Username 被搶走了 | 在後面加數字或連字號,例如 `wang-math-2026` |
> | 沒收到驗證信 | 檢查垃圾郵件匣,或點「Resend code」重寄 |
> | 拼圖驗證一直失敗 | 重新整理頁面再試一次 |
> | 想改 username | 到 Settings → Account → Change username(但會影響既有連結) |

---

### 步驟一：登入 GitHub

> 🔁 **重複執行安全檢查**：如果 `gh auth status` 顯示已登入，此步驟直接跳過。

檢查是否已登入：
```bash
gh auth status
```

如果尚未登入，改為手動方式 — 請你先產生一組 **GitHub Personal Access Token**：

> 🖐️ **請手動操作**：
>
> 1. 開啟 https://github.com/settings/tokens
> 2. 點「Generate new token (classic)」
> 3. 設定：
>    - **Note**：OpenCode CLI
>    - **Expiration**：No expiration
>    - **Scopes**：勾選 repo（全部）、workflow、read:org
> 4. 滑到最下方點「Generate token」
> 5. 複製產生的 token（一串以 `ghp_` 開頭的英數碼）
>
> ⚠️ 這組 token 只會顯示一次，請先貼到記事本暫存。

取得 token 後，由 OpenCode 自動完成登入：

請把上方產生的 token 告訴我，我來幫你完成登入。
當你提供 token 後，我會執行以下指令：

```bash
echo "<你的token>" | gh auth login --with-token
```

登入成功後確認：
```bash
gh auth status
```

---

### 步驟二：設定 Git 使用者資訊

> 🔁 **重複執行檢查**：請先執行 `git config --global user.name` 和 `git config --global user.email` 檢查是否已有設定。
> - 如果**兩個已有值** → 跳過此步驟，告知使用者「Git 使用者資訊已設定」
> - 如果**缺少任一或全部** → 繼續執行以下步驟

檢查是否已有設定：
```bash
git config --global user.name
git config --global user.email
```

如果沒有設定：

> 🖐️ **需要手動操作**：請詢問使用者他想顯示的姓名和 email。

```bash
git config --global user.name "使用者的姓名"
git config --global user.email "使用者的email"
```

---

### 步驟三：建立第一個測試 repo 並驗證

> 🔁 **本步驟已支援重複執行**。如果 repo 已存在，會自動跳過。

為了確認一切正常，建立一個測試用的 repo：

```bash
# 先檢查遠端 repo 是否已存在（避免重複執行時失敗）
if gh repo view github-test > /dev/null 2>&1; then
  echo "測試 repo 已存在於 GitHub，略過建立步驟"
else
  # 清除本機殘留目錄（如果有的話）
  if [ -d ~/Documents/github-test ]; then
    rm -rf ~/Documents/github-test
  fi

  mkdir -p ~/Documents/github-test
  cd ~/Documents/github-test
  git init
  echo '<!DOCTYPE html><html><head><meta charset="utf-8"></head><body><h1>Hello！GitHub 連接成功！</h1></body></html>' > index.html
  git add .
  git commit -m "Initial commit"
  gh repo create github-test --public --source=. --push
  gh api repos/$(gh api user -q .login)/github-test/pages -X POST -f source.branch=main -f source.path=/

  echo "等待約 1 分鐘讓 GitHub Pages 部署完成..."
fi

# 取得 GitHub Pages 網址
gh api repos/$(gh api user -q .login)/github-test/pages -q .html_url 2>/dev/null || echo "Pages 可能還在部署中"
```

1. 將上方回傳的網址告知使用者
2. 請使用者在瀏覽器開啟確認

> 🖐️ **需要手動操作**：請使用者開啟瀏覽器確認網頁顯示「Hello！GitHub 連接成功！」

---

### 步驟四：清除測試 repo（可選）

確認成功後，詢問使用者是否要刪除測試 repo：

> 🖐️ **需要手動操作**：詢問使用者「測試成功了！要保留這個測試 repo 還是刪除它？」

```bash
# 先確認 repo 確實存在再刪除
if gh repo view github-test > /dev/null 2>&1; then
  gh repo delete github-test --yes
  echo "已刪除 GitHub 上的 github-test repo"
else
  echo "遠端 repo 已不存在，跳過"
fi

# 刪除本機資料夾（如果存在的話）
if [ -d ~/Documents/github-test ]; then
  rm -rf ~/Documents/github-test
  echo "已刪除本機的 github-test 資料夾"
fi
```

告知使用者：「✅ 全部完成！你的 OpenCode 已成功連接 GitHub。以後只要說『幫我推到 GitHub 上線』，OpenCode 就會自動幫你做好。」

---

## 完成！接下來你可以這樣用

連接成功後，你隨時可以在 OpenCode 裡用自然語言操控 GitHub。以下是 20 個實際使用範例：

### 📦 類別一：Repo 操作（5 個範例）

| # | 你說的話 | OpenCode + GitHub 會做的事 | 適用時機 |
|---|---------|------------------------|---------|
| 1 | 「幫我做一個互動遊戲並推到 GitHub 上線」 | 產生 HTML → 建 repo → 推送 → 開啟 Pages → 給你網址 | 製作新教材上線 |
| 2 | 「幫我更新這個網頁的內容」 | 修改檔案 → 推送 → 自動更新 Pages | 修改既有教材 |
| 3 | 「幫我把這個 repo 刪除」 | 刪除 GitHub 上的 repo（含確認） | 清理測試或過期專案 |
| 4 | 「幫我把這個 repo 複製一份到我的帳號」 | fork 現有 repo → 設定 upstream | 參考他人專案改編 |
| 5 | 「幫我開一個組織 repo 給教學團隊用」 | 建立組織 → 建立組織 repo → 設定權限 | 團隊共同維護教材 |

### 🌐 類別二：GitHub Pages（5 個範例）

| # | 你說的話 | OpenCode + GitHub 會做的事 | 適用時機 |
|---|---------|------------------------|---------|
| 6 | 「幫我把這個網頁的 QR Code 產生出來」 | 取得 Pages 網址 → 產生 QR Code 圖片 | 讓學生掃碼開啟 |
| 7 | 「幫我設定 Pages 用自訂網域名稱」 | 設定 Pages 自訂網域 → 新增 CNAME 紀錄 | 品牌化教材網址 |
| 8 | 「幫我把 Pages 切換到 docs/ 資料夾」 | 修改 Pages 來源路徑 → 重新部署 | 使用 Jekyll 或主題 |
| 9 | 「我的 Pages 顯示 404，幫我檢查」 | 檢查部署狀態 → 確認分支 → 重新觸發部署 | Pages 故障排除 |
| 10 | 「幫我開啟 GitHub Pages」 | 檢查 repo → POST 開啟 Pages → 回報網址 | 第一次部署網站 |

### 👥 類別三：協作（5 個範例）

| # | 你說的話 | OpenCode + GitHub 會做的事 | 適用時機 |
|---|---------|------------------------|---------|
| 11 | 「幫我邀請小明當這個 repo 的協作者」 | `gh api` 新增 collaborator → 寄送邀請 | 同事共同編輯 |
| 12 | 「幫我看看有沒有待處理的 Pull Request」 | 列出所有 PR → 顯示內容 → 協助 merge | 審查協作者貢獻 |
| 13 | 「有人回報問題，幫我開一個 Issue」 | 建立 Issue → 指派負責人 → 加標籤分類 | 追蹤問題或建議 |
| 14 | 「幫我回覆 Issue #3 說問題已修正」 | 讀取 Issue → 新增 comment → 關閉 Issue | 與使用者溝通 |
| 15 | 「幫我把這個 repo 設成私人，只給團隊看」 | 修改 repo visibility → 確認協作者清單 | 尚未公開的教材 |

### 🎓 類別四：教學場景（5 個範例）

| # | 你說的話 | 流程說明 | 適用時機 |
|---|---------|---------|---------|
| 16 | 「幫我把這份教材推到 GitHub 並開啟 Pages」 | 建立 repo → 推送教材 → 開啟 Pages → 產出 QR Code | 每次完成新教材 |
| 17 | 「幫我開一個 repo 讓學生交作業」 | 建立模板 repo → 設定作業格式 → 提供連結 | 學生繳交作業 |
| 18 | 「幫我開一個課程組織，裡面放三份教材」 | 建立組織 → 分批建立 repo → 設定 Pages | 整學期課程管理 |
| 19 | 「每次我更新教材就自動部署到 Pages」 | 設定 GitHub Actions → push 自動觸發部署 | 自動化發布流程 |
| 20 | 「幫我找適合老師的开源專案來改編」 | 搜尋 GitHub → 分析專案 → fork 到帳號 | 開源協作入門 |

這 20 個範例涵蓋了從個人操作到團隊協作、從基礎到進階教學的所有使用場景。隨著你對 GitHub 越來越熟悉，還可以與 NotebookLM、Obsidian 等其他懶人包自由組合。

---

## 如果安裝失敗，如何重來

對 OpenCode 說：
「GitHub 懶人包執行失敗了，幫我檢查哪裡出問題，重新處理。」

OpenCode 會自動：
1. 重新執行環境檢查
2. 確認 Git 和 GitHub CLI 是否正常
3. 確認 GitHub 登入狀態
4. 找出問題並修復

如果需要完全重置 GitHub CLI 登入：
```bash
gh auth logout
```
然後重新執行步驟一（PAT 手動登入）。

---

## 常見問題

| 問題 | 解法 |
|------|------|
| `gh: command not found` | 重啟 OpenCode 桌面版，或確認安裝路徑已加入 PATH |
| `git: command not found` | 重啟 OpenCode 桌面版，Windows 需確認 Git for Windows 已安裝 |
| gh auth login 瀏覽器沒開啟或逾時 | 改用手動 PAT 方式登入（步驟一），token 設為 No expiration 即可永久有效 |
| GitHub Pages 網頁顯示 404 | 等待 1-2 分鐘再重新整理，Pages 部署需要時間 |
| push 被拒絕 | 確認 `gh auth status` 有顯示 `repo` 權限 |
| 可以同時登入多個 GitHub 帳號嗎？ | 可以。使用 `gh auth switch` 切換帳號，或用 `GH_HOST` 環境變數指定 |
| 如何確認目前登入的是哪個帳號？ | 執行 `gh api user -q .login` 查看目前使用者名稱 |
| Pages 自訂網域設定後沒生效？ | DNS 需設定 CNAME 指向 `你的帳號.github.io`，等待 DNS 傳播（最長 48 小時） |
| repo 可以從 public 轉 private 嗎？ | 可以。對 OpenCode 說：「幫我把這個 repo 設成私人」 |
| 不小心推到錯誤的分支怎麼辦？ | 執行 `git reset HEAD~1` 撤回上次 commit，再重新推送 |
| 學生要怎麼下載我的教材？ | 給學生 repo 網址，他們執行 `git clone` 即可，不需 GitHub 帳號也能下載 |
| 每次都要手動登入 gh 嗎？ | 不用。`gh auth login` 後認證資訊會存在本機，下次自動生效 |

---

## 更新紀錄

| 日期 | 版本 | 更新內容 |
|------|------|---------|
| 2026-04-04 | v0.1 | 初版 |
| 2026-04-04 | v0.2 | 加入環境檢查、復原機制、跨平台支援、測試 repo 驗證 |
| 2026-06-06 | v0.3 | 全面更新 Claude Code → OpenCode |
| 2026-06-07 | v0.4 | 補上測試 repo 的 git init/index.html 指令；移除 `build_type=workflow` 多餘參數；FAQ 新增 Pages 404 與 push 拒絕項目 |
| 2026-06-10 | v0.5 | 深度擴充：20 個使用範例（4 類）、🔁 重複執行檢查（步驟零、一）、FAQ 5→12 題 |
| 2026-06-11 | v0.6 | 登入方式改為手動 PAT（Personal Access Token），解決 `gh auth login --web` 逾時問題 |

---

## 相關連結

- [懶人包 #00：環境建置](./00-環境建置.md)
- [懶人包 #01：連接 NotebookLM](./01-連接-NotebookLM.md)
- [📋 OpenCode 懶人包索引](./README.md)
