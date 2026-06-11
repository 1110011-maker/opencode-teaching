# OpenCode 十節課教案 — 懶人包索引

> 國中資訊科技（七～九年級）| 每節 45 分鐘 | AI 助教 OpenCode

---

## 教案文件

| 檔案 | 說明 |
|------|------|
| [教師大綱](./OpenCode-十節課教案-教師大綱.md) | 每課教學目標、時間分配、評量方式總表 |
| [教師手冊](./OpenCode-十節課教案-教師手冊.md) | 完整教學引導（含老師引導語、卡關處理） |
| [學生講義](./OpenCode-十節課教案-學生講義.md) | 學生用活動手冊（含檢查點、記錄欄位） |

## 懶人包

| 編號 | 檔案 | 用途 | 對應課次 |
|------|------|------|---------|
| #00 | [環境建置](./00-環境建置.md) | 安裝 Git、gh、uv、winget | 第 4–5 課 |
| #01 | [連接 NotebookLM](./01-連接-NotebookLM.md) | 安裝 nlm、登入 Google、MCP 設定 | 第 6–8 課 |
| #08 | [安裝 FB 頻道摘要 Skill](./08-安裝FB頻道摘要Skill.md) | 安裝 SKILL.md、測試互動 | 第 9 課 |

### 規劃中

| 編號 | 檔案 | 用途 |
|------|------|------|
| #02 | [連接 GitHub](./02-連接-GitHub.md) | GitHub 帳號登入與推送流程 |
| #03 | [建立第二大腦（Obsidian）](./03-建立第二大腦-Obsidian.md) | Obsidian 安裝與基礎筆記 |
| #04 | [第二大腦設定指南](./04-第二大腦設定指南.md) | Obsidian 進階設定與最佳實踐 |
| #07 | [開工/收工/初始化技能](./07-開工收工初始化技能.md) | 每日工作流程自動化 Skill |

## 輔助資源

| 檔案 | 說明 |
|------|------|
| [新手安裝指南](./00-新手安裝指南.md) | 從零開始安裝 OpenCode（含 API Key 申請） |
| [AGENTS.md](./AGENTS.md) | 專案說明與開發注意事項 |

## 懶人包依賴關係

```
#00 環境建置 → #01 連接 NotebookLM → #08 FB 頻道摘要 Skill
```

完成 #00 後才能進行 #01，完成 #01 後才能進行 #08。

## 技術棧

- **OS**: Windows 10+（主要），支援 macOS/Linux
- **Shell**: PowerShell 5.1（Windows），bash（macOS/Linux）
- **工具**: Git, GitHub CLI (gh), uv, winget
- **MCP**: notebooklm-mcp-cli (nlm)
- **AI 平台**: OpenCode, OpenRouter (API Key), Google NotebookLM
