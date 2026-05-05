# Day 14 — 2026-05-04 3-Wiki 比較実験と自己観察

## 何が起きたか

著者が **同じ問い**「[MindTrellis](../entities/MindTrellis.md) の話を ingest したことでどんな変化があった？」を 3 つの Wiki（**Karpathy LLM Wiki / A1**、**[ConnectingDots](../concepts/ConnectingDots.md) / A2**、**LENCHI / A3**）に並列で投げて、結果の差分を分析した。これは事実上、**手動 orchestrator パターン** の最小実装になった（人間が Aggregator を担う）。

著者の分析結果と、それに対する LENCHI Wiki 自身の自己観察（特に A3 の特徴づけの修正）を fill back した。

## 言語化された新概念

- **[Wikiの人格化（wikis-as-personas）](../concepts/Wikiの人格化.md)** — 同じ問いを複数 Wiki に並列で投げると、各 Wiki が **自分のスキーマ・運用目的を通して** 問いを読み替える。Wiki は「自分の関心枠を持った人格」として振る舞う。

## 観察された 5 つの差分

1. **問いを「自分の目的」を通して読み替える** — 同じ語「変化」が、A1 ではメタ wiki 視点、A2 では positioning、A3 では本書の構造、を指す。
2. **anti-misattribution 規律**（A2 のみ） — ConnectingDots の Dot/source 分離精神が回答スタイルに染み出す。
3. **時間粒度・記録 artifact の差**（A3 が独自） — Q 番号付きバックログによる二層記録（後述）。
4. **Kozaneba「前言語的」ニッチへの独立収束**（3 Wiki 共通） — 多視点での独立到達は概念頑健性のシグナル。
5. **転用可能性の抽象度階層** — A1 は他ドメイン転移可能な抽象、A2 は具体的スキーマ拡張、A3 は個別意思決定（Q23）。

## A3（LENCHI）の特徴づけ — 自己修正

著者の初期分析では「**A3 は ingest が新概念ではなく未決 Q 追加として記録される**」と整理されたが、実データを確認すると：

- Day 12 Sessions A/B/C: 新概念 5 件 + 新エンティティ 2 件 + Q14/16/17 解決 + Q15/19/20/21/22 新設
- Day 13: 新概念 1 件（[ConnectingDots](../concepts/ConnectingDots.md)）+ 新エンティティ 1 件（[MindTrellis](../entities/MindTrellis.md)）+ Q19 更新 + Q23 新設

→ LENCHI の ingest は **新概念 / 新エンティティの追加と Q 層の更新を同時にやっている**。

正確な特徴づけは：

> LENCHI Wiki は ingest イベントが **新概念追加 + 未決 Q 層の状態変化として二重に記録される**。これは [questions/未解決の問い.md](../questions/未解決の問い.md) を **first-class artifact** として持つ設計判断の現れ。

A1/A2 にはこの artifact がない。LENCHI が「**書籍プロジェクト**」という時間的な開始点と完成点を意識しているための設計差分。

## 引き継ぎ事項

- [Wikiの人格化](../concepts/Wikiの人格化.md) を [第二部 導入章](../chapters/第二部-LLM_Wikiの導入.md) の本論ノードに登録するか検討（→ 新規問い追加候補）。
- 3-Wiki 比較を **継続的な query 手法** として運用するか（毎月など）。これは [後段としてのWiki](../concepts/後段としてのWiki.md) を multi-wiki に拡張する運用実験。
- A2 の anti-misattribution 規律を LENCHI でも採用すべきか（ナラティブの価値の精度向上に資する可能性）。

## 出典

- 著者の 3-Wiki 比較分析（このセッション内で共有）
- LENCHI 内部の self-reflection（A3 特徴づけの自己修正）
