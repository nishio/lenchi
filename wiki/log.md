# Log

Ingest / Query / Lint の時系列ログ。`## [YYYY-MM-DD] {ingest|query|lint} | 概要` の書式で1エントリ1行を起点に追記する。

## [2026-05-01] ingest | 現行 LLM 動向（Q12 部分対応）

利用者判断: Q14（デジタル民主主義書籍 ingest）は **不採用**で記録。Q12（後発モデル追従）に着手。

- WebSearch で 2026-05 時点の状況を確認。Claude 4 世代の Opus 4.7（2026-04-16）・Sonnet 4.6・GPT-5 世代の 5.5（2026-04-23）が現行フロンティア。
- 新設: [entities/Claude4系.md](entities/Claude4系.md)、[entities/GPT-5系.md](entities/GPT-5系.md)。
- 更新: [index.md](index.md) に現行モデル節を追加、[questions/未解決の問い.md](questions/未解決の問い.md) Q12 を **部分対応済み** に格下げ、Q14 を **解決: 採用しない** で記録。
- 設計判断: 既存 [entities/Claude3Opus.md](entities/Claude3Opus.md) 等は **2024 期の記録として保存**し、現行は別エンティティに分離。これにより各時点での LLM 状態が比較可能になる。

## [2026-05-01] lint | Day 11 後の整合性チェック

新方針（LLM Wiki 導入・第二部開始）を受けて既存ページを点検した。

- **A** 古い "as-of" の明示: [entities/Claude3Opus.md](entities/Claude3Opus.md)、[entities/o1pro.md](entities/o1pro.md)、[entities/ChatGPT.md](entities/ChatGPT.md) に「これは2024年期の記録」である旨を追加し、Q12 にリンク。
- **B** [concepts/コンテキスト維持.md](concepts/コンテキスト維持.md) に「構造解 — LLM Wiki の導入」節を追加。Day 11 と 第二部 導入章へ接続。
- **C** [questions/未解決の問い.md](questions/未解決の問い.md) を更新: Q6 に第二部の venue 確定を追記、Q11 を **半解決** に格下げ、Q12 を **優先度高** に格上げして17か月空白を反映、Q13（第一部・第二部の接続）と Q14（デジタル民主主義書籍 ingest）を新設。
- **D** [CLAUDE.md](../CLAUDE.md) に `questions/*.md` テンプレートを追加。
- 孤児ページ無し。書誌的事実として保存すべき2024年の章本文（前書き・第一章）は更新せず原文保存。

## [2026-05-01] ingest | Day 11 — プロジェクト再起動・第二部開始

- 利用者からの状況更新: デジタル民主主義活動が一段落、関連書籍を 2026-09 出版予定。LENCHI 再起動。
- 「Karpathy の LLM Wiki を導入したことの解説」が本日のアクション。
- 作成: `wiki/timeline/Day11.md`、`wiki/chapters/第二部-LLM_Wikiの導入.md`（初稿40%）
- 更新: `wiki/overview.md`（再起動ステータス・第二部追加）、`wiki/index.md`（Day11・第二部）、`wiki/entities/デジタル民主主義.md`（活動一段落・出版予定）、`CLAUDE.md`（LLM Wiki の帰属を Karpathy に修正）
- 次の推奨: [第二部 導入章](chapters/第二部-LLM_Wikiの導入.md) 末尾の「第二部で書くこと」見取り図に従い、次節（記憶の3層構造）を着手

## [2026-05-01] ingest | Wiki初期構築

- Source: `raw/nishio-llmを使いこなすエンジニアの知的生産術.2hop.txt`（Scrapbox エクスポート、133ページ）
- 対象期間: 2024-04-08（Day1）〜 2024-12-08（Day10）
- 作成したページ:
  - スキーマ: `CLAUDE.md`
  - ハブ: `wiki/overview.md`、`wiki/index.md`、`wiki/log.md`
  - 章ドラフト 4: `wiki/chapters/{前書き,第一章,第二章,講演}.md`
  - 概念 14: `wiki/concepts/*.md`
  - エンティティ 10: `wiki/entities/*.md`
  - タイムライン 9: `wiki/timeline/{Day1〜Day4, Day6〜Day10}.md`（Day 5は記録なし）
  - 未解決の問い 1: `wiki/questions/未解決の問い.md`
- 参照モデル: [llm-wiki.md](../llm-wiki.md) のパターンを採用
- 次の推奨アクション: `questions/未解決の問い.md` の Q6（実践編の新章執筆）から着手
