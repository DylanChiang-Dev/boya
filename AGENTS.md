# AGENTS

本倉庫是面向文組研究者的開源 AI Agent skill 庫，整理從讀文獻到寫論文的完整研究工作流。

- 核心設計原則：**人類在環（human-in-the-loop）**——流程可自動接力，但每個「只有你能決定」的關卡都必須硬停等研究者拍板；這是 boya 與「全自動論文機」的根本分界，也是「刻意不採用多 agent 長跑 orchestrator／無人值守 pipeline」的總綱。
- 內容流（單一真實來源）：`skills/` 倉庫是唯一真實來源；持續打磨倉庫 → 書隨時跟進倉庫（所有標準以倉庫為準）→ 自媒體依書與倉庫撰寫發佈。方向單向下游，發現問題先修倉庫再讓下游跟進，不得用書／自媒體覆蓋倉庫標準。
- 技能規範：單文件 `skills/<name>/SKILL.md`，繁體中文優先，frontmatter 含 name 與 description。
- 寫作公約：新增或修改 skill 前先讀 [CONVENTIONS.md](CONVENTIONS.md)（目錄／frontmatter／段落模板／出案例硬規／命名）。
- 內容鐵律：絕不編造（查核類技能尤其），所有工作流原創撰寫，思路來源在 README 致謝具名。**編造指「憑記憶／無來源生成事實」；人工查證過的真資料（如帶來源的期刊條目）可內建或引用，但每筆須附來源＋查證日期、過時標「待複查」、承重前回原始出處核對，缺欄留「待補」絕不從記憶填。**
- 版本策略：0.0.X＝打磨輪（實測修訂一輪尾號+1）；0.X.0＝新 skill 發布或工作流結構調整；1.0.0＝全套 skill 穩定版。每版打 git tag，版本史記於 MEMORY.md。
- 版權模式：倉庫內全部內容 MIT（版權人 Dylan Chiang／蔣濤，外部貢獻按 inbound=outbound 同樣以 MIT 授入）；專案名稱與品牌不在 MIT 授權範圍內。
- 多語 README 同步：默認只改繁體中文 `README.md`（主檔）；`README.zh-CN.md`／`README.en.md`／`README.ja.md` 僅在作者明確要求時才改，且一改即四語一起對齊，不單獨更新某一語。完整規則見 [CONVENTIONS.md](CONVENTIONS.md) §10。
