# VERIFICATION　博雅驗證證據鏈

> 每個 skill 都拿真實研究材料跑過、把暴露的坑寫回規則。本表是過去實測的留痕證據；未來回歸斷言見 [evals/](evals/)。
> 資料源：[examples/](examples/) 與 git 歷史，不新增實測、只彙總已發生的。

## 驗證狀態

| 狀態 | 意義 | 進入條件 |
|---|---|---|
| Stable | 已穩定 | 已用真實材料完整跑過，暴露的坑已寫回 `SKILL.md`，且有 example 或 eval 可回看 |
| Beta | 可用但仍在磨 | 已有實測或局部案例，但邊界條件、地區語境或資料類型仍需要更多回歸 |
| Draft | 草稿 | 只有設計或少量試跑，尚未形成可依賴的實測證據鏈 |

目前 12 個 Boya skills 均列為 **Stable**：不是因為「不會錯」，而是因為每個 skill 都至少經過一輪真實材料實測，並把失敗模式寫回規則。未來新增 skill 一律先從 Draft 或 Beta 開始，不可未測即標 Stable。

- **venue-fit**（0.3.0 新增）：目前 **Draft**——僅有設計與 SKILL.md，尚未拿真實投稿材料跑過。升 Beta 條件：在 `examples/` 補 >=1 篇實跑真錄並校準 `evals/venue-fit.md`。

## Evidence Ledger 最小格式

每次新增 example、修訂 skill 規則、或宣稱某個坑已被驗證時，至少留下這五欄。它是輕量證據帳，不是大型自動化研究系統。

| 欄位 | 必填內容 |
|---|---|
| claim | 正在驗證的判斷或規則，例如「API 查無不等於文獻不存在」 |
| source | 證據來源：example、原始材料、公開資料庫、文件路徑或 commit |
| check | 實際做了什麼核對，例如 DOI 反查、資料庫比對、段落回源、格式對照 |
| result | 通過／不通過／不確定；不確定時必須說明缺口 |
| next | 下一步：寫回 `SKILL.md`、補 eval、標待人工、或暫不採納 |

建議用這個 Markdown 骨架：

```md
### YYYY-MM-DD · <skill> · <短標題>

- claim:
- source:
- check:
- result:
- next:
```

## Source Map 與 Action Map

當任務涉及多份材料、審稿意見、口試問題、或長篇修改時，建議額外加兩張表，避免 AI 把來源、評論與行動混在一起。

**Source Map**

| source_id | 來源 | 範圍 | 用途 |
|---|---|---|---|
| S1 | 文件路徑、URL、資料庫紀錄或訪談材料 | 頁碼、段落、條目或時間戳 | 用來支持哪個 claim |

**Action Map**

| action_id | 來源 | 要做的事 | 狀態 |
|---|---|---|---|
| A1 | S1 / reviewer comment / defense question | 修改、查核、補資料、刪除或保留 | done / pending / rejected |

## 刻意不採用的重型設計

Boya 維持人文社科研究者可讀、可手動介入的技能庫，不把每個 skill 改成大型自動化框架。因此目前不採用：

- `_shared/` 大型共用 fragments。
- `manifest.yaml` 分片載入系統。
- 多 agent 長跑 orchestrator。
- 無人值守研究 pipeline。
- Nature／理工論文專用的圖表、專利、投稿包流程。

若未來某個 skill 明顯過長，才考慮把少量共用材料外移到 `knowledge/` 或 `templates/`，但 `SKILL.md` 仍保留可直接閱讀的核心規則。

| skill | 版本 | 實測日期 | 用的真實材料 | 暴露的坑 | 對應 example |
|---|---|---|---|---|---|
| citation-verify | 0.0.2 | 2026-06-12 | 作者碩論 47 筆參考文獻 | 查無≠偽造（中文文獻誤判風險） | examples/2026-06-12-master-thesis-case.md |
| lit-matrix | 0.0.2 | 2026-06-13 | 碩論 5 篇異質文獻 | 引用語境≠主題、異質語料硬併 | examples/2026-06-13-litmatrix-thesis-litreview.md |
| self-review | 0.0.2 | 2026-06-13 | 本書教學章稿 | 文稿類型錯配、證據-宣稱規模不相稱、絕對宣稱 | examples/2026-06-13-selfreview-teaching-chapter.md |
| topic-refine | 0.0.2 | 2026-06-14 | 兩岸關係題 | 可行性紅燈（資料閉門） | examples/2026-06-14-topicrefine-cross-strait.md |
| method-design | 0.0.2 | 2026-06-14 | 碩論研究設計 | 對象分層不清、AI 扮受訪者太乖 | examples/2026-06-14-methoddesign-thesis.md |
| outline-builder | 0.0.2 | 2026-06-14 | 碩論骨架 | 完整性幻覺、warrant 缺席 | examples/2026-06-14-outlinebuilder-thesis.md |
| style-tune | 0.0.2 | 2026-06-14 | 碩論緒論 | AI 腔的專業偽裝 | examples/2026-06-14-styletune-thesis.md |
| defense-prep | 0.0.2 | 2026-06-14 | 碩論口試模擬 | 論文階段誤判、漏質性可推論性 | examples/2026-06-14-defenseprep-thesis.md |
| ai-disclosure | 0.0.2 | 2026-06-14 | 重度 AI 協作聲明 | 重度使用時 AI 不敢說 | examples/2026-06-14-aidisclosure-heavy-ai-use.md |
| abstract-bilingual | 0.0.2 | 2026-06-14 | 碩論中英摘要 | 關鍵詞中英不對齊、「顯著」當統計詞照搬 | examples/2026-06-14-abstractbilingual-thesis.md |
| cite-format | 0.0.2 | 2026-06-14 | 碩論參考文獻 | 先排後驗＝錯資料的漂亮包裝 | examples/2026-06-14-citeformat-thesis.md |
| research-roadmap | 0.0.2 | 2026-06-14 | 完整研究工作流 | 退化成目錄朗讀機 | examples/2026-06-14-researchroadmap-workflow.md |
