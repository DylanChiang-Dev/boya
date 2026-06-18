# CONVENTIONS　博雅 skill 寫作公約

> 本文是新增或修改 skill 時的契約。誠信硬規見 [RULES.md](RULES.md)，版本策略與版權見 [AGENTS.md](AGENTS.md)，本文不重抄、只補「怎麼寫」。

## 1. 目錄約定

- 一個 skill 一個目錄：`skills/<name>/SKILL.md`，單檔，繁體中文優先。
- skill 名一律 kebab-case（如 `citation-verify`）。

## 2. frontmatter schema

```yaml
---
name: <kebab-case，與目錄同名>
description: <一句話功能 ＋ 觸發情境。必須寫明「當使用者說……時使用」，把觸發語寫進去，ROUTER 從這裡抽。誠信類技能須在此聲明「絕不編造／查無即標註」。>
---
```

- 僅 `name`、`description` 兩個欄位；不加版本欄位（版本走倉庫級 tag）。

## 3. SKILL.md 段落模板

依現有 12 個 skill 的共性，新 skill 至少含：

1. `# <英文名>　<中文名>`
2. `## 你的角色` — 一句話界定 agent 扮演誰、只做一件事。
3. `## 鐵律` — 編號硬規，誠信類必含「絕不編造」「查無≠偽造」「逐筆不抽樣」「留痕」。
4. `## 工作流` — 分步驟；標出「僅使用者能決定」的關卡。
5. 輸出格式 — 說明產出長什麼樣（表格／清單／報告）。

## 4. 出案例硬規

- 任一 skill **升版號前**，必須在 `examples/` 有 ≥1 篇實跑真錄（檔名 `日期-skill-案例.md`），記錄：用什麼真實材料跑、暴露了什麼坑、怎麼寫回規則。
- 對應的回歸斷言寫進 `evals/<skill>.md`（見 evals/README.md）。

## 5. 版號規則

見 [AGENTS.md](AGENTS.md) 版本策略（0.0.X／0.X.0／1.0.0），與 [RULES.md](RULES.md) 第 4 條三段式鐵律。本文不重述。

## 6. 命名規範

- skill 目錄／name：kebab-case。
- 案例檔：`YYYY-MM-DD-<skill 簡名>-<案例簡述>.md`。
- eval 檔：`evals/<skill>.md`，與 skill 同名。

## 7. 知識庫／模板／驗證日誌維護

- `knowledge/`：輕量參考卡，每份一頁量級；venue 分級嚴禁編造，未證實標「待補」。
- `templates/`：可填空骨架，非範文；結構與對應 skill 保持一致。
- `VERIFICATION.md`：skill 每次實測後補一行（版本／日期／材料／坑／example）。
