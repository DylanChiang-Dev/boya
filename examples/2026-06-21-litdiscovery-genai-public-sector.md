# 實測案例：用 lit-discovery 探勘「公部門／立法幕僚使用生成式 AI」

> 2026-06-21，`lit-discovery` 0.5.0 Draft 的首跑真錄。延用本庫錨定的碩論主題（公部門人員生成式 AI 使用行為，核心對象立法委員助理），實際打 OpenAlex／Crossref 匿名端點撈候選，測四件事：候選是否全來自真實命中、中文題會不會被誠實標 ❓、弱相關會不會被偷砍、模糊檢索的噪音長什麼樣。
>
> 邊界：本 skill 只撈候選、不判真偽（那是 citation-verify）、不精讀（那是 lit-matrix）。以下候選全部 🤖 待核。

## 研究問題與檢索策略

- 研究問題：公部門人員（核心：立法委員助理）使用生成式 AI 的行為與影響。
- 核心概念：`生成式 AI` × `公部門/政府人員` × `使用行為/採用`。
- 同義詞：generative AI / GenAI；public sector / government / civil servant；adoption / use behavior。
- 排除：純技術實作（只要使用行為層面）。

## 實跑命中（真實 API 回應節錄）

**OpenAlex `title.search:generative artificial intelligence public sector`（被引排序）**

| 候選（縮略） | 年 | 相關層級 | 命中／備註 |
|---|---|---|---|
| Evaluating public sector employee perceptions towards AI...（DOI 10.1177/01655515241293775） | 2024 | 🟢 高 | 對象＝公部門員工、變項＝對 AI 的認知，直接命中 |
| Strategies for the Use of AI in the Public Sector（10.31553/kpsr...） | 2024 | 🟡 中 | 公部門 AI 策略，偏政策非個人使用行為 |
| Application of generative AI solutions in Lithuanian public...（DOI None） | 2026 | 🟡 中 | 切題但 OpenAlex 無 DOI → 書目待 citation-verify 補 |

**OpenAlex `title.search:generative AI government`（被引排序）**

| 候選（縮略） | 年 | 相關層級 | 命中／備註 |
|---|---|---|---|
| Synergizing Generative AI and Cybersecurity...（10.36227/techrxiv.23968809） | 2023 | ⚪ 低 | **被引 61 卻離題**（cybersecurity）＝模糊檢索噪音 |
| 〃 同篇 techrxiv `.v1` 副本（...23968809.v1） | 2023 | — | **同論文第二個 DOI**，去重併一筆、標可能重複/預印本 |
| Automating Government Report Generation: A Generative AI Approach（10.1145/3691352） | 2024 | 🟡 中 | 政府報告自動生成，場景相近可借鑒 |

**Crossref `query.bibliographic=generative AI public sector adoption`**

| 候選（縮略） | 年 | 相關層級 | 命中／備註 |
|---|---|---|---|
| Exploring the Future of Public Sector Work: Generative AI Adoption...（10.2139/ssrn.5258102） | 2025 | 🟢 高 | 直接命中，惟 SSRN 預印本→真偽/版本待查 |
| （無標題條目，DOI 10.3030/101159214） | ? | — | **EU grant 記錄、非論文**，剔除不列為候選 |

**OpenAlex 中文關鍵詞 `title.search:立法委員助理`**

- count=2：①「立法委員個人助理之研究」（2003，題對但前生成式 AI 時代）；②一筆完全離題的日文論文（子どもの知る権利／AID）。
- 判定：中文題覆蓋稀疏且夾噪音 → 標 `❓待人工`，導向華藝／國圖「台灣博碩士論文知識加值系統」。**未撈到 ≠ 沒人做過。**

## 四個打磨發現（feed 回 SKILL.md 與 eval）

1. **模糊檢索的噪音是真的**：cybersecurity 那筆被引 61 卻離題，坐實「撈到≠相關、高被引≠切題」。寫進鐵律與已知陷阱 1–2：相關性分層是人工掃，不是真偽判定。
2. **同論文多 DOI 副本要去重**：techrxiv `.v1`/base 同篇兩個 DOI；SSRN 預印本版本問題。寫進第 3 步去重：併一筆、標可能重複/預印本，書目交 citation-verify。
3. **中文覆蓋稀疏且夾離題**：「立法委員助理」count=2 還混進日文。固化鐵律 2：中文題一律 ❓待人工＋人工管道，撈不到不得腦補「首創」。
4. **Crossref 會回非論文記錄**：EU grant（10.3030）混進結果。寫進已知陷阱 5：命中≠期刊論文，類型存疑就標，剔除非論文。

## 方法與聲明

- 工具：本倉庫 `lit-discovery`（0.5.0 Draft 首跑）。命中為 2026-06-21 實際 curl OpenAlex／Crossref 匿名端點所得節錄。
- 本 skill 只撈候選、按相關性分層，**不判真偽**：以上每一筆書目是否正確、是否真實存在，須交 `citation-verify` 逐筆查；決定要讀的再交 `lit-matrix`。
- 紅線守住：候選全來自真實 API 命中，無一筆靠記憶捏造；中文查無標 ❓ 不硬湊；弱相關（cybersecurity 那筆）保留標 ⚪ 低、未靜默丟棄；🗑 留給作者。
