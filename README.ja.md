言語: [繁體中文](README.md) | [简体中文](README.zh-CN.md) | [English](README.en.md) | [日本語](README.ja.md)

<div align="center">

# Boya（博雅）· 人文・社会科学のための AI 研究スキル集

### 文系研究者の AI 研究ワークフロー

**コードを書かない文系・人文社会科学系の研究者のための Claude Code / Codex skill 集です。テーマ設定、文献確認、文献読解、研究設計、アウトライン作成、初稿、自己レビュー、仕上げ、発表・口頭試問準備までを支援します。**

<br/>

[![Stars](https://img.shields.io/github/stars/DylanChiang-Dev/boya?style=for-the-badge&logo=github&color=ffca28)](https://github.com/DylanChiang-Dev/boya/stargazers)
[![Forks](https://img.shields.io/github/forks/DylanChiang-Dev/boya?style=for-the-badge&logo=github&color=42a5f5)](https://github.com/DylanChiang-Dev/boya/network/members)
[![License: MIT](https://img.shields.io/badge/License-MIT-4caf50?style=for-the-badge)](LICENSE)
[![Skills](https://img.shields.io/badge/skills-12-7e57c2?style=for-the-badge)](#12-個の-skill)
[![version](https://img.shields.io/badge/version-0.2.0-7e57c2?style=for-the-badge)](MEMORY.md)
[![日本語](https://img.shields.io/badge/日本語-Lightweight-e4002b?style=for-the-badge)](#)

</div>

---

> このリポジトリは、人文・社会科学系の研究者が AI エージェントを研究補助として使うための skill 集です。12 個の skill は、研究テーマを絞る、引用文献を確認する、文献を読む、研究方法を設計する、論文の骨格を作る、文章を整える、自己レビューする、引用形式を整える、AI 利用を説明する、といった作業を担当します。

中心にある考え方は単純です。**AI に作業を任せても、研究判断は人間が持つ。** AI は文献を探す手がかりを出し、表を作り、質問を投げ、形式を整えることはできます。しかし、研究課題、方法、解釈、最終的な主張は研究者自身が決める必要があります。

## 対象

- 人文・社会科学系の学部生、大学院生、研究者。
- 修士論文、博士論文、投稿論文、授業レポート、研究計画書を書いている人。
- AI を使いたいが、丸投げや代筆にはしたくない人。
- 汎用プロンプト集ではなく、研究プロセス全体の流れがほしい人。

## 基本方針

- **作業は AI、判断は人間。** 検索、確認、表作成、形式整理、模擬質問は AI に任せられます。研究上の判断は人間が行います。
- **引用は必ず原典に戻る。** skill は文献の存在確認を助けますが、その文献が自分の主張を本当に支えるかは原文で確認します。
- **隠すのではなく説明する。** AI 利用は、必要に応じて正直に説明できる形で残します。
- **一発自動生成ではない。** このリポジトリは「論文自動生成機」ではなく、人間が進行方向を決めるためのワークフローです。

## 12 個の skill

同じ 12 個の skill を、繁体字中国語、簡体字中国語、英語、日本語、または混在した研究資料に対して使えます。skill 本文は 1 セットだけを維持し、言語別 README は入口として用意しています。

`VERIFICATION.md` には実測の証拠、`knowledge/` には venue 分類と中文学術文体の参考カード、`templates/` には論文構成と口頭試問スライドの穴埋め骨格があります。

| skill | 内容 | 段階 |
|---|---|---|
| [`topic-refine`](skills/topic-refine) | 研究テーマを絞り込む。問いの意識、発散、収束、実現可能性、指導教員風の問い直しを扱います。 | テーマ |
| [`citation-verify`](skills/citation-verify) | Crossref / OpenAlex / Semantic Scholar などで文献の存在確認を補助し、DOI ミス、著者名の分割、疑わしい引用を見つけます。 | 文献確認 |
| [`lit-matrix`](skills/lit-matrix) | 文献を主張・証拠・方法・反論可能性に分けて読み、比較表やレビュー地図を作ります。 | 文献読解 |
| [`method-design`](skills/method-design) | インタビュー、質問紙、質的分析、簡単な統計確認など、研究方法の設計を補助します。 | 研究設計 |
| [`outline-builder`](skills/outline-builder) | 論文構成、章立て、段落ごとの claim-evidence-warrant を整理します。 | アウトライン |
| [`style-tune`](skills/style-tune) | 自分の文体に合わせた段落単位の修正、AI っぽい学術文体の検出を行います。 | 初稿 |
| [`self-review`](skills/self-review) | 方法論、分野、批判的読者、編集者の視点から原稿を模擬レビューします。 | 自己レビュー |
| [`defense-prep`](skills/defense-prep) | 口頭試問、発表、質疑応答の準備を補助します。 | 発表・試問 |
| [`ai-disclosure`](skills/ai-disclosure) | AI 利用の範囲を整理し、大学・授業・学会・投稿先の方針に合わせた説明文の作成を補助します。 | AI 利用説明 |
| [`cite-format`](skills/cite-format) | APA / Chicago / MLA または指定テンプレートに合わせて参考文献形式を整えます。真偽確認は別作業です。 | 形式 |
| [`abstract-bilingual`](skills/abstract-bilingual) | 中文・英文を中心に、完成稿から要旨とキーワードを整理します。数字や固有名詞は人間が確認します。 | 要旨 |
| [`research-roadmap`](skills/research-roadmap) | 今どの段階にいるか、次にどの skill を使うべきか、何が完了条件かを案内します。 | ナビゲーション |

## インストール

### Codex に手動インストール

Codex は `.agents/skills` と `~/.agents/skills` を読みます。各 skill ディレクトリには `SKILL.md` が入っています。

```bash
git clone https://github.com/DylanChiang-Dev/boya.git

# 全体インストール
mkdir -p ~/.agents/skills
cp -r boya/skills/* ~/.agents/skills/

# または現在のプロジェクトだけにインストール
mkdir -p .agents/skills
cp -r boya/skills/* .agents/skills/
```

### Claude Code に手動インストール

```bash
git clone https://github.com/DylanChiang-Dev/boya.git

# 全体インストール
mkdir -p ~/.claude/skills
cp -r boya/skills/* ~/.claude/skills/

# または現在のプロジェクトだけにインストール
mkdir -p .claude/skills
cp -r boya/skills/* .claude/skills/
```

インストール後は、`$citation-verify` のように明示的に呼び出すか、「この参考文献が実在するか確認して」のように自然言語で依頼できます。

## 日本語環境で使うときの注意

この README は軽量な日本語入口です。日本の大学院制度、各大学の様式、学会・投稿規定、研究倫理方針までを網羅するものではありません。

### 文献確認

`citation-verify` は Crossref / OpenAlex / Semantic Scholar などの公開 API を使います。英語論文や DOI のある文献には有効ですが、日本語文献、書籍、紀要、学位論文、政府資料、新聞記事、アーカイブ資料は API だけでは確認できないことがあります。

**API で見つからないことは、文献が存在しないことを意味しません。** 日本語資料では、必要に応じて次のような経路で原典確認してください。

- CiNii Research
- J-STAGE
- IRDB
- 大学図書館の蔵書検索
- 各大学の機関リポジトリ
- 国立国会図書館サーチ
- 出版社ページ
- 政府・自治体・省庁の公式ページ

### 引用形式

引用形式の優先順位は次のように考えてください。

```text
大学・研究科・授業の指定様式 > 指導教員の指示 > 投稿先の規定 > 一般的なスタイル
```

`cite-format` は形式整理を補助しますが、大学や投稿先の正式ルールを自動で知っているわけではありません。使うときは、指定様式、投稿規定、または正しいサンプルを agent に渡してください。

### AI 利用説明

大学、授業、学会、投稿先によって AI 利用の扱いは異なり、今後も変わります。`ai-disclosure` を使うときは、最新の方針文を一緒に渡してください。

このリポジトリは、AI 利用を正直に説明するための補助をします。AI 利用を隠す、検出を回避する、代筆を軽い校正のように見せる、といった用途は扱いません。

## ライセンス

MIT License. Copyright Dylan Chiang.

バージョン履歴は [`MEMORY.md`](MEMORY.md#changelog) にあります。謝辞と詳細な背景は [English README](README.en.md) または [繁體中文 README](README.md) を参照してください。
