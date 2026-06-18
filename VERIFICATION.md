# VERIFICATION　博雅驗證證據鏈

> 每個 skill 都拿真實研究材料跑過、把暴露的坑寫回規則。本表是過去實測的留痕證據；未來回歸斷言見 [evals/](evals/)。
> 資料源：[examples/](examples/) 與 git 歷史，不新增實測、只彙總已發生的。

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
