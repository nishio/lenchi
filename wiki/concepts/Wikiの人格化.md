# Wikiの人格化（wikis-as-personas）

複数の LLM Wiki に **同じ問い** を並列で投げると、各 Wiki が **自分のスキーマ・運用目的を通して** その問いを読み替えて答える。Wiki は単なる検索可能な知識ベースではなく、**「自分の関心枠を持った人格」** として振る舞う。手動 orchestrator パターン（人間が複数 Wiki に並列照会して結果を集約）の最小実装でこれが実演された。

## 来歴

[Day 14](../timeline/Day14.md)（2026-05-04）に、本 Wiki（LENCHI / 通称 A3）と他 2 つの Wiki（Karpathy LLM Wiki / A1、ConnectingDots / A2）に対して **同一の問い**「[MindTrellis](../entities/MindTrellis.md) の話を ingest したことでどんな変化があった？」を並列で投げて結果を比較した実験から言語化された。

## 観察された差分の構造

### 1. 問いを「自分の目的」を通して読み替える

| Wiki | 「変化」の解釈対象 |
| --- | --- |
| A1 (LLM Wiki) | wiki 内部で何が増えた・繋がった（メタ wiki 視点） |
| A2 (ConnectingDots) | 我々のシステムの positioning がどう変わったか |
| A3 (LENCHI) | 本書のプロジェクト構造がどう変わったか |

同じ語「変化」が 3 つの違う対象を指している。これが Wiki 人格化の最も基本的な現れ — **質問のスキーマを自分の関心に変換している**。

### 2. 各 Wiki の運用文化が回答スタイルに染み出す

A2（ConnectingDots）は「**anti-misattribution 規律**」を持っており、同じソース内でも誰由来か（MindTrellis vs GPT の整理 vs 西尾自身）を切り分ける文化がある。これは [ConnectingDots](ConnectingDots.md) の Dot に `source` を必須とする fact-wiki-separation の精神が **回答スタイルにまで** 染み出している例。

A1（LLM Wiki）と A3（LENCHI）はこの分離をしない。

### 3. 時間粒度・記録 artifact の差

A3（LENCHI）は **「Q 番号付きバックログ」** という artifact を持ち、ingest が **新概念追加 + 未決 Q 層の状態変化として二重に記録される**（[未決問いの first-class 化](#a3-の二層記録設計-について) 参照）。これは A1/A2 にはない構造。

### 4. 多視点での独立収束（堅牢性のシグナル）

3 つの Wiki が独立に [Kozaneba](../entities/Kozaneba.md) の **「前言語的な構造化に強い」** ニッチに到達した。これは：

- Kozaneba の本質的ニッチは **特定 Wiki の解釈に依存しない**（多視点で同じ答えに収束する程度には頑健）
- 一方で、**それが各 Wiki にとって何を意味するか** は完全に分かれる（A1: 既存ツール、A2: View の一種、A3: 第二章の実演対象）

→ [思考の熟成](思考の熟成.md) の機構と同型: **異経路で同じ場所に辿り着く** ことが概念の頑健性の指標になる。

### 5. 抽出可能な転移可能性に階層がある

各 Wiki の応答に含まれる「他に転用できる insight」の抽象度が違う：

| Wiki | 転用可能なもの | 抽象度 |
| --- | --- | --- |
| A1 | structure-as-hypothesis（AI が出した構造を仮説として扱う） | 他ドメインに転移しうる **抽象** |
| A2 | AI 役割タクソノミ（Extractor / Linker / Critic / Storyteller / Curator） | ConnectingDots スキーマ拡張に直結する **具体** |
| A3 | Q23（本書の章立て判断） | **個別意思決定** |

抽象度が 3 段階あり、Wiki ごとに「どのレイヤーで考える主体か」が分化している。

## 手動 Orchestrator パターン

本実験は、**人間が Aggregator を担う最小実装** だった：

1. 人間が同じ問いを 3 Wiki に並列で投げる
2. 各 Wiki が独立に回答
3. 人間が回答を比較し、共通点 / 差分 / 抽象度 / 堅牢性を抽出する
4. 抽出された meta-finding を各 Wiki に **fill back** する

これは [後段としてのWiki](後段としてのWiki.md) の発想を multi-wiki に拡張したもの。後段の Wiki が **複数あって、それぞれが上流の同じ問いを違う視点で吸収する**。Aggregator は当面人間が担うが、将来的には自動化の余地。

## A3 の二層記録設計について

LENCHI Wiki の独自構造は「**未決問いを first-class artifact として持つ**」点にある。具体的には [questions/未解決の問い.md](../questions/未解決の問い.md) というファイルが、概念層と並ぶ独立レイヤーとして存在する。

帰結：

- ingest イベントは **二層** に状態変化を刻む（concept layer に新ページ、question layer に Q の状態変化）
- Q ライフサイクル（new → 部分対応 → 解決）が時間で navigable
- 「何が解決されたか」を遡って問い直せる

A1/A2 にはこの artifact がない。これは LENCHI が「**書籍プロジェクト**（[overview.md](../overview.md)）」という時間的な開始点と完成点を意識しているための設計判断。

## 含意

- **Wiki 設計は人格設計** — schema を選ぶことは、その Wiki が将来どのような問いをどのように受け取るかを決める。
- **多視点の収束は概念頑健性のシグナル** — 同じ概念に独立に到達する Wiki が複数あれば、その概念は schema 依存ではない。
- **単一 Wiki に閉じない知的生産** — 個人プロジェクト（LENCHI）/ 設計プロジェクト（ConnectingDots）/ パターン提唱（LLM Wiki）が並走するとき、人間は orchestrator として複数 Wiki を切り替える。

## 関連概念

- [後段としてのWiki](後段としてのWiki.md) — 単一 Wiki の発想を multi-wiki に拡張したのが本概念。
- [思考の熟成](思考の熟成.md) — 異経路収束による頑健性。
- [ナラティブの価値](ナラティブの価値.md) — 各 Wiki が異なる schema で同じ raw を吸収するとき、どのナラティブ次元が保存され、どれが失われるかは Wiki ごとに異なる。
- [ConnectingDots](ConnectingDots.md) — A2 の運用文化（anti-misattribution）の出所。
- [段階的開示](段階的開示.md) — 各 Wiki が自分のインデックス階層で問いを処理する。

## 出典

- [Day 14](../timeline/Day14.md)（2026-05-04）の 3-Wiki 比較実験
- LENCHI 内部の自己観察（log.md の query エントリ）
