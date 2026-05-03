# MindTrellis

複数文書を読むユーザと AI が、文書由来の知識とユーザ自身の洞察を **同じ知識グラフ上で共同編集** する研究システム。2026 年の論文（arXiv 2604.23129）。LENCHI には [Day 13](../timeline/Day13.md) で取り込み。

## 概要

普通の RAG チャットは「質問→答え」を返すが、MindTrellis は答えを一回きりの文章として終わらせず、**ノードとエッジからなる構造に追加していく**。ユーザはその構造を見ながら、質問・ノード追加・関係修正・階層再編が可能。

論文ではこれを **co-created knowledge graph** と呼ぶ。文書由来の知識とユーザ由来の洞察が同じグラフ上に共存。

## 設計の特徴

### UI 構成

- **左**: ファイル管理パネル（文書アップロード）
- **中央**: Knowledge Canvas（知識グラフ表示）
- **右**: チャットパネル（自然言語で質問・ノード追加・リンク変更を命令）

Canvas ではノードクリックで追加質問・削除・拡張候補表示・重要ノードハイライト。**セマンティックズーム**（ズームアウトでタイトルだけ、ズームインで詳細）。

### 知識グラフの表現

マインドマップとコンセプトマップの中間：

- マインドマップから階層構造を借用（上位概念 → 下位概念）
- コンセプトマップから **エッジラベル** を借用（"is caused by" のような関係明示）
- あるノードが **複数の親に属する** ことが可能（例: "Deforestation" が "Causes of Climate Change" と "Biodiversity Loss" の両方）

### 内部構造 — 3 つのエージェント

- **Oracle** — 入力が「質問 / グラフ編集 / 既存ノードの拡張」のいずれかを判定
- **Adaptive Retriever** — RAPTOR 型の階層検索。広い概観は上位要約、細部は下位チャンク
- **Map Manager** — グラフ編集担当。`AddNode` / `AddEdge` / `DeleteNode` / `UpdateNode` の関数呼び出しとして実行、失敗時は再計画

実装: React + Flask + LangGraph + ChromaDB + GPT-4o / GPT-4o-mini + text-embedding-3-small。

## 評価結果

12 人のユーザスタディ（気候変動・AI 倫理の文書セットでスライド作成）：

- 知識整理・使いやすさ・トピック理解・スライド構成支援で高評価
- Oracle 意図分類精度: 91.4%
- Map Manager 編集成功率: 93.0%（完全に正しく統合できた率: 78.1%）
- Adaptive Retriever 正答率: 82.5%（ナイーブ RAG 58.8%）
- エンドツーエンド成功率: 83.6%

ただし参加者 12 人で生成 AI 経験者中心、長期利用での安定性は未検証。

## LENCHI における意義

### 「AI 生成構造を暫定物として扱う」設計思想

論文の独自性は、AI が作った階層・関係ラベル・グルーピングを **すべて仮説** として扱い、ユーザが自然言語でも直接操作でも直せること。

> AI 生成の組織化は最終決定ではなく、すべてのレベルでユーザが調整できるべき（論文より）

これは LENCHI Wiki の「[ナラティブの価値](../concepts/ナラティブの価値.md)」観（wiki 化が暗黙知・順序の意味・共感などを犠牲にする）と問題意識が交差する。**AI が提示した構造と人間の違和感の差分から理解が進む** という設計。

### ConnectingDots との関係

[ConnectingDots](../concepts/ConnectingDots.md) システム（西尾自身の設計）と比較すると、MindTrellis は **Dots → Relations 部分を AI 支援で作る研究実装** に位置づけられる（[Day 13](../timeline/Day13.md)）。ConnectingDots はその上に Stories と Views を明示的に置く点で射程が広い。

### 弱点

- 意図解釈の曖昧さ（エンドツーエンド失敗の 52% は Oracle 誤分類由来）
- 表現形式が階層的ノードリンク図に固定（空間クラスタ・行列・タイムラインに弱い）
- テキストのみ対応（図・スライド・手書きメモなどの視覚情報を扱えない）

## 関連

- [ConnectingDots](../concepts/ConnectingDots.md) — 西尾の設計。MindTrellis は その Dots/Relations 部分の AI 実装と重なる
- [Kozaneba](Kozaneba.md) — 「前言語的な構造化」に強い空間 UI、MindTrellis とは異なる強みを持つ
- [後段としてのWiki](../concepts/後段としてのWiki.md)、[段階的開示](../concepts/段階的開示.md) — 同じ「外部記憶 + AI」系譜
- [Q19](../questions/未解決の問い.md) — 外部記憶の研究系譜への追加候補

## 出典

- 論文: arXiv:2604.23129 "MindTrellis: Co-Creating Knowledge Structures with AI through Interactive Visual Exploration"
- raw: `2026-05-03-mindtrellis-connectingdots-GPT.txt`（[Day 13](../timeline/Day13.md) の GPT 解説）
