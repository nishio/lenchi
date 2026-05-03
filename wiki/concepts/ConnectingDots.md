# ConnectingDots

[西尾泰和](../entities/西尾泰和.md) が設計中の知識管理システム。**事実・関係・解釈・物語・表示の分離** を中核とする設計思想。検証可能な「Dots（事実カード）」を蓄積し、人間がそれを編んで「Stories（語り）」を作り、「Views（表示形式）」で見せる、という三層構造。

## 来歴と本書プロジェクトでの位置づけ

- 西尾の Scrapbox: [ConnectingDotsシステム](https://scrapbox.io/nishio/ConnectingDotsシステム)、[自己紹介と歴史は共通の構造を持つ](https://scrapbox.io/nishio/自己紹介と歴史は共通の構造を持つ)。
- [Day 13](../timeline/Day13.md)（2026-05-03）に GPT との対話で **MindTrellis ([entities/MindTrellis.md](../entities/MindTrellis.md))** との対比が整理され、2026-05-04 以降の 5 週間アクションプランが立てられた。
- LENCHI（個人の知的生産）と [ブロードリスニング本](../entities/ブロードリスニング本.md)（集団の知的生産）に並ぶ、**3 つ目の並走プロジェクト** になる可能性。LENCHI とは「[ナラティブの価値](ナラティブの価値.md) で言う wiki化の損失問題」を別アプローチで扱う関係（[Q23](../questions/未解決の問い.md)）。

## 設計の核心 — 4 層の分離

| 層 | 内容 | 役割 |
| --- | --- | --- |
| **Dots** | 検証可能な事実カード（claim + source + quote） | 再利用可能な部品 |
| **Relations** | Dot 間の関係（supports / contradicts / causes / precedes / elaborates / same_as / example_of） | 構造の明示（ただし最初は Story 内の順序に持たせる） |
| **Stories** | 目的と聴衆を持つ語り（selected dots + interpretation + omitted dots） | 主観的キュレーション |
| **Views** | 表示形式（Kozaneba / 年表 / エッセイ / スライド / 因果図） | 出力 UI |

特に重要なのは：

- **「事実」と「解釈」を混ぜない** — Dot の `claim` は事実、Story の `caption` は語り側の解釈。
- **「何を入れたか」だけでなく「何を入れなかったか」も価値判断** — `omittedDots` を Story に明示する。
- **Story は主観的** — どの事実を選ぶか、どの順序で並べるか、何を重要とみなすかには価値判断が入る。

## MindTrellis との関係

[MindTrellis](../entities/MindTrellis.md) は ConnectingDots の Dots → Relations 部分を AI 支援で作る研究実装。一方、ConnectingDots はその上に **Stories と Views を明示的に置く** 点で射程が広い。

> MindTrellis は、ConnectingDots における Dots と Relations を AI 支援で作る部分に近い。ConnectingDots は、その上に Stories と Views を明示的に置こうとしている。（[Day 13 GPT サーベイ](../timeline/Day13.md)）

GPT は、AI の役割を 5 つに分けて設計することを提案：**AI Extractor / AI Linker / AI Critic / AI Storyteller / Human Curator**。AI Storyteller を無制限に走らせると事実と解釈が混ざるため、`Fact` / `Inference` / `Interpretation` / `Story` / `View` を分離して表示する設計が望ましい。

## Kozaneba との関係

[Kozaneba](../entities/Kozaneba.md) は ConnectingDots の **View の一種** として位置づけられる（GPT の整理）：

> ConnectingDots = データモデル / 思想 / 事実と解釈の分離
> MindTrellis = 文書から Dots と Relations を育てる AI 機構
> Kozaneba = Dots, Relations, Stories を触る空間 UI

Kozaneba の独自性は「**前言語的な構造化**」に強い点。MindTrellis の知識グラフは「意味関係」を明示したがるが、KJ法的な配置は「まだ言語化できない近さ」も扱える。

## LENCHI Wiki との関係

ConnectingDots と LENCHI Wiki（[Karpathy の LLM Wiki](../../llm-wiki.md) の実装）は **同じ問題に対する別アプローチ**：

| | LENCHI Wiki | ConnectingDots |
| --- | --- | --- |
| 主単位 | 概念ページ（境界が引かれた抽象） | Dot（検証可能な事実） |
| 統合の場 | wiki ページ（合成知） | Story（目的を持つ語り） |
| ナラティブの扱い | `raw/` に保存、`wiki/` で抽出（[ナラティブの価値](ナラティブの価値.md) で 6 軸の損失） | Story の `caption` と順序で表現 |
| 出典 | wiki ページ末尾の「出典」節 | Dot に `source` フィールドとして必須 |
| 主観性の扱い | 概念抽出時に編集者の判断（暗黙） | Story 単位で明示（「主観的キュレーション」） |

[ナラティブの価値](ナラティブの価値.md) で言う「wiki 化が 6 軸のうち 4〜5 軸を犠牲にする」問題に対し、ConnectingDots は **Story 層で語り次元（順序・解釈・omitted）を明示的に保持する** ことで応答している、と読める。

## 関連概念・エンティティ

- [ナラティブの価値](ナラティブの価値.md) — wiki 化で失われる 6 次元。ConnectingDots の Story 層がその一部を保持する設計。
- [Kozaneba](../entities/Kozaneba.md) — View の一種として位置づけ可能。
- [MindTrellis](../entities/MindTrellis.md) — Dots/Relations 部分の AI 支援実装。
- [後段としてのWiki](後段としてのWiki.md) — LENCHI Wiki と ConnectingDots はどちらも「下流に永続記憶を置く」発想。

## 出典

- raw: `2026-05-03-mindtrellis-connectingdots-GPT.txt`（[Day 13](../timeline/Day13.md) の GPT 対話）
- 関連 Scrapbox: `ConnectingDotsシステム`、`自己紹介と歴史は共通の構造を持つ`、`かんがえをまとめるデジタル文房具Kozaneba`
