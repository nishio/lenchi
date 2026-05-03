# Day 13 — 2026-05-03 MindTrellis / ConnectingDots / Kozaneba 三者対比

## 何が起きたか

著者が ChatGPT (GPT-5系) に「ネットを検索して面白い話題を見つけてまとめて」と依頼したことから始まり、4 ラウンドの対話を経て、**[MindTrellis](../entities/MindTrellis.md)（外部研究）/ [ConnectingDots](../concepts/ConnectingDots.md)（西尾自身の設計）/ [Kozaneba](../entities/Kozaneba.md)（西尾の既存ツール）の三者対比** と、ConnectingDots 構築の **5 週間アクションプラン**（2026-05-04〜05-31）が整理された。raw: `2026-05-03-mindtrellis-connectingdots-GPT.txt`（当初 `wiki/concepts/gpt-mindtrellis-connectingdots-20260503.md` として誤配置されていたものを `raw/` に改名移動）。

## 新規作成

- **[concepts/ConnectingDots.md](../concepts/ConnectingDots.md)** — 西尾自身の設計中システム。**事実・関係・解釈・物語・表示の 4 層分離**（Dots / Relations / Stories / Views）が中核。LENCHI Wiki と同じ問題（[ナラティブの価値](../concepts/ナラティブの価値.md) の wiki化損失）に対する別アプローチ。
- **[entities/MindTrellis.md](../entities/MindTrellis.md)** — 2026 年の研究システム（arXiv:2604.23129）。AI と人間が同じ知識グラフを共同編集。「AI 生成構造を暫定物として扱う」設計思想。

## 三者対比の整理

| | Kozaneba | MindTrellis | ConnectingDots |
| --- | --- | --- | --- |
| 主単位 | こざね | Knowledge Graph ノード | Dot（検証可能な事実） |
| 主操作 | 空間配置・グループ化・線引き | 質問・ノード追加・関係修正・階層再編 | Dot 採用・Relation 採用・Story 編集 |
| AI の位置 | もともとは文房具的・人間主導 | AI が検索・提案・構造化に参加 | AI は候補生成のみ、人間が curator |
| 強み | 思考の手触り、前言語的な近さ | 文書根拠、知識グラフの共同成長 | 事実と解釈の分離、複数 Story の再利用 |
| LENCHI Wiki との関係 | 既存の道具 | 同じ系譜（外部記憶 + AI） | 同じ問題への別アプローチ |

GPT の整理：**MindTrellis は ConnectingDots の Dots/Relations 部分の AI 実装。ConnectingDots はその上に Stories と Views を明示的に置く**。

## ConnectingDots と LENCHI Wiki の関係

ConnectingDots は LENCHI Wiki と **同じ問題に対する別アプローチ** として位置づけられる。

| | LENCHI Wiki | ConnectingDots |
| --- | --- | --- |
| 主単位 | 概念ページ | Dot（事実カード） |
| 統合の場 | wiki ページ（合成知） | Story（目的を持つ語り） |
| ナラティブの扱い | `raw/` 保存、`wiki/` で抽出 | Story の caption と順序で表現 |
| 出典 | ページ末尾の「出典」節 | Dot に必須フィールド |
| 主観性 | 概念抽出時に編集者の判断（暗黙） | Story 単位で明示 |

[ナラティブの価値](../concepts/ナラティブの価値.md) で言う「wiki 化が 6 軸のうち 4〜5 軸を犠牲にする」問題に対し、ConnectingDots は **Story 層で語り次元を明示的に保持する** ことで応答している、と読める。

## 5 週間アクションプラン（2026-05-04〜05-31）

GPT が整理した、ConnectingDots 最小実用品の構築計画：

- **第 1 週（5/4-10）**: 自己紹介を題材に Dots/Stories/Views の最小実装。静的 HTML 出力、accepted Dots 20 個、Story 1 本。AI なし
- **第 2 週（5/11-17）**: AI を **candidate 生成だけ** に使う（accepted にはしない、人間が昇格）
- **第 3 週（5/18-24）**: 同じ Dots から **別 Story** を作る（再利用可能性の検証）
- **第 4 週（5/25-31）**: Kozaneba を Story 編集の **作業 View** として接続
- **5 週目以降**: MindTrellis 的な文書根拠探索・関係提案を足す

「**やらないこと**」も明示：知識グラフ UI を作らない、Relation テーブルを本格設計しない、AI に Story を完成させない、Kozaneba 統合を先にやらない、など。

## 設計判断

- **GPT 対話原文の配置先**: 当初 `wiki/concepts/` に誤配置されていたが、**生の対話ログは `raw/` の領分**（CLAUDE.md の 3 層ルール）。`raw/2026-05-03-mindtrellis-connectingdots-GPT.txt` に改名移動。
- **MindTrellis をエンティティ化**: 特定の研究システムなのでエンティティページに（[Q19](../questions/未解決の問い.md) で挙げた他の研究 RAG / ReAct / MemGPT 等は概念ページ内の言及のみだが、MindTrellis は LENCHI と接続点が深いので独立化）。
- **ConnectingDots を概念ページに**: 西尾の設計思想であり実装はこれから。エンティティ（実体のある書籍・人物・ツール）ではなく、設計パターンに近いので concepts/ に配置。

## 引き継ぎ事項

- ConnectingDots の 5 週間アクションプランが 5/4 から開始予定。LENCHI 側でフォローアップする場合は週次で進捗を ingest する候補（→ [Q23](../questions/未解決の問い.md)）。
- [ナラティブの価値](../concepts/ナラティブの価値.md) の 6 次元が ConnectingDots でどこまでカバーされるか（特に「2. 順序の意味」「5. 共感・視点取得」）の検証。
- [Q19](../questions/未解決の問い.md)（外部記憶の研究系譜）に MindTrellis を追加。

## 出典

- raw: `2026-05-03-mindtrellis-connectingdots-GPT.txt`（西尾 × ChatGPT GPT-5 系の 4 ラウンド対話）
- 関連 Scrapbox: `ConnectingDotsシステム`、`自己紹介と歴史は共通の構造を持つ`、`かんがえをまとめるデジタル文房具Kozaneba`
- 論文: arXiv:2604.23129
