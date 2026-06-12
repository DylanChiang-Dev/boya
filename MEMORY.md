# MEMORY

- 2026-06-12：倉庫建立。首個技能 citation-verify v0.1（引用查核，Crossref/OpenAlex/Semantic Scholar 三源）。技能路線圖對應書稿 11 章，見 README 清單。
- 2026-06-12：第一輪實測（5 筆混合清單：真DOI/真無DOI/虛構/中文/專書）。發現四個陷阱並修入 SKILL.md：模糊檢索永遠有結果、重複DOI登記（Attention Is All You Need 2025年副本）、書評假冒專書、OpenAlex 要用 title.search 不用 search。citation-verify 升 0.0.1（版本制改為 0.0.X：打磨輪尾號+1、新技能中號+1、書出版定 1.0.0）。
- 2026-06-12：0.0.2 —— 第二輪實測（用戶碩士論文真實參考文獻 47 筆）。新增規則：DataCite 回退（arXiv DOI 在 Crossref 必 404）、區域註冊機構前綴判 ❓、DOI 指錯人反查更正、URL 內嵌 DOI 抽取、重複條目偵測、格式異常區、線上先行 ±1 容忍、拆名陷阱。實戰戰果：抓到 3 筆 DOI 貼錯、1 筆作者拆名錯誤、11 筆缺作者的格式異常條目、2 筆重複。
