# Kozaneba

[西尾泰和](西尾泰和.md) が開発した **デジタル文房具**。紙の [KJ法](../concepts/KJ法とLLM.md) を電子化したもの。線引き、ズーム、コピー・バックアップ機能を持ち、アイデアの空間配置・グループ化・関連付けに使う。

## LENCHI でのこの本の位置づけ

- [第二章](../chapters/第二章.md) のもうひとつの主役。「紙の KJ法 → Kozaneba」という著者の道具の進化を語る軸。
- 本プロジェクトでは Day1〜Day7 で講演資料の構造化に活用（[Day7](../timeline/Day7.md) は特に Kozaneba 中心）。
- 著者は LLM の出力（テキスト断片）を Kozaneba に流し込み、空間配置で構造化する運用を実験している。

## 既知の限界

- マインドマップの解像度を [GPT-4o](ChatGPT.md) で読み取らせる試みは成功していない。視覚的構造を LLM に渡すワークフローは未解決（[KJ法とLLM](../concepts/KJ法とLLM.md)）。

## 隣接システムとの関係（[Day 13](../timeline/Day13.md) 追記）

2026 年に隣接する 2 つのシステムが浮上した：

- **[MindTrellis](MindTrellis.md)**（外部研究、arXiv:2604.23129）— AI と人間が同じ知識グラフを共同編集。意味関係を明示することに強い
- **[ConnectingDots](../concepts/ConnectingDots.md)**（西尾自身の設計）— 事実・関係・解釈・物語・表示の 4 層分離。Kozaneba は **その View の一種** として位置づけ可能

GPT による三者の整理：

> ConnectingDots = データモデル / 思想 / 事実と解釈の分離
> MindTrellis = 文書から Dots と Relations を育てる AI 機構
> Kozaneba = Dots, Relations, Stories を触る空間 UI

Kozaneba の独自性は「**前言語的な構造化**」に強い点。MindTrellis の知識グラフは「意味関係」を明示したがるが、KJ法的な配置は「**まだ言語化できない近さ**」も扱える。ConnectingDots の 5 週間アクションプラン（[Day 13](../timeline/Day13.md)）では、Kozaneba は第 4 週で **Story 編集の作業 View** として接続予定。

## 出典

- raw: `LENCHI_第二章 デジタルツールで知的生産を加速する`、`LENCHI_Day1時点のKozaneba`、`LENCHI_Day3時点のKozaneba`、`LENCHI_Day7`、`LLMを使いこなすエンジニアの知的生産術(講演資料)`、`2026-05-03-mindtrellis-connectingdots-GPT.txt`
