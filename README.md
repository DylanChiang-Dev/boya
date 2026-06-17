<div align="center">

# 文組生的 AI 研究工作流

### Liberal Arts Research Skills

**給不會寫程式的研究者的 Claude Code / Codex 技能庫——從讀文獻到寫論文，一條人工帶路的工作流。**

*A Claude Code / Codex skill collection for liberal-arts researchers — the full path from literature to thesis, no coding required.*

<br/>

[![Stars](https://img.shields.io/github/stars/DylanChiang-Dev/liberal-arts-research-skills?style=for-the-badge&logo=github&color=ffca28)](https://github.com/DylanChiang-Dev/liberal-arts-research-skills/stargazers)
[![Forks](https://img.shields.io/github/forks/DylanChiang-Dev/liberal-arts-research-skills?style=for-the-badge&logo=github&color=42a5f5)](https://github.com/DylanChiang-Dev/liberal-arts-research-skills/network/members)
[![License: MIT](https://img.shields.io/badge/License-MIT-4caf50?style=for-the-badge)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-12-7e57c2?style=for-the-badge)](#十二個-skill)
[![繁體中文](https://img.shields.io/badge/繁體中文-First-e4002b?style=for-the-badge)](#)

</div>

---

> 本倉庫是《**文組生的 AI 研究工作流——用 Claude Code 從讀文獻到寫論文，不會寫程式也做得到**》（撰寫中）的隨書開源技能庫。書裡每一章的操作，這裡都有對應的、裝上就能跑的 skill；技能先行發布、隨書稿迭代。它同時是書內 QR code 指向的**線上更新頁**。

一句話講清楚這個倉庫在做什麼：**把指導教授腦子裡那種「看三篇文獻就知道這題能不能做」的判斷，盡量拆成明白的規則與提問，寫成你隨時叫得動的流程。** 它縮小資訊差，但不替你做研究——

## 🧭 核心信念

> ### AI 是副駕駛，不是機長。

- **苦工外包，判斷自留。** skill 處理檢索、查核、格式、模擬提問；研究問題、方法選擇與詮釋，永遠是你的。
- **凡引用必回源。** skill 只證明文獻存在，不證明它支持你的論點。
- **透明而非遮掩。** 全部 skill 鼓勵留痕與 AI 使用揭露，目標是品質，不是隱藏協作事實。
- **人工帶路，不是一鍵跑完。** 這不是全自動論文機（那正是本書批評的東西）——每一步 AI 幹活、你握方向盤。

## 🗺️ 工作流地圖

從一個念頭到一篇可以投出去的論文，十二個 skill 各守一段，`research-roadmap` 在最上層導航：

```mermaid
flowchart TD
    Start([💡 一個念頭]) --> S1[磨題目<br/>topic-refine]
    S1 --> S2[找文獻<br/>citation-verify]
    S2 --> S3[讀文獻<br/>lit-matrix]
    S3 --> S4[研究設計<br/>method-design]
    S4 --> S5[搭骨架<br/>outline-builder]
    S5 --> S6[寫初稿<br/>style-tune]
    S6 --> S7[自我審查<br/>self-review]
    S7 --> S8[定稿・口試<br/>defense-prep · cite-format · abstract-bilingual]
    S8 --> S9[倫理揭露<br/>ai-disclosure]
    S9 --> End([📄 可投出去的論文])
    RM{{research-roadmap<br/>全程導航書脊}} -.隨時定位你在哪.-> S1
    RM -.該喚哪個 skill.-> S5
    RM -.哪些只有你能決定.-> S9
```

## 📦 十二個 skill

> **九個核心**（逐階段工作）＋ **兩個收尾**（定稿階段）＋ **一個導航**（書脊）＝ **十二個**，皆 `0.0.2`、皆以作者真實研究材料實測打磨。

### 核心 · 一階段一個

| skill | 功能 | 章 |
|---|---|---|
| [`topic-refine`](skills/topic-refine) | 蘇格拉底式磨題：問題意識 → 有界發散 → 三問收斂（新／可行／誰在乎）→ 指導教授模擬 → 一頁研究問題簡報；只追問不給答案 | 3 |
| [`citation-verify`](skills/citation-verify) | 引用查核：用 Crossref / OpenAlex / Semantic Scholar 公開 API 驗證參考文獻是否**真實存在**，抓 DOI 貼錯、拆名、虛構引用 | 4 |
| [`lit-matrix`](skills/lit-matrix) | 文獻精讀與矩陣：單篇四欄筆記（主張／證據／方法／可挑戰處）、跨篇對照矩陣、綜述對話地圖 | 5 |
| [`method-design`](skills/method-design) | 研究設計：方法地圖、起草訪談大綱／問卷＋人工校準、角色扮演預訪談、編碼建議（詮釋留你）、統計謬誤核驗 | 6 |
| [`outline-builder`](skills/outline-builder) | 論文骨架：選結構模式（IMRaD／綜述／思辨／政策）、長出大綱、段落論證鏈 claim–evidence–warrant（專補推理橋） | 7 |
| [`style-tune`](skills/style-tune) | 聲音校準：用舊文讓 AI 學你的文風、段落級潤稿（守整篇代寫紅線）、中文學術 AI 腔識別清單 | 8 |
| [`self-review`](skills/self-review) | 自我審查（**模擬審查**）：一桌審稿人（方法論／領域／魔鬼代言人／主編）輪審＋誠信自查＋意見分級（必改／可辯／誤讀） | 9 |
| [`defense-prep`](skills/defense-prep) | 口試準備：論文 → 簡報骨架、分層出難題（澄清／方法／理論／貢獻／陷阱）、答詢策略（含英文） | 10 |
| [`ai-disclosure`](skills/ai-disclosure) | AI 使用揭露：盤點使用 → 抄襲／代寫／輔助三分法 → 按目標機構格式生成誠實具體聲明 → 留痕自證 | 11 |

### 收尾 · 定稿階段

| skill | 功能 | 章 |
|---|---|---|
| [`cite-format`](skills/cite-format) | 引用格式整理：APA／Chicago／MLA 轉換與全文統一、隨文引註↔文末清單一一對應（抓孤兒）、缺欄位標註不編造；**只管格式不驗真偽** | 4・10 |
| [`abstract-bilingual`](skills/abstract-bilingual) | 中英雙語摘要：從定稿濃縮中文摘要＋英文摘要（按英文慣例重寫、非逐字翻譯）＋中英關鍵詞；只濃縮不新增、數字逐一核對 | 8・10 |

### 導航 · 書脊

| skill | 功能 | 章 |
|---|---|---|
| [`research-roadmap`](skills/research-roadmap) | 全流程導航：判斷你在哪一階段、該喚哪個 skill、哪些關卡只有你能決定、何時過關；**只導航不代跑**，串起其餘十一個 | 序・1 |

## 🚀 安裝

### 方式一：一句話交給 Claude Code 或 Codex（推薦，不需要會終端機）

打開 Claude Code 或 Codex，把這句話貼進去：

```
幫我從 https://github.com/DylanChiang-Dev/liberal-arts-research-skills 安裝 citation-verify 技能
```

它會自己下載倉庫、把技能檔放到正確位置、回報裝了什麼。預設裝到當前專案；想讓所有專案都能用，句尾加「**到全域技能目錄**」。新裝的 skill 通常在下次啟動 Claude Code 或 Codex 時生效。

> 💡 2026-06 實測通過；過程中它要動你的檔案時會先徵求同意，看一眼再按確認。想一次裝全部，把上面那句的 `citation-verify` 換成「**所有技能**」。

### 方式二：手動複製到 Codex（會用終端機的話）

Codex 讀取 `.agents/skills` 與 `~/.agents/skills`。每個 skill 目錄只要包含 `SKILL.md` 就能被辨識。

```bash
git clone https://github.com/DylanChiang-Dev/liberal-arts-research-skills.git

# 全域安裝（所有專案可用）
mkdir -p ~/.agents/skills
cp -r liberal-arts-research-skills/skills/* ~/.agents/skills/

# 或只裝到當前專案
mkdir -p .agents/skills
cp -r liberal-arts-research-skills/skills/* .agents/skills/
```

裝好後在 Codex 裡可用 `$citation-verify` 這類明確呼叫，也可以直接用自然語言觸發，例如：「幫我查核這份參考文獻的真偽」。

### 方式三：手動複製到 Claude Code（會用終端機的話）

```bash
git clone https://github.com/DylanChiang-Dev/liberal-arts-research-skills.git

# 全域安裝（所有專案可用）
mkdir -p ~/.claude/skills
cp -r liberal-arts-research-skills/skills/* ~/.claude/skills/

# 或只裝到當前專案
mkdir -p .claude/skills
cp -r liberal-arts-research-skills/skills/* .claude/skills/
```

裝好後在 Claude Code 裡直接用自然語言觸發，例如：「幫我查核這份參考文獻的真偽」。

## 🔬 實測案例

每個 skill 都拿**真實研究材料**跑過、把暴露的坑寫回規則——多數用在作者自己那本碩士論文上，是一條工作流全鏈的真實示範。

| # | 案例 | 一句話戰果 |
|---|---|---|
| 001 | [citation-verify 查作者碩論](examples/2026-06-12-master-thesis-case.md) | 47 筆全量查核，抓到 **3 筆 DOI 貼錯**、1 筆拆名、11 筆出處不全，附公開勘誤表 |
| 002 | [lit-matrix 整理碩論文獻](examples/2026-06-13-litmatrix-thesis-litreview.md) | 5 篇異質文獻分群做矩陣；暴露「引用語境≠主題／異質語料分群」 |
| 003 | [self-review 審本書第 5 章](examples/2026-06-13-selfreview-book-ch5.md) | 暴露「文稿類型錯配／證據-宣稱規模不相稱／絕對宣稱」 |
| 004 | [defense-prep 模擬碩論口試](examples/2026-06-14-defenseprep-thesis.md) | 分層出真考題；暴露「論文階段誤判／漏質性可推論性」 |
| 005 | [topic-refine 磨「兩岸關係」題](examples/2026-06-14-topicrefine-cross-strait.md) | 在「日台非官方安全」踩出可行性紅燈（資料閉門），示範換做法保住問題 |
| 006 | [method-design 檢視碩論設計](examples/2026-06-14-methoddesign-thesis.md) | 暴露「對象分層要想清楚／AI 扮受訪者太乖」 |
| 007 | [outline-builder 檢視碩論骨架](examples/2026-06-14-outlinebuilder-thesis.md) | 暴露「完整性幻覺（齊全≠論證線）／warrant 缺席」 |
| 008 | [style-tune 掃碩論 AI 腔](examples/2026-06-14-styletune-thesis.md) | 一本談 GenAI 的論文緒論本身讀起來像 AI 生成；暴露「AI 腔的專業偽裝」 |
| 009 | [ai-disclosure 為「這本書」生成聲明](examples/2026-06-14-aidisclosure-thisbook.md) | 一本用 AI 寫的書揭露自己怎麼用 AI；暴露「重度使用時 AI 不敢說」 |
| 010 | [abstract-bilingual 生碩論中英摘要](examples/2026-06-14-abstractbilingual-thesis.md) | 抓到「官方關鍵詞中英本身不對齊／『顯著』是統計詞別照搬」 |
| 011 | [cite-format 排碩論參考文獻](examples/2026-06-14-citeformat-thesis.md) | 坐實「先驗後排——未查核清單＝錯資料的漂亮包裝」 |
| 012 | [research-roadmap 導航本書工作流](examples/2026-06-14-researchroadmap-bookworkflow.md) | 抓到最大退化「目錄朗讀機」——要依產出物倒推、非按章節順序 |

## 🧱 設計原則

- **單文件 skill**：每個 skill 一個 `SKILL.md`，看得懂、改得動，歡迎 fork 改造成你的領域版本。
- **不編造**：所有 skill 內建「查無即標註、不確定即說明」的硬規則。
- **用—磨—寫**：每個 skill 都先拿真實材料跑、把坑寫回規則，才升版號——不閉門造框架。
- **中文優先**：為華語人文社科研究場景設計（含台灣學術環境的引用與政策語境）。

## ⭐ Star 趨勢

如果這個倉庫幫到你，按顆星——讓更多卡在論文裡、身邊沒有人可商量的文組生看到它。

[![Star History Chart](https://api.star-history.com/svg?repos=DylanChiang-Dev/liberal-arts-research-skills&type=Date)](https://star-history.com/#DylanChiang-Dev/liberal-arts-research-skills&Date)

## 🏷️ 版本策略

| 版號 | 意義 |
|---|---|
| `0.0.X` | 打磨輪——任何 skill 經實測修訂一輪，尾號 +1 |
| `0.X.0` | 新 skill 發布——對應書稿一章完成，中號 +1 |
| `1.0.0` | 《文組生的 AI 研究工作流》出版日定版 |

每個版本打 git tag，CHANGELOG 記在 [`MEMORY.md`](MEMORY.md)。

## 📄 授權與致謝

**MIT License**（版權人 Dylan Chiang 蔣濤）——可自由使用、修改、再發布（含商用），保留版權聲明即可。

工作流思路受以下公開項目與研究啟發，特此致謝：

- [**academic-research-skills**](https://github.com/Imbad0202/academic-research-skills)（ARS）—— 誠信閘門與引用核驗的理念方向
- [**Supervisor-Skills**](https://github.com/HKUSTDial/Supervisor-Skills)（HKUST）—— 把導師判斷編碼成 skill、投稿前自審（模擬審查）的立意
- **The AI Scientist**（Lu et al., 2024, [arXiv:2408.06292](https://arxiv.org/abs/2408.06292), Sakana AI）—— 全自動化研究的失敗模式
- **Zhao et al.（2026）** —— 對幻覺引用的大規模實證

> 僅借鑑理念方向與問題意識，**提示語、結構、案例全部原創自製**——零內容轉述、不抄 prompt、不用截圖。這份分寸，正是本書談的學術誠信。
