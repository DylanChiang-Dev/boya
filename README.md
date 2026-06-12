# Liberal Arts Research Skills

**文科生的 AI 研究技能庫** — 給不會寫程式的研究者的 Claude Code 技能集，覆蓋「讀文獻到寫論文」的完整工作流。

A Claude Code skill collection for liberal-arts students and researchers — the full workflow from literature to thesis, no coding required. Chinese-first (Traditional).

> 本倉庫是《文科生的 AI 研究工作流》（撰寫中）的隨書開源技能庫：書裡每一章的操作，這裡都有對應的、裝上就能跑的技能。技能先行發布、隨書稿迭代。

## 理念

- **AI 是副駕駛，不是機長**：技能處理苦工（檢索、查核、格式、模擬提問），研究問題、方法選擇與詮釋永遠是你的。
- **凡引用必回源**：工具只證明文獻存在，不證明它支持你的論點。
- **透明而非遮掩**：所有技能鼓勵留痕與 AI 使用揭露，目標是品質，不是隱藏協作事實。

## 安裝

把技能目錄複製到你的專案或全域技能目錄即可：

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
| `citation-verify` | ✅ v0.1 | 引用查核：用 Crossref / OpenAlex / Semantic Scholar 公開 API 驗證參考文獻是否真實存在 | 第 4 章 |
| `topic-refine` | 🚧 規劃中 | 蘇格拉底式磨題：把模糊興趣磨成可研究的問題 | 第 3 章 |
| `lit-matrix` | 🚧 規劃中 | 文獻矩陣：批量精讀筆記與綜述對話地圖 | 第 5 章 |
| `method-design` | 🚧 規劃中 | 研究設計：方法選擇、訪談大綱與問卷的預訪談模擬 | 第 6 章 |
| `outline-builder` | 🚧 規劃中 | 論文骨架：從研究問題與文獻地圖長出章節大綱 | 第 7 章 |
| `style-tune` | 🚧 規劃中 | 聲音校準：用你的舊文校準文風，識別 AI 腔 | 第 8 章 |
| `self-review` | 🚧 規劃中 | 自我審查：多角色模擬審稿（方法論／領域／魔鬼代言人） | 第 9 章 |
| `defense-prep` | 🚧 規劃中 | 口試準備：論文壓縮成簡報、模擬口試委員出難題 | 第 10 章 |
| `ai-disclosure` | 🚧 規劃中 | AI 使用揭露：按學校／期刊格式生成使用聲明 | 第 11 章 |

## 設計原則

- **單文件技能**：每個技能一個 `SKILL.md`，看得懂、改得動，歡迎 fork 改造成你的領域版本。
- **不編造**：所有技能內建「查無即標註、不確定即說明」的硬規則。
- **中文優先**：為華語文科研究場景設計（含台灣學術環境的引用與政策語境）。

## 授權與致謝

MIT License — 可自由使用、修改、再發布（含商用），保留版權聲明即可。

工作流思路受以下公開項目與研究啟發，特此致謝：[academic-research-skills](https://github.com/Imbad0202/academic-research-skills)（誠信閘門與引用核驗理念）、The AI Scientist（Lu et al., *Nature* 2026）所揭示的全自動化失敗模式、Zhao et al.（2026）對幻覺引用的大規模實證。本倉庫所有內容為原創撰寫。
