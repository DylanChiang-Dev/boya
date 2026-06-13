# Liberal Arts Research Skills

**文組生的 AI 研究技能庫** — 給不會寫程式的研究者的 Claude Code 技能集，覆蓋「讀文獻到寫論文」的完整工作流。

A Claude Code skill collection for liberal-arts students and researchers — the full workflow from literature to thesis, no coding required. Chinese-first (Traditional).

> 本倉庫是《文組生的 AI 研究工作流》（撰寫中）的隨書開源技能庫：書裡每一章的操作，這裡都有對應的、裝上就能跑的技能。技能先行發布、隨書稿迭代。

## 理念

- **AI 是副駕駛，不是機長**：技能處理苦工（檢索、查核、格式、模擬提問），研究問題、方法選擇與詮釋永遠是你的。
- **凡引用必回源**：工具只證明文獻存在，不證明它支持你的論點。
- **透明而非遮掩**：所有技能鼓勵留痕與 AI 使用揭露，目標是品質，不是隱藏協作事實。

## 安裝

**方式一：一句話交給 Claude Code（推薦，不需要會終端機）**

打開 Claude Code，把這句話貼進去：

```
幫我從 https://github.com/DylanChiang-Dev/liberal-arts-research-skills 安裝 citation-verify 技能
```

它會自己下載倉庫、把技能檔放到正確位置、跟你回報裝了什麼。預設裝到當前專案；想讓所有專案都能用，句尾加「到全域技能目錄」。新裝的技能在下次啟動 Claude Code 時生效。（2026-06 實測通過；過程中它要動你的檔案時會先徵求同意，看一眼再按確認。）

**方式二：手動複製（會用終端機的話）**

```bash
# 全域安裝（所有專案可用）
git clone https://github.com/DylanChiang-Dev/liberal-arts-research-skills.git
cp -r liberal-arts-research-skills/skills/* ~/.claude/skills/

# 或只裝到當前專案
cp -r liberal-arts-research-skills/skills/* .claude/skills/
```

裝好後在 Claude Code 裡直接用自然語言觸發，例如：「幫我查核這份參考文獻的真偽」。

## 技能清單

| 技能 | 狀態 | 功能 | 對應書章 |
|---|---|---|---|
| `citation-verify` | ✅ 0.0.2 | 引用查核：用 Crossref / OpenAlex / Semantic Scholar 公開 API 驗證參考文獻是否真實存在 | 第 4 章 |
| `topic-refine` | ✅ 0.0.2 | 蘇格拉底式磨題：問題意識→有界發散→三問收斂（新/可行/誰在乎）→指導教授模擬→一頁研究問題簡報；只追問不給答案 | 第 3 章 |
| `lit-matrix` | ✅ 0.0.2 | 文獻精讀與矩陣：單篇四欄筆記（主張／證據／方法／可挑戰處）、跨篇對照矩陣、綜述對話地圖；與 citation-verify 分工（它驗真偽、本技能理內容） | 第 5 章 |
| `method-design` | ✅ 0.0.2 | 研究設計：方法地圖（訪談/問卷/個案/論述分析）、起草訪談大綱問卷＋人工校準引導題、角色扮演預訪談測題、編碼建議（詮釋留你）、統計謬誤核驗、倫理 | 第 6 章 |
| `outline-builder` | ✅ 0.0.2 | 論文骨架：選結構模式（IMRaD/綜述/思辨/政策）、長出「每章回答什麼」的大綱、段落論證鏈 claim–evidence–warrant（專補推理橋）、查重疊章節 | 第 7 章 |
| `style-tune` | ✅ 0.0.2 | 聲音校準：用舊文讓 AI 學你的文風、段落級潤稿（守整篇代寫紅線）、中文學術 AI 腔識別清單、改稿停止條件 | 第 8 章 |
| `self-review` | ✅ 0.0.2 | 自我審查：一桌審稿人（方法論／領域／魔鬼代言人／主編）輪審＋誠信自查＋意見分級（必改／可辯／誤讀）；按文稿類型調整角色；與 citation-verify、lit-matrix 串用 | 第 9 章 |
| `defense-prep` | ✅ 0.0.2 | 口試準備：論文→簡報骨架、分層出難題（澄清/方法/理論/貢獻/陷阱）、答詢策略（含英文）；判論文階段；與 self-review 串用 | 第 10 章 |
| `ai-disclosure` | 🚧 規劃中 | AI 使用揭露：按學校／期刊格式生成使用聲明 | 第 11 章 |

## 實測案例

- [案例 001：作者用 citation-verify 查核自己的碩士論文](examples/2026-06-12-master-thesis-case.md) — 47 筆全量查核，抓到 3 筆 DOI 貼錯、1 筆作者拆名、11 筆出處不全，附公開勘誤表。
- [案例 002：用 lit-matrix 整理碩論核心文獻](examples/2026-06-13-litmatrix-thesis-litreview.md) — 5 篇異質文獻分群做矩陣與對話地圖；暴露「內容層級三級／多源仍抓不到摘要／引用語境≠主題／異質語料分群」等真實限制，回饋升 0.0.2。
- [案例 003：用 self-review 審本書自己的第 5 章](examples/2026-06-13-selfreview-book-ch5.md) — 一桌審稿人審一篇教學文，暴露「文稿類型錯配／證據-宣稱規模不相稱／絕對宣稱」三盲點，回饋升 0.0.2；並當場抓到第 5 章兩個可改點。
- [案例 004：用 defense-prep 模擬作者碩論的口試](examples/2026-06-14-defenseprep-thesis.md) — 分層出真考題（方法/理論/陷阱/可推論性），暴露「論文階段誤判／弱點多層輪問要歸組／漏質性可推論性」三盲點，回饋升 0.0.2。四個 skill 至此全用在同一本論文：查引用→理文獻→審論證→練口試。
- [案例 005：用 topic-refine 把「對兩岸關係有興趣」磨成研究問題](examples/2026-06-14-topicrefine-cross-strait.md) — 有界發散→三問盤問，在「日台非官方安全合作」上踩出可行性紅燈（資料閉門），示範如何換做法保住問題；暴露「發散失控／封閉領域可得性／替學生編問題意識」三盲點，回饋升 0.0.2。
- [案例 006：用 method-design 檢視作者碩論研究設計](examples/2026-06-14-methoddesign-thesis.md) — 質性訪談五層級對象，暴露「對象分層要想清楚／AI 扮受訪者太乖／小圈子去識別化難」三盲點，回饋升 0.0.2。
- [案例 007：用 outline-builder 檢視作者碩論骨架](examples/2026-06-14-outlinebuilder-thesis.md) — 暴露「前置章節重複膨脹／完整性幻覺（齊全≠有論證線）／warrant 缺席（理科腦寫1+1=2不寫如何=2）」，回饋升 0.0.2。
- [案例 008：用 style-tune 掃作者碩論的 AI 腔](examples/2026-06-14-styletune-thesis.md) — 一本談 GenAI 的論文緒論本身讀起來像 AI 生成（總之收尾/萬能讚詞/空洞排比）；暴露「AI 腔的專業偽裝（整齊≠好）／整篇 AI 腔時段落級潤救不了」，回饋升 0.0.2。

## 設計原則

- **單文件技能**：每個技能一個 `SKILL.md`，看得懂、改得動，歡迎 fork 改造成你的領域版本。
- **不編造**：所有技能內建「查無即標註、不確定即說明」的硬規則。
- **中文優先**：為華語人文社科研究場景設計（含台灣學術環境的引用與政策語境）。

## 版本策略

- **0.0.X**：打磨輪——任何技能經實測修訂一輪，尾號 +1（當前 0.0.1）
- **0.X.0**：新技能發布——對應書稿一章完成，中號 +1
- **1.0.0**：《文組生的 AI 研究工作流》出版日定版

每個版本打 git tag，CHANGELOG 記在 `MEMORY.md`。

## 授權與致謝

MIT License — 可自由使用、修改、再發布（含商用），保留版權聲明即可。

工作流思路受以下公開項目與研究啟發，特此致謝：[academic-research-skills](https://github.com/Imbad0202/academic-research-skills)（誠信閘門與引用核驗理念）、The AI Scientist（Lu et al., 2024, arXiv:2408.06292，Sakana AI）所揭示的全自動化失敗模式、Zhao et al.（2026）對幻覺引用的大規模實證。本倉庫所有內容為原創撰寫。
