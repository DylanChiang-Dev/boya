# MEMORY

## CHANGELOG

### v0.5.1（2026-06-27）人類在環命名＋outline-builder topic-sentence 前置

- **人類在環（human-in-the-loop）顯化**：把原「核心信念」第四條提升為全庫最高設計原則並命名。README 核心信念加分界句、第四條改名「人類在環，不是一鍵跑完」、設計原則段加總綱條；`CLAUDE.md` 設計邊界段前置一句立為「所有刻意不採用的總綱」；`AGENTS.md` 加首條核心設計原則。三處措辭對齊（CLAUDE／AGENTS 雙向同步硬規）。三語 README 未跟改（默認規則）。
- **outline-builder 0.0.3→0.0.4**：補彭思達公開筆記的「段落 message 前置（topic sentence）」缺口——原本只在逆向體檢查「首句點題」，正向搭骨架沒教。新增鐵律 6＋第 4 步擺位提醒。借自 `Master-cai/Research-Paper-Writing-Skills` 上游的彭思達筆記理念，全部自行重寫。
- 拿 silicon sampling 知識論題（接力 framework-build 人文思辨型框架）正向搭骨架實測，撞出兩個思辨型獨有坑並寫回：①讓步—反轉段讓步句不得獨佔首句（concession 冒充主題句）；②段落主題句不得覆讀章核心論點（message-first 是段落級）。
- 配套：新增 `examples/2026-06-27-outlinebuilder-silicon-sampling.md`；`evals/outline-builder.md` 補 MUST／MUST NOT＋兩條已暴露的坑；`SKILL.md` 鐵律 6＋已知陷阱 9、10；`VERIFICATION.md` 狀態表＋兩條 Evidence Ledger。README 致謝補「彭思達公開研究筆記」、實測案例補 015。版本 badge 與 plugin.json（claude／codex）0.5.0→0.5.1。
- 版本理由：outline-builder 實測修訂一輪，依 AGENTS.md 規則屬 `0.0.X` 打磨輪，倉庫版號尾號 +1。防呆 `scripts/check-skills.py`：0 ERROR／0 WARN。

### main（2026-06-23）期刊事實表・階段一 SSCI 全 10 學科群一次跑完（28 本）

- 接續第 1 批，把 SSCI 階段 10 個學科群一次跑完（群 2–10 各取 2–3 本代表刊）：政治/IR、社會、傳播、STS、IS、教育、心理、管理/組織、法律/法政，共補 23 本，連同第 1 批 5 本＝28 本，全部寫入 venues.md。
- 方法：群 2–10 由 WebSearch 自各刊**官方作者須知頁**取得事實（多含字數/摘要/關鍵詞/引用格式/AI 政策），但**未親自渲染原頁**，故狀態一律 ❓；每筆附來源 URL＋查證日期，未涵蓋欄標待補。Elsevier 刊（Information & Management、Computers & Education、CHB）抓到明確生成式 AI 政策。
- 完整度披露：✅ 親抓 2（JPART、GIQ）；❓ 搜尋待核 24；待補 2（Governance、PMR，出版商 403）。全程無一從記憶填。
- venues.md 增至 127 行（未破 200 拆檔線，暫不拆）。升 ❓→✅ 需逐本親開官網渲染核對，留待後續（可用瀏覽器分批，或外部瀏覽 agent 照任務書跑）。TSSCI／CSSCI 兩階段未啟動。

### main（2026-06-23）期刊事實表・階段一 SSCI 第 1 批（公共行政，5 本）

- 依 `plans/2026-06-23-真實期刊事實表分階段計劃.md` 啟動：venues.md 新增「期刊事實表」區塊，第 1 批公共行政 SSCI 候選 5 本（JPART／PAR／Governance／GIQ／PMR）。
- 第一輪 web_fetch：僅 **JPART**（Oxford）取得全文標 ✅；其餘 4 本出版商頁 JS 動態只得空殼。
- 第二輪外部瀏覽 agent 補抓（附來源任務書 `plans/2026-06-23-期刊事實表-外部抓取任務書.md`）：**GIQ** 由官方 ScienceDirect Guide for Authors 補齊升 ✅（摘要 ≤250、關鍵詞 1–7、APA7、highlights 3–5、雙匿名、且有明確生成式 AI 揭露政策；僅全文字數上限待補）；**PAR** 補到 ❓（8,000 詞、150 詞摘要、Chicago16 Author-Date，但來源是 PAR 編輯團隊 submission-process 頁非 Wiley 官方頁，AI/DOI 待補）；**Governance／PMR** 出版商須知頁均回 **403 Forbidden**，依鐵律整本留待補，不以搜尋摘要或他刊資料硬填。
- 結果：✅ JPART、GIQ；❓ PAR；待補 Governance、PMR。坑：Wiley／T&F 對自動化抓取回 403，需真人瀏覽器登入/開頁手動複製。索引層級（SSCI/分區）非須知頁內容，一律標「待確認」不憑記憶。
- 驗證了改後誠信鐵律的實效：策展真資料附來源＋日期可入表，但抓不到一律 ❓/待補，全程未從記憶硬填。
- 未升版號未打 tag。

### main（2026-06-23）誠信鐵律措辭收斂：區分「編造」與「策展真資料」

- 起因：評估 `brycewang-stanford/awesome-journal-skills`（1984 skill／122 逐刊深度包，把期刊作者須知與編委偏好策展成靜態庫）。釐清一個被混淆的點：**人工查證並附來源的策展期刊資料，不是「編造」**；編造專指「憑記憶／無來源生成事實」。原 venue-fit 鐵律 1／venues.md 的「**不內建**任何期刊規範」把「不准編造」（內核）與「連策展真資料都不准內建」（保守設計選擇）綁死，過度延伸。
- 措辭調整（內核不動、鬆開設計選擇那半）：CLAUDE.md 誠信鐵律新增「編造 ≠ 策展」一條、AGENTS.md 內容鐵律同步補；venue-fit 鐵律 1 由「不內建」改為「不憑記憶生成；策展真資料須附來源＋查證日期＋過時標待複查＋承重前回官網核對」，eval MUST NOT 同步；venues.md 表頭誠信句同改，候選刊表補「查證日期」欄。**絕對保留：缺欄留待補、絕不從記憶填。**
- 範圍邊界：本輪只改**規則措辭**，未建任何期刊資料庫。是否把 venues.md 養成帶來源的小型真期刊表，屬規模／維護決定，待另案；明確不採用 awesome-journal-skills 的逐刊 1984-skill 架構（撞「不讓 skill 膨脹」邊界）。
- 雙向同步：CLAUDE.md ↔ AGENTS.md 誠信段已對齊。未升版號未打 tag。

### main（2026-06-23）lit-matrix 缺口段補「強弱判準＋四類型」、self-review 補表述膨脹自查

- 借鑒一篇「從 30 篇文獻提煉研究缺口」的實務貼文（理工味、行銷文性質，只取判斷邏輯不取其 STEM 例子，亦不作為來源引用）。經比對，文章八成內容 boya 已涵蓋（lit-matrix 四欄卡／三層閱讀／對話地圖、topic-refine 三問）。**評估後刻意不開 `knowledge/` 卡也不新增 skill**：依 CONVENTIONS §8「預設留 SKILL.md，只有跨 skill 真複用才外移」，此判準目前唯一主人是 lit-matrix。
- `lit-matrix` 第 4 步缺口段：補「先判強弱（弱＝研究較少／不足；強＝說清前人解釋停在哪、那個停住懸置了什麼問題）」＋對象／方法／機制／情境四類定性（說服力遞增，文組翻譯版：機制＝因果或詮釋路徑），並保留既有盲點框法與「不腦補、標候選回查」誠信細節；新增已知陷阱 8「把『研究不足』當缺口」。eval 補兩條 MUST、一條 MUST NOT。
- `self-review` 第 3 步誠信自查補一條「缺口／貢獻表述膨脹」（局部缺口包裝成過大突破），eval 同步補一條 MUST。對應原文 gap 公式的分母 B；**刻意不採用 `G=(T×V×E)/B` 偽量化公式**（與 boya 散文鐵律風格不合、假精確）。
- frontmatter 不帶版本。**本輪標 Draft 級修訂、未升版號未打 tag**：依 CONVENTIONS §4／§5，需先拿真實文獻群實跑一遍、把坑寫回規則並補 `examples/` 真錄，才升 lit-matrix 尾號。

### main（2026-06-23）`research-roadmap` 更名為 `boya`（總導航入口）

- 把全程導航 skill `research-roadmap` 更名為 **`boya`**（與倉庫同名，作為使用者不確定時的預設入口，呼叫即 `boya`／`博雅`）。`git mv skills/research-roadmap → skills/boya`、`evals/research-roadmap.md → evals/boya.md`。
- SKILL frontmatter `name` 改 `boya`、description 改以 `boya`／`博雅`／「帶我走」為主觸發語並強化「核心職責＝主動告訴你下一步該做什麼」；eval 補一條「boya 觸發＋主動告知下一步」MUST。
- 同步：`ROUTER.md`（補「👉 從這裡開始」入口區塊＋改路由列）、四語 README（敘述／mermaid 節點／skill 表連結 `skills/boya`／實測案例 012 顯示名）、`GUIDE.md` §2、`VERIFICATION.md`（界定段＋狀態表）、`CLAUDE.md`（關鍵文件地圖＋設計邊界段）。
- 刻意保留檔名與內文不改的歷史檔（加頂部「原名」註記）：`examples/2026-06-14-researchroadmap-workflow.md`、`docs/superpowers/` 3 份 spec/plan——維持實跑真錄不竄改（誠信鐵律：真錄不竄改）。
- AGENTS.md 未引用該 skill 名，雙向同步無衝突。**版本 tag／plugin.json 版號未動，留待作者決定是否隨此改名打 tag。**

### main（2026-06-22）framework-build 0.0.2 Draft→0.1.0 Beta（人文思辨型首例，三分流覆蓋兩）

- `framework-build` 0.0.2 Draft→**0.1.0 Beta**：拿社計博士生 LLM silicon sampling 知識論課題跑**人文思辨型**首例（批判實在論主視角，四原則主義降為論點）。三分流（概念框架／理論視角／分析框架）現已實測覆蓋前兩支，eval MUST #1「先判論文類型再定錨」首次在人文思辨分支驗成立。升版號理由：新增人文思辨型分析維度分流 = 工作流結構調整，依 AGENTS.md 規則升 **0.1.0**（minor）。
- 四個人文思辨型獨有坑寫回 SKILL.md 與 Evidence Ledger：①**思辨版框架沙拉（跨哲學子域並列）**——批判實在論答認識論、四原則主義答規範倫理，兩者回答不同哲學問題，不得並列為同級主框架（鐵律 3 補第②種隱形版）；②**人文型操作化＝分析維度不是問卷**——思辨型 framework 落點是「從哪幾個面向讀爭議」（生成機制可及性／層間跌落診斷／知識責任邊界），未給維度即人文型操作化漏洞（鐵律 5 補人文思辨型分流）；③**老倫理框架跨域遷移代價**——四原則主義有確鑿支撐卻「自主原則」失去著力點（silicon sampling 無真實受訪者），與 TAM 案例同屬「✅支撐≠免遷移」但成因不同（應用場景跨域遷移 vs 技術世代遷移，鐵律 1 延伸）；④**研究問題橫跨哲學子域須步驟 2 預警**——認識論＋規範倫理並置，步驟 2 應主動標出分裂風險並給三條出路（步驟 2 補⚠️預警區塊）。
- 配套：新增 `examples/2026-06-22-framework-humanist.md` 真錄；`VERIFICATION.md` 狀態表補一行（0.1.0 Beta）、Evidence Ledger 補四條；`SKILL.md` 鐵律 1／3／5 與步驟 2 四處修訂。升 Beta 後升 Stable 條件已列：需再補政策分析型「分析框架」案例。

### main（2026-06-22）framework-build 0.0.1 Draft→0.0.2（文組實證題實測）

- `framework-build` 0.0.1 Draft→**0.0.2 實測打磨**：拿作者碩論（立委助理×生成式 AI，TAM＋科技壓力＋社會影響）跑首個**文組實證／混合方法**題，補上先前唯一案例（JASM）的國際關係偏向。接 lit-matrix 案例 002 產出、交棒 method-design 案例 006，全鏈仍收在同一本碩論。
- 三個文組獨有坑寫回 SKILL.md／eval：①**偽並列主框架**——摘要關鍵詞把三理論平鋪，一度被擺成三並列主框架＝框架沙拉隱形版，紀律＝選扣題最直接者（TAM）為唯一主框架、餘降中介（鐵律 3）；②**隱性遷移代價**——TAM 有 Davis 1989 確鑿支撐卻一度被當「拿來即用」，但 PU/PEOU 為確定性 mainframe 建、接不住生成式 AI 的不確定性，紀律＝✅ 支撐≠免遷移、理論代價欄標世代遷移（鐵律 1 延伸）；③**混合方法漏質性抓手**——一度只給可量化抓手漏了 6 場訪談那半，紀律＝每概念雙棲抓手（問卷測＋訪談追，鐵律 5）。
- 配套：新增 `examples/2026-06-22-framework-thesis.md` 真錄；eval 補第二基準輸入＋兩條 MUST／兩條 MUST NOT／三個坑；`VERIFICATION.md` 補一行。frontmatter 不帶版本（版本走倉庫 tag），未動 README badge／skill 計數（framework-build 已計入 14/15）。

### v0.5.0（2026-06-21）借鑒 frontier-tracker，新增 lit-discovery 文獻探勘

- 評估 `LiAngsong98/frontier-tracker`（自動化文獻週報 pipeline）：其無人值守 cron、`state/` 持久狀態、Python 腳本、CAS/JCR 排名匯入、Excel/Obsidian 渲染**全撞本庫設計邊界，整套架構不採用**；只取它 `scan` 階段「從研究問題撈該讀的候選文獻」這一**概念缺口**——博雅階段 2「找文獻」原本只有 `citation-verify`（查已引的），沒有 skill 幫使用者先找到那批文獻。
- 版本依 AGENTS.md 規則升 v0.5.0：`lit-discovery` 是新增 skill，屬 `0.X.0` 發布。
- 新增 `lit-discovery`（文獻探勘）**Draft**：研究問題→拆檢索策略→OpenAlex/Crossref/S2 匿名端點撈**待核候選**→相關性分層（🟢高/🟡中/⚪低/❓待人工）→交棒 citation-verify 查真偽、lit-matrix 精讀。保留 frontier-tracker 的三路 API 與分層篩選**概念**，但改寫成散文、無狀態、人在環中；不做排程、不存狀態、不匯排名。
- 新增 `evals/lit-discovery.md`、`templates/lit-search-strategy.md`、`examples/2026-06-21-litdiscovery-genai-public-sector.md`。實打 OpenAlex/Crossref 固化 5 個坑：模糊檢索噪音、高被引≠相關、同論文多 DOI 副本、OpenAlex 中文覆蓋稀疏夾離題、Crossref 回非論文 grant 記錄。
- `research-roadmap` 階段 2 由 `citation-verify` 改為 `lit-discovery`→（接力）`citation-verify`，產出物「候選清單→帶驗證狀態清單」；ROUTER 在 citation-verify 列前插入 lit-discovery；VERIFICATION 狀態表＋Evidence Ledger 各補一行（lit-discovery Draft）。四語 README skill 計數 14→15、工作流 mermaid 與 skill 清單同步接入；GUIDE 階段說明補探勘。**升 Beta 待補不同學科或中文為主的探勘案例。**

### main（2026-06-21）吸收 STORM 啟發到三個既有 skill（0.0.3）

- 評估 Stanford STORM 方法：其招牌機制「模擬 5 個專家視角生成議題認識」直撞本庫誠信鐵律與「不採無人值守 pipeline」邊界，**整套不採用、不新增 storm skill**；只取「多角度逼問題／自我體檢」骨架，落進三個既有 skill，產出全鎖成 🤖 待核問題。
- `topic-refine` 0.0.2→0.0.3：第 2 步「有界發散」加**五透鏡發散引擎**（實務者／學者／懷疑者／利益／歷史，每副只逼一個待查問題），盲點＝新穎性候選缺口。坑：利益透鏡易發無源事實、透鏡撐爆清單。
- `self-review` 0.0.2→0.0.3：四角色審完加**第 4.5 步收尾自評**（信心分數 1–10、偏誤檢查、缺席視角），信心分數與「承認邊界」鐵律綁死。坑：信心分數誘導對領域裝權威。
- `lit-matrix` 0.0.2→0.0.3：第 4 步缺口處加**盲點框法**（RQ 需要×這批未覆蓋＝缺口候選），硬防「這批沒人碰＝首創」腦補。
- 配套：三份 eval 補 MUST/MUST NOT、三篇 `examples/2026-06-21-*-storm-lens.md` 實跑真錄、`VERIFICATION.md` 狀態表＋Evidence Ledger 各補一行。ROUTER 觸發語不變、不新增路由。

### v0.4.0（2026-06-21）framework-build 理論框架定錨

- 版本號依 AGENTS.md 規則升為 v0.4.0：`framework-build` 是新增 skill，屬 `0.X.0` 發布；`v0.3.0` 保留給投稿延伸與 `venue-fit` 線。
- 新增 `framework-build`（理論框架定錨）Draft：插在 `lit-matrix` 與 `method-design` 之間，從文獻地圖攤候選框架、標庫存支撐、推薦分層，並在主框架選擇處硬 GATE 交回研究者拍板。
- 新增 `evals/framework-build.md`、`templates/framework-anchor.md`、`examples/2026-06-21-framework-jasm.md`，用日台半導體經濟安全（JASM）課題固化「不堆框架沙拉／不編承重文獻／避免紅海誤選／預防兩張皮」四個坑。
- `research-roadmap` 新增階段 4「理論框架定錨」並重編後續階段；ROUTER、GUIDE、四語 README、VERIFICATION 與 `lit-matrix`／`method-design`／`outline-builder` 交叉指引同步接入。四語 README skill 計數 13→14，版本 badge 升 0.4.0。

### main（2026-06-20）outline-builder 逆向體檢模式

- `outline-builder` 新增「逆向體檢」模式：拿成稿反推骨架，逐段套一段一意／首句點題／句關係／名詞術語清單，再扣回主線。
- `style-tune`／`self-review` 補交叉指引：讀起來鬆散或段落層級讀不順時，先回 `outline-builder` 跑逆向體檢。
- 新增 `examples/2026-06-20-outline-reverse-checkup-case.md` 與 `evals/outline-builder.md` 斷言；借自 `Master-cai/Research-Paper-Writing-Skills` 的逆向大綱＋段落流暢想法，但全部自行重寫，並固定「只診斷不代筆」「節錄級不可偽裝全文」邊界。

### main（2026-06-19）工作痕跡表整合

- 新增 `CONVENTIONS.md §9` 與 `templates/work-trace-table.md`，把「工作痕跡表」定義為跨三個誠信 skill 的統一留痕格式。
- `citation-verify`／`self-review`／`ai-disclosure` 接入痕跡表：查核狀態寫入 ✅/❓、AI 審查意見先標 🤖、揭露聲明優先據表盤點。
- 新增 `examples/2026-06-19-work-trace-table-case.md` 與三份 eval 斷言，固定邊界：查無不落 🗑，轉 🧍 是作者動作，揭露不得寫空話。

### main（2026-06-18）venue-fit 真跑升 Beta

- `venue-fit` 用作者碩士論文《生成式人工智慧使用行為之研究：以立法委員助理為例》對標《公共行政學報》真實投稿規範，新增 `examples/2026-06-18-venuefit-thesis-jpa.md`。
- 實測暴露 4 個規則點：不得補編作者須知、學位論文轉期刊先判文稿類型、AI 使用指引已成投稿硬條件、近兩年目錄契合未查即標待補。
- `VERIFICATION.md` 將 `venue-fit` 由 Draft 改 Beta；`evals/venue-fit.md` 回填基準輸入與新 MUST/MUST NOT；`skills/venue-fit/SKILL.md` 補實測狀態與學位論文轉期刊規則。

### main（2026-06-18）驗證說明補丁

- `VERIFICATION.md` 補技能驗證狀態（Draft / Beta / Stable）、Evidence Ledger 最小格式、Source Map / Action Map，以及刻意不採用 `_shared/` fragments、`manifest.yaml` 分片載入、多 agent 長跑 orchestrator 的邊界。
- 四語 README 補驗證狀態口徑；繁中、簡中、英文 README 同步補「不做重型自動化框架」設計原則。

### v0.2.0（2026-06-18）知識與模板版

- 新增 VERIFICATION.md（驗證證據鏈）、knowledge/（venue 分級方法卡＋中文學術寫作範本卡）、templates/（三種論文結構＋口試簡報骨架）。
- ROUTER／CONVENTIONS 同步收錄。

### v0.1.0（2026-06-18）結構版

- 更名為博雅（Boya），四語 README 與 repo slug 同步。
- 新增 ROUTER.md（機器路由）、CONVENTIONS.md（寫作公約）、evals/（12 份回歸基準）、.claude-plugin/.codex-plugin（安裝 manifest）。
- 12 個 skill 全部完成並實測（0.0.2 打磨輪）。

### v0.0.2

- 三個新 skill 0.0.1→0.0.2 打磨輪；12 skill 全部實測。

### v0.0.1

- 技能庫初版，citation-verify 等首批 skill。

## 歷史記錄

- 2026-06-12：倉庫建立。首個技能 citation-verify v0.1（引用查核，Crossref/OpenAlex/Semantic Scholar 三源）。技能路線圖覆蓋完整研究工作流，見 README 清單。
- 2026-06-12：第一輪實測（5 筆混合清單：真DOI/真無DOI/虛構/中文/專書）。發現四個陷阱並修入 SKILL.md：模糊檢索永遠有結果、重複DOI登記（Attention Is All You Need 2025年副本）、書評假冒專書、OpenAlex 要用 title.search 不用 search。citation-verify 升 0.0.1（版本制改為 0.0.X：打磨輪尾號+1、新技能中號+1、全套 skill 穩定版定 1.0.0）。
- 2026-06-12：0.0.2 —— 第二輪實測（用戶碩士論文真實參考文獻 47 筆）。新增規則：DataCite 回退（arXiv DOI 在 Crossref 必 404）、區域註冊機構前綴判 ❓、DOI 指錯人反查更正、URL 內嵌 DOI 抽取、重複條目偵測、格式異常區、線上先行 ±1 容忍、拆名陷阱。實戰戰果：抓到 3 筆 DOI 貼錯、1 筆作者拆名錯誤、11 筆缺作者的格式異常條目、2 筆重複。
- 2026-06-12：新增 examples/ 實測案例 001——作者碩論 47 筆查核全記錄＋公開勘誤表，README 掛連結。定位：工具案例＋學術勘誤雙身份；日後作者有個人頁時勘誤可遷移、案例留存。
- 2026-06-13：新增技能 lit-matrix v0.0.1 初版（A5.1，讀文獻到綜述階段）。範疇：單篇四欄精讀筆記（主張／證據／方法／可挑戰處）、跨篇對照矩陣、綜述對話地圖；定位三層閱讀法第二層；鐵律含「只整理作者已寫出的、不腦補、不判真偽（與 citation-verify 分工）、不替代回源、摘要不可信三情況」。**未實測**，待 A5.2 拿真實文獻批跑打磨；本版不打 release tag。
- 2026-06-13：全庫在地用語對齊——AGENTS.md「文科生」→「文組生」（與台灣在地化一致）。
- 2026-06-13：lit-matrix 0.0.1→**0.0.2**（A5.2 打磨輪）。實測：取碩論 5 篇核心文獻、以「公部門 AI 使用行為」為錨跑一次（僅摘要級演練，內容取自 S2／OpenAlex）。新增 5 條規則：①內容層級三級（全文／僅摘要／**僅題名**）；②內容多源嘗試但抓不到是常態（標僅題名級、退回求全文）；③主題判定看文獻本身不看引用語境（Wu&Lin 被當科技採用引、實為品牌忠誠）；④異質語料先分群＋允許 N/A；⑤誠實處理「非同一對話」、依 RQ 重定位角色。新增 examples/ 案例 002。
- 2026-06-13：新增技能 **self-review v0.0.1 初版**（A9.1，自我審查階段）。一桌審稿人（方法論／領域／魔鬼代言人／主編）輪審＋誠信自查（虛構引用/數據-結論斷裂/統計誤用/過度宣稱）＋意見分級（必改/可辯/誤讀）。鐵律：不討好/不放水、可操作回指段落、只診斷不代筆、誠信問題置頂、承認領域邊界。與 citation-verify／lit-matrix 串用。**未實測**，待 A9.2 拿真實草稿跑；本版不打 release tag。
- 2026-06-13：self-review 0.0.1→**0.0.2**（A9.2 打磨輪）。實測：審一篇教學稿（非實證）。3 條打磨：①**文稿類型偵測**（第 1 步表，按實證/理論/綜述/教學文調整四角色——非實證稿方法論/領域角色說「不適用」而非硬擠假意見）；②主編查「證據—宣稱規模相稱」（開場上百篇、示範 5 篇的落差）；③新增陷阱「放過絕對宣稱」（魔鬼代言人專挑「AI 永遠做不到 X」類信念句）。新增 examples/案例 003；當場抓到兩個可改點。限制：方法論/領域角色待用實證論文草稿再壓測。
- 2026-06-14：新增技能 **defense-prep v0.0.1→0.0.2**（A10.1+A10.2，修訂定稿與口試階段）。三件事：論文→簡報骨架、分層出難題（澄清/方法/理論/貢獻/延伸陷阱）、答詢策略（含非母語英文框架）。鐵律：只出題教策略不代答、題扎根真實弱點、模擬器非預言機。A10.2 打磨：模擬作者碩論前期稿口試，3 條規則——①論文階段判定（前期稿 vs 完整論文，與 self-review 文稿類型同源）②同一弱點多層輪問要歸組③質性研究必出可推論性題。案例 004。**四個 skill 至此全用在同一本碩論上**（查引用→理文獻→審論證→練口試）＝工作流收口。
- 2026-06-14：新增技能 **topic-refine v0.0.1→0.0.2**（A3.1+A3.2，磨題目階段）。蘇格拉底式磨題：問題意識→有界發散→三問收斂（有人答過/答得動/誰在乎）→指導教授模擬→一頁研究問題簡報。鐵律：不替用戶定題、不當答案機、可行性誠實。A3.2 打磨（磨「對兩岸關係有興趣」）3 條：發散要有界、狠問封閉/敏感領域資料可得性（日台非官方安全＝track-two 接觸不到）、不替學生編問題意識。案例 005。
- 2026-06-14：新增技能 **method-design v0.0.1→0.0.2**（A6.1+A6.2，研究設計階段）。研究設計：方法地圖→起草訪談/問卷＋人工校準→角色扮演預訪談→編碼建議（詮釋留人）→統計謬誤核驗→倫理。鐵律：方法跟研究問題走、AI起草人校準、模擬答案非資料、詮釋不外包。A6.2 打磨（檢視碩論質性設計）3 條：對象分層要想清楚（跨群體別一鍋烩）、AI 扮受訪者太乖（測題不測混亂）、小圈子/菁英去識別化特別難。案例 006。
- 2026-06-14：新增技能 **outline-builder v0.0.1→0.0.2**（A7.1+A7.2，論文骨架階段）。論文骨架：選結構模式（IMRaD/綜述型/思辨型/政策型，不預設 IMRaD）→長出「每章回答什麼」的大綱→段落論證鏈 claim-evidence-warrant（專補最易省略的 warrant 推理橋）→查重疊章節。鐵律：骨架必須是你的、不套單一模板、盯緊 warrant。A7.2 打磨（碩論骨架）：前置章節重複膨脹、完整性幻覺（齊全≠論證線）、warrant 缺席＝理科腦病根。案例 007。
- 2026-06-14：新增技能 **style-tune v0.0.1→0.0.2**（A8.1+A8.2，寫初稿階段）。聲音校準：餵舊文讓 AI 學你的文風→段落級潤稿（收緊/換語氣/重寫/補warrant，守整篇代寫紅線）→中文學術 AI 腔識別清單（總之/首先其次/萬能讚詞/空洞排比/正確的廢話）→改稿停止條件。鐵律：先骨架再潤、整篇代寫是紅線、校準是讓AI學你非你學AI。A8.2 打磨（掃碩論 AI 腔）：AI 腔的專業偽裝（整齊≠好捨不得刪）、整篇AI腔時段落級潤救不了要重寫。案例 008。**至此 7 個 skill 全部 0.0.2，6 個用在同一本碩論。**
- 2026-06-14：新增技能 **ai-disclosure v0.0.1→0.0.2**（A11.1+A11.2，AI 使用揭露階段）。AI 使用揭露：盤點使用→抄襲/代寫/輔助三分法→按目標機構格式（引原文）生成誠實具體聲明→留痕自證→師生溝通。立場（＝本庫 RULES 第 1 條）：透明協作非隱藏，不協助規避偵測/淡化使用。A11.2 打磨（重度 AI 協作聲明）：重度使用時 AI 不敢說（透明不因程度高而隱瞞）、產出類型決定聲明形式。案例 009。**🎉 九個核心 skill 全部完成、皆 0.0.2。**
- 2026-06-14：新增**三個 skill（皆 0.0.1 草稿、未實測）**，把技能庫從「逐階段九個」補成「九核心＋兩收尾＋一導航＝十二個」。①`cite-format`——引用格式整理（APA/Chicago/MLA 轉換與全文統一、隨文引註↔文末清單一一對應抓孤兒、缺欄位標註不編造）；只管格式不驗真偽，與 citation-verify 分工。②`abstract-bilingual`——中英雙語摘要（從定稿濃縮中文摘要＋英文摘要按英文慣例重寫非直譯＋中英關鍵詞）；鐵律「只濃縮不新增、數字人名逐一核對、缺漏標註不編造」。③`research-roadmap`——全流程導航**書脊**（判斷使用者在哪一階段、該喚哪個 skill、哪些關卡只有他能決定、何時過關）；鐵律「只導航不代跑、不跳關、每步把方向盤交回、不替做研究判斷」，本身不做苦工只串起其餘十一個 skill。三者皆**未實測**，本版不打 release tag，待後續拿真實稿打磨升 0.0.2。
- 2026-06-14：三新 skill **0.0.1→0.0.2 打磨輪**（拿作者碩論與完整工作流實測，案例 010–012）。**abstract-bilingual**（案例 010，碩論五要素生中英摘要）：①原稿官方關鍵詞中英本身不對齊（中5英6、英多 social influence）→ 標註請作者定、不自行增刪；②「顯著」是統計詞、混合方法要分清來自量化還是質性才照搬；③混合方法摘要要寫出「量化+質性如何整合」非兩段並列。**cite-format**（案例 011，碩論參考文獻排 APA7）：①「先驗後排」被坐實（未查核清單＝錯資料的漂亮包裝，Davis 缺作者/Thomas-Backer 拆名例）；②重複判定要看標題、非作者+年（同作者同年不同篇要 2014a/2014b 不可合併）；③API 查不到的類型（專書/章節/學位論文/研討會）＝cite-format 主場兼最易錯區（citation-verify 幫不上、缺欄位最多）。**research-roadmap**（案例 012，導航完整研究工作流）：①最大退化＝「流程朗讀機」（要依產出物倒推真實位置、非按線性順序）；②「讀完/寫完」是自我感覺、要用「能不能交出 X 產出物」核實；③階段順序依論文類型不同（綜述/思辨/政策型的階段 4–6 形態不一樣）。順手修 roadmap 總表殘留「AI 預審」→「模擬審查」。**🎉 十二個 skill 全部 0.0.2、皆實測打磨。**
- 2026-06-14：**README 重寫**（徽章＋工作流 mermaid 圖＋12 skill 分組＋12 案例表＋star-history 趨勢圖＋補 Supervisor-Skills 致謝），已 push。
- 2026-06-14：**事實校正——清除虛構研究對象**。前幾輪自主稿把作者碩論對象誤寫成「立委、助理、縣市首長、局處首長、基層公務員**五層級**」「十幾個人」「全體公務員」（純屬編造）。依國圖事實卡校正全倉：真實＝對象**立法委員＋立委助理兩種角色**（核心立委助理）、**混合方法（212 問卷＋6 質性訪談）**。改動：案例 004（口試考題）、案例 006（method-design 檢視），及編進 SKILL 的教學例（method-design 對象分層例改中性「高階決策者 vs 第一線執行人員」、預訪談角色去公務員化、去識別化例留「立委助理」；defense-prep 可推論性例改「6 位、立委+助理兩角色」）。案例 003 的「公部門基層×AI×負面效應」屬文獻層廣義缺口（非虛構對象名單）、且為 6/13 審查記錄，判定保留。教訓：自主輪缺真錨時填的 placeholder 會擴散進 skill，需用權威事實卡反向清掃。
- 2026-06-18：新增 `README.zh-CN.md` 簡體中文入口，面向中國大陸高校文科／人文社科碩博生，補充知網、萬方、維普、國家哲學社會科學文獻中心、GB/T 7714、答辯、導師、AI 使用聲明等語境說明；`README.md` 增加雙語入口。12 個 `SKILL.md` 仍維持單套繁體正文，避免雙份維護。
- 2026-06-18：公開名稱調整為「人文社科 AI 研究技能庫／技能库」，保留「文組生／文科生的 AI 研究工作流」作為副標，避免變成泛用 AI 研究工具庫，強化文科與人文社科定位。
- 2026-06-18：新增 `README.en.md` 英文完整入口與 `README.ja.md` 日文輕量入口；四個 README 互鏈。多語策略仍只翻譯公開入口，不複製 12 個 skill 正文，避免多份維護。
- 2026-06-18：新增技能 **venue-fit v0.0.1 草稿（未實測）**（0.3.0「學位論文→期刊投稿」延伸第一個 skill）。投稿對標：按「索引/語種（SSCI/TSSCI/CSSCI）× 量化/質性」兩軸，拿定稿對標目標刊真實作者須知，輸出 must-fix/should-fix/待補 三級差距。鐵律：不內建/不生成任何期刊清單/IF/排名/須知，查不到標待補；對標≠代寫；質性不硬套 IMRaD；引用/揭露/摘要分別指向 cite-format/ai-disclosure/abstract-bilingual 不重做。附 templates/venue-fit-checklist.md、evals/venue-fit.md（基準輸入待補）、ROUTER 路由。設計見 plans/2026-06-18-博雅0.3.0投稿延伸設計.md。**未實測，不打 tag**；README（md/zh-CN/en/ja）skill 數 12→13 與升 Beta 留待真實案例實測後。
- 2026-06-18：新增 `GUIDE.md` 繁中使用手冊，補足 README 與 ROUTER 之間的「人怎麼開始用」入口：說明適合對象、安裝後第一步、按研究階段選 skill、完整工作流、templates/knowledge/evals 用法、venue-fit Draft 狀態、誠信紅線、常見情境與維護者入口；`README.md` 增加一行手冊連結。暫不同步多語 README。
- 2026-06-18：重寫 `README.md` 首屏推廣文案，明確面向文組／人文社科研究者截圖傳播：主標改為「博雅 Boya」、副標改為「給文組／人文社科研究者的 AI 論文工作流」，提前呈現「AI 做苦工，你做判斷」與三個使用場景（題目太大、文獻太亂、初稿要交）。
- 2026-06-20：**research-roadmap 升級「引導式精靈」（guided dispatcher）**——從「只指路、要使用者自己一個一個手動喚 skill」改為「自動接力喚起下一個 skill、一步一個 skill 帶著走，但每到『只有你能決定』的關卡硬停等使用者拍板才放行」。借 superpowers 的自報家門＋硬跳轉＋checkpoint 機制，全收斂在 research-roadmap 一個檔，**12 個下游 skill 不動**（架構選 roadmap 中心制）。改動：SKILL.md（description／鐵律 2 細分「接力腳手架可、代做研究判斷禁」／新增鐵律 7「gate 必停不得擅自接力跳關」／新增「接力協定」段／陷阱 1 改寫＋新增陷阱 5「接力失速」）、evals/research-roadmap.md（補 gate 必停等斷言）、VERIFICATION.md（補界定句「引導式精靈≠無人值守 pipeline，差別在遇 gate 必停」）、GUIDE/README×4 描述同步。設計見 `docs/superpowers/specs/2026-06-20-roadmap-guided-dispatcher-design.md`。**例子與升版號後補**（依 CONVENTIONS §4 需先真跑一遍引導流程留 example，待使用者另一台機器實跑後補；本輪不打 tag）。README skill 計數維持 13。
