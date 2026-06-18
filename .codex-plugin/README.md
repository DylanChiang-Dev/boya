# Codex 安裝說明

Codex 可透過 plugin manifest 載入本庫，也可直接讀取 skills 目錄。一般本機使用以「直接安裝 skills」最簡單；plugin／marketplace 適合團隊分發或需要在 Codex plugin directory 裡管理時使用。

## 作為 plugin

本庫提供 `.codex-plugin/plugin.json`，其中 `"skills": "./skills/"` 指向倉庫根目錄的 12 個 skill。

若要透過 Codex plugin marketplace 分發，請把本倉庫作為 plugin source，並在 repo 或個人 marketplace 中加入 `boya` entry。這不是單一 skill 安裝；它會把 `skills/` 下的 12 個 Boya skills 作為一組提供。

## 直接安裝 skills

若只想在本機使用 skills，可把 `skills/*` 複製到以下任一位置：

- repo scope：`$REPO_ROOT/.agents/skills/`
- user scope：`$HOME/.agents/skills/`

Codex 會讀取每個 `SKILL.md` 的 `name` 與 `description`，並在任務符合描述時載入完整 skill。
