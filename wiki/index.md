# Index — LENCHI Wiki

このプロジェクトは [西尾泰和](entities/西尾泰和.md) の未完の書籍 **「LLMを使いこなすエンジニアの知的生産術」** を、未来の LLM エージェントの記憶として整備するためのWiki。最初に読むべきページは → **[overview.md](overview.md)**。

## 0. プロジェクトの根本ファイル

- [overview.md](overview.md) — プロジェクト全体の合成。最初に読む
- [../CLAUDE.md](../CLAUDE.md) — エージェント運用スキーマ
- [log.md](log.md) — Ingest / Query / Lint の時系列ログ
- [questions/未解決の問い.md](questions/未解決の問い.md) — 次にやるべきことの源泉

## 1. 章ドラフト（chapters/）

第一部（2024）

- [前書き](chapters/前書き.md) — 完成度95%、Claude 3 Opus生成。本文全文を保存
- [第一章 『エンジニアの知的生産術』を問い直す](chapters/第一章.md) — 完成度90%、本文全文を保存
- [第二章 デジタルツールで知的生産を加速する](chapters/第二章.md) — 冒頭のみ完成、本論未着手
- [講演（Day9, 2024-06-06）](chapters/講演.md) — 実施済み、講演資料の構成要約

第二部（2026開始）

- [導入: LLM Wiki の導入](chapters/第二部-LLM_Wikiの導入.md) — 2026-05-01 着手、初稿40%

## 2. 概念（concepts/）

LLM時代の知的生産論を構成する概念群。

- [LLM時代の知的生産](concepts/LLM時代の知的生産.md) — 本書のフレーミング概念
- [異知性コミュニケーション](concepts/異知性コミュニケーション.md) — LLM を異質な知性として扱うスキル
- [創発的アプローチ](concepts/創発的アプローチ.md) — 章立てを先に決めない執筆姿勢
- [脱線のメリット](concepts/脱線のメリット.md) — レール外しを駆動力に
- [発散と収束](concepts/発散と収束.md) — LLM時代の中心問題
- [ニーズ駆動の生成](concepts/ニーズ駆動の生成.md) — ニーズが品質を決める
- [パーソナライズされた生成](concepts/パーソナライズされた生成.md) — 自分のニーズの言語化
- [フラクタル要約](concepts/フラクタル要約.md) — 異なる詳細度の要約群
- [KJ法とLLM](concepts/KJ法とLLM.md) — 紙のKJ法を更新する
- [自分に対する批判的思考](concepts/自分に対する批判的思考.md) — 自分を疑う
- [コンテキスト維持](concepts/コンテキスト維持.md) — 引き継ぎ・要約中継の技法
- [社会的トリガー](concepts/社会的トリガー.md) — 公開メモが他者から再訪を呼ぶ
- [有限化と無限ネットワーク](concepts/有限化と無限ネットワーク.md) — 書籍と Scrapbox の関係
- [RAG](concepts/RAG.md) — 個人知識ベースと汎用LLMの組み合わせ

## 3. エンティティ（entities/）

人物・書籍・モデル・ツール。

- 人物
  - [西尾泰和](entities/西尾泰和.md) — 著者
- 著者の前著
  - [『エンジニアの知的生産術』(2018)](entities/エンジニアの知的生産術2018.md) — 本書が問い直す対象
  - [『コーディングを支える技術』(2013)](entities/コーディングを支える技術2013.md)
- LLM モデル — 2024年期（プロジェクト第一部）
  - [Claude 3 Opus](entities/Claude3Opus.md) — Day1〜8の主たる対話相手
  - [ChatGPT / GPT-4 / GPT-4o](entities/ChatGPT.md)
  - [o1 pro](entities/o1pro.md) — Day10で総合振り返りに使用
- LLM モデル — 現行（2026, 第二部以降の対話相手候補）
  - [Claude 4 系](entities/Claude4系.md) — Opus 4.7 / Sonnet 4.6 ほか
  - [GPT-5 系](entities/GPT-5系.md) — GPT-5 / 5.2 / 5.5
- ツール
  - [Scrapbox（現Cosense）](entities/Scrapbox.md) — 著者の知識ベース、本書 raw 資料の源
  - [Kozaneba](entities/Kozaneba.md) — 著者作のデジタル KJ法ツール
  - [NISHIO Hirokazu's Assistant](entities/NISHIOアシスタント.md) — 著者の RAG カスタムGPT
- 関連プロジェクト
  - [デジタル民主主義](entities/デジタル民主主義.md) — 著者の並走プロジェクト

## 4. タイムライン（timeline/）

各 Day で何が言語化されたか。

- [Day 1](timeline/Day1.md) — 2024-04-08〜09 / 前書き・第一章生成、創発的アプローチ確立
- [Day 2](timeline/Day2.md) — 2024-04-09 / 第二章着手、コンテキスト圧迫エラー
- [Day 3](timeline/Day3.md) — 2024-04-10 / 異知性コミュニケーション・自分への批判的思考
- [Day 4](timeline/Day4.md) — 2024-04-11/04-20 / 脱線・ニーズ・パーソナライズ
- (Day 5 — 記録なし、デジタル民主主義に注力)
- [Day 6](timeline/Day6.md) — 2024-05-12 / フラクタル要約・カスタムGPT・発散収束
- [Day 7](timeline/Day7.md) — 2024-05-22 / Kozaneba で講演整理
- [Day 8](timeline/Day8.md) — 2024-06-01〜04 / 有限化、講演直前
- [Day 9 講演](timeline/Day9-講演.md) — 2024-06-06 / 講演実施
- [Day 10](timeline/Day10.md) — 2024-12-08 / o1 pro で総合振り返り、実践ガイドライン化提案
- (空白期間 2024-12〜2026-04 / デジタル民主主義活動)
- [Day 11](timeline/Day11.md) — 2026-05-01 / プロジェクト再起動、LLM Wiki 導入、第二部開始

## 5. 未解決の問い

- [questions/未解決の問い.md](questions/未解決の問い.md) — 12個の問い（理論的・編集上・運用上）

## 6. 一次資料（raw/）

- `../raw/nishio-llmを使いこなすエンジニアの知的生産術.2hop.txt` — Scrapbox からのエクスポート 133ページ。**改変禁止**
