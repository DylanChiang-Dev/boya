# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 這是什麼倉庫

博雅（Boya）是面向文組／人文社科研究者的開源 AI Agent **skill 庫**，整理從讀文獻到寫論文的完整研究工作流。**它是散文式的提示工程產物，不是程式專案**：沒有編譯、沒有套件依賴、沒有自動化測試框架。每個 skill 是單一 `skills/<name>/SKILL.md`，內容為繁體中文的角色設定＋鐵律＋工作流。

整套同時以兩種 plugin 形式分發：Claude（`.claude-plugin/plugin.json`）與 Codex（`.codex-plugin/plugin.json`），兩者都指向同一個 `skills/` 目錄。

## 倉庫／書／自媒體：單一真實來源與下游關係

本專案的內容流是**單向下游**，`skills/` 倉庫是唯一真實來源（single source of truth）：

1. **持續打磨倉庫**：日常工作就是不斷打磨這個 skills 倉庫（boya）。
2. **書跟進倉庫**：作者寫的書隨時跟進倉庫；**所有標準一律以 skills 倉庫為準**，書與倉庫衝突時以倉庫為準。
3. **自媒體跟進書與倉庫**：自媒體內容依「書＋倉庫」撰寫、發佈。

方向不可逆：發現問題先回頭修倉庫，再讓書與自媒體跟進；不得反過來用書或自媒體的說法覆蓋倉庫標準。

## 沒有 build／lint／test，「測試」是手動回歸

不要找 `package.json`、`make`、`pytest`。本倉庫的品質閘門是 **evals 手動回歸**：

- 每個 skill 對應一份 `evals/<skill>.md`，是一張「MUST／MUST NOT」斷言清單。
- 改完某個 `SKILL.md` 後，依 `evals/README.md`：打開對應 eval → 讀「基準輸入」指向的 `examples/` 案例 → 取同樣輸入用當前 skill 跑一遍 → 逐條核對行為有沒有退化。
- 誠信類斷言（不編造／查無標註）是硬門檻，永遠 MUST。
- 驗證留痕寫進 `VERIFICATION.md` 的 evidence ledger（claim／source／check／result／next 五欄）。

skill 內若示範了實際指令（如 citation-verify 用 `curl` 打 Crossref／OpenAlex／Semantic Scholar），那是 skill 的工作流內容，不是本倉庫的建置流程。

## 新增或修改 skill 的固定節奏

順序是硬規（見 `GUIDE.md` §9、`CONVENTIONS.md`）：

1. **先寫 `evals/<skill>.md`**，定義 MUST / MUST NOT（eval 先行）。
2. 再寫 `skills/<skill>/SKILL.md`。
3. 若需要可填空骨架，新增 `templates/<name>.md`。
4. 接入 `ROUTER.md`（把觸發語登錄路由表）。
5. 升版號前，必須在 `examples/` 有 ≥1 篇實跑真錄（檔名 `YYYY-MM-DD-<skill簡名>-<案例>.md`），記錄用什麼真實材料跑、暴露什麼坑、怎麼寫回規則；並在 `VERIFICATION.md` 補一行。
6. 未實測前只能標 Draft；跑過真實材料、把坑寫回規則後才升 Beta／Stable。**不可未測即標 Stable。**

### SKILL.md 寫作契約

- frontmatter 僅 `name`、`description` 兩欄；**不加版本欄位**（版本走倉庫級 git tag）。
- `name` 與目錄同名，一律 kebab-case。
- `description` 必須寫明「當使用者說……時使用」把觸發語寫進去（ROUTER 從這裡抽）；誠信類技能須在此聲明「絕不編造／查無即標註」。
- SKILL.md 至少含四段：`## 你的角色`、`## 鐵律`、`## 工作流`、輸出格式。
- **分層參考料**（CONVENTIONS.md §8）：預設全部留在 SKILL.md；跨 skill 複用的料 → `knowledge/`（參考卡）或 `templates/`（骨架）；該 skill 獨佔又塞不進四段的長料 → `skills/<name>/references/`。SKILL.md **> 200 行**時強制檢查一次是否該拆。

## 誠信鐵律（最高優先，覆蓋一切便利性）

- **絕不編造**：查核類技能尤其；API 查不到 ≠ 文獻是假的，一律標「待人工確認」。
- **編造 ≠ 策展**：禁止的是「憑記憶／無來源生成事實」（刊名、影響因子、排名、字數、格式、審稿政策…）；**人工查證過的真資料可以內建或引用**（如帶來源的期刊條目），但每筆須附**來源＋查證日期**，過時效窗標「待複查」，使用者承重前提示回原始出處核對。缺欄一律留「待補」，**絕不從記憶填**。
- 不收錄任何規避 AIGC 檢測、隱藏 AI 使用痕跡的技能——本庫立場是透明協作（`RULES.md` §1）。
- 不內嵌個人憑證／API key；公開 API 一律匿名端點。
- 凡查不到、無來源、不確定的內容，一律標「待補」或「需人工確認」，不得美化成已證實。
- **工作痕跡表標記**（CONVENTIONS.md §9）：🧍你判斷／🤖AI待核／✅已查證／❓待查／🗑捨棄。標記定義只在 §9 出現一次，template 與各 skill 一律引用、不得自訂另一套。🗑 只由作者標記，skill 不得替作者把「查無」判成捨棄或造假。

## 版本策略

- 一切帶版本的產出一律**三段式、從 0.0.1 起版**；禁止 v0.1／v1.0 兩段式（`RULES.md` §4）。
- 0.0.X＝打磨輪（實測修訂一輪尾號 +1）；0.X.0＝新 skill 發布或工作流結構調整；1.0.0＝全套 skill 穩定版。
- 每版打 git tag，版本史記於 `MEMORY.md`。commit 訊息用 conventional commits（`feat:`／`fix:`／`docs:`／`test:`…），繁體中文描述。

## 多語 README 同步（記憶）

倉庫有四份 README：`README.md`（繁體中文，主檔／真實來源）、`README.zh-CN.md`、`README.en.md`、`README.ja.md`。完整規則見 `CONVENTIONS.md` §10。

- **默認只改繁體中文 `README.md`**；其他三語（zh-CN／en／ja）**不主動跟改**。
- 三語版**僅在作者明確要求時才改**，且一改就**四語一起對齊**，不單獨更新某一語。
- 三語落後屬已知狀態、非錯誤；待作者下令時批次補齊。

## 關鍵文件地圖

| 檔案 | 角色 |
|---|---|
| `AGENTS.md` | 倉庫定位、版本策略、版權模式（給 agent 的最上層約定） |
| `CONVENTIONS.md` | skill 寫作公約（目錄／frontmatter／段落模板／分層／工作痕跡表） |
| `RULES.md` | 誠信鐵律（4 條硬規） |
| `ROUTER.md` | 技能路由表：agent 接任務先查此表定位 skill；不確定先喚 `boya`（總導航入口，原 `research-roadmap`） |
| `GUIDE.md` | 使用者手冊＋維護者入口 |
| `VERIFICATION.md` | 驗證狀態表＋evidence ledger＋刻意不採用的重型設計 |
| `evals/` | 手動回歸斷言（每 skill 一份，與 skill 同名） |
| `examples/` | 實跑真錄（升版號的前置條件） |
| `knowledge/` | 跨 skill 共用的輕量參考卡（venue 分級嚴禁編造） |
| `templates/` | 可填空骨架，非範文 |
| `scripts/` | 維護輔助腳本（唯讀、只報告、非 build 依賴）；`check-skills.py`＝frontmatter 契約＋ROUTER 同步防呆檢查 |
| `docs/superpowers/` | 設計 spec 與實作 plan |

## 刻意的設計邊界（不要引入）

本庫的最高設計原則是**人類在環（human-in-the-loop）**：流程可以自動接力，但每一個「只有你能決定」的關卡都必須**硬停下來等研究者拍板**——這是 boya 與「全自動論文機」的根本分界，也是底下所有「刻意不採用」的總綱。

本庫維持「人文社科研究者可讀、可手動介入」的定位，**刻意不採用**（`VERIFICATION.md` 末節）：`_shared/` 大型共用 fragments、`manifest.yaml` 分片載入、多 agent 長跑 orchestrator、無人值守 pipeline、理工論文專用圖表／投稿包流程。`boya`（原 `research-roadmap`）是「引導式精靈」會接力喚起下一個 skill，但每到「只有你能決定」的關卡硬停等使用者拍板——這與被禁止的無人值守 pipeline 的唯一差別就是「會不會停」（即人類在環）。新增功能前先確認沒踩這條線。

## CLAUDE.md 與 AGENTS.md 雙向同步（每次必檢）

本倉庫同時存在 `CLAUDE.md`（本檔，給 Claude Code）與 `AGENTS.md`（給泛用 agent／Codex）。**每次工作開始前與結束前，都必須檢查兩者內容是否同步、雙向對齊**：

- 任一檔案修改了倉庫定位、版本策略、版權模式、誠信鐵律、寫作節奏、多語 README 策略等共通約定時，必須同步反映到另一檔，不可只改一邊。
- 兩檔定位不同、詳略可不同（AGENTS.md 精簡、CLAUDE.md 含操作細節），但**不得互相矛盾**；發現衝突先停下、向使用者指出，再決定以哪一份為準。
- 同步方向是雙向的：在 CLAUDE.md 新增的共通規則要回看 AGENTS.md 是否該補；反之亦然。
