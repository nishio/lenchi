# Log

Ingest / Query / Lint の時系列ログ。`## [YYYY-MM-DD] {ingest|query|lint} | 概要` の書式で1エントリ1行を起点に追記する。

## [2026-05-08] ingest | Day 16 — 著者の包括フィードバック（5/7 電車移動中執筆）

- Source: `raw/2026-05-08-nishio-train-feedback.txt`（著者が 5/7 電車内で Wiki 全体を通読してまとめた所感・補足・再フレーミング・ingest 指示）
- 新規ページ:
  - [timeline/Day16.md](timeline/Day16.md) — 本セッション
  - [concepts/まだ言語化できない近さ.md](concepts/まだ言語化できない近さ.md) — Kozaneba の独自ニッチを表す概念。意味関係の明示前の概念間距離
  - [concepts/分布としての他者.md](concepts/分布としての他者.md) — ブロードリスニングを狭く取り直した本書での扱い
- Q 状態変化（多数）:
  - **解決アーカイブへ**: Q8（プロセスログ：電子なら全部残す）、Q20（命名規約：二系統併存）
  - **部分対応に格下げ**: Q23（ConnectingDots 進捗追跡は不要、本書扱いは保留）
  - **著者見解追記**: Q4（サービス提供論はスコープ外）、Q6・Q7（LLM時代の新サービスが必要）、Q9（ingest着手予定）、Q10（JSON+Claude Code+視線エミュレーション）、Q21（分布としての他者へフォーカス）、Q22（Cosense比較も含めて拡張）
  - **新設**: Q27（Q tracking を Spaced Repetition / Incremental Reading 系に再設計）
- 既存ページ更新:
  - [entities/Kozaneba.md](entities/Kozaneba.md) — 新方針（JSON+視線エミュ）、道具世代交代の論点
  - [concepts/後段としてのWiki.md](concepts/後段としてのWiki.md) — 別表現「下流に永続記憶を置く」を冒頭に追加
  - [concepts/ブロードリスニング.md](concepts/ブロードリスニング.md) — 「分布としての他者へフォーカス」節、AI要約の進化と収束ムーブの位置づけ
  - [overview.md](overview.md) — 「初見不親切問題」自己観察を反映、サービス提供論スコープ外を明記
  - [index.md](index.md) — 新概念2件・Day 16・新raw・active件数（22）を更新
- Ingest 待ち（[Q27](questions/未解決の問い.md) に集約）:
  1. 著者の Spaced Repetition 議論（エンジニアの知的生産術より、raw に入っているか要確認）
  2. SuperMemo Incremental Reading
  3. 常緑のノート（Evergreen Notes）系議論
  4. 「収束ムーブ」概念（[分布としての他者](concepts/分布としての他者.md) と接続）
  5. 「Cosense 的とは何か」の言語化
- 設計判断:
  - 「下流に永続記憶を置く」は独立概念ページにせず、[後段としてのWiki](concepts/後段としてのWiki.md) の別表現として冒頭に追記（重複回避）
  - Q27 は当面「Spaced Repetition 再設計の方向性 + ingest 待ちリスト」のメタ Q として運用。再設計の実装は ingest 完了後に判断

## [2026-05-08] lint | Day 15 後の Wiki 健康診断と前向き整備

実施項目: 孤児ページ、古い主張、横断概念の逆リンク、章ドラフト鮮度、CLAUDE.md 観点拡充。

### 発見

- **A. 孤児ページなし**（最少 4 件、新規 Wikiの人格化／想起の設計含む）
- **B. 章ドラフト鮮度**: 前書き・第一章は Day 12 進展までで Day 15（記憶=想起の設計、やる気=プロジェクト停滞）への接続が未反映。第二部 導入章の見取り図に「想起の設計」が未登録
- **C. 横断的統合性**: [想起の設計](concepts/想起の設計.md) を「第二部の主要概念群を横断する整理」と位置づけたが、横断される側（後段としてのWiki、段階的開示、ナラティブの価値、RAG、フラクタル要約、思考の熟成、コンテキスト維持）の関連欄に逆リンクなし
- **D. 古い主張**: [overview.md](overview.md) の中間層議論が Q4「両論併記」前提のまま。Day 15 で「A 不要、B 優位」確定なので注記必要
- **E. Q (未解決の問い) 鮮度**: 最新（直近で Q24/Q25/Q26 新設、Q4 を部分対応へ、Q5/Q25 著者見解統合）
- **F. CLAUDE.md Lint 観点**: 想起の設計の四つの軸（discoverability / zoom / context preservation / latency tolerance）を運用評価指標として併用できる

### 実施した整備

1. 想起の設計を 7 つの横断概念ページの関連欄に逆リンク追加（後段としてのWiki / 段階的開示 / ナラティブの価値 / RAG / フラクタル要約 / 思考の熟成 / コンテキスト維持）
2. 章ドラフト 前書き・第一章 残課題に Day 15 進展への接続を追記
3. [chapters/第二部-LLM_Wikiの導入.md](chapters/第二部-LLM_Wikiの導入.md) の見取り図に「[想起の設計](concepts/想起の設計.md) としての LLM Wiki」節を追加
4. [overview.md](overview.md) に「中間層」節を新設、Day 15 で確定した「A 不要、B 優位」を反映
5. [concepts/Wikiの人格化.md](concepts/Wikiの人格化.md) の差分 2 節（運用文化）に **2026-05-07 補足** を追加。`nishio:` 撤回経緯と「ファイル境界 vs ファイル内境界」での分離設計の対比
6. [CLAUDE.md](../CLAUDE.md) の Lint 節に「想起の設計の四つの軸」を運用評価指標として追加
7. 本 Lint 結果を log.md に記録（このエントリ）

### 設計判断

- 想起の設計のメタ位置づけ（既存概念群を束ねる）を、横断される側からの逆リンクとして双方向に成立させた。これにより読者がどの概念から入っても想起の設計に到達できる
- `nishio:` プレフィックス撤回の経緯を **Wikiの人格化** ページに残すことで、「LENCHI と ConnectingDots の anti-misattribution 設計差」が後日参照可能になった

## [2026-05-07] ingest | raw/2026-05-07-nishio-Q4Q5コメント.txt を Wiki に反映

直前のセッションで raw 化した著者の Q4・Q5 直筆コメントを、AI による合成知の形で wiki 側に反映：

- **Q4**: 「A は不要、B が優れている」を著者見解として明記、残課題はサービス提供（範囲・課金）論に整理。**部分対応** に格下げ
- **Q5**: 「アイデア → 実行可能なネクストアクション分解」の枠組みを著者見解として記録。**ボトルネックの移動**（分解 → 実行リソース）が重要観察として明示
- **Q25**: Q5 の著者見解と接続、停滞要因に「人間にしかできないアクションの実行リソース不足」を追加。「ボトルネックの移動」観点も統合
- **[concepts/有限化と無限ネットワーク.md](concepts/有限化と無限ネットワーク.md)**: 接続装置進化の表に「2026-05-07 著者見解の更新」節を追加、A 不要・サービス提供論の位置づけを明示
- **[entities/NISHIOアシスタント.md](entities/NISHIOアシスタント.md)**: 「著者の最新見解」節を追加、2024 年期の記録 + 第三者向け窓口として保存し続ける旨を明記
- 設計判断: 著者の生コメント（raw）と、AI による合成知（wiki）の **両方を保持**。raw は「あの時こう言った」の記録、wiki は「現時点でどう整理されているか」の合成
- 含意: 「[Q26](questions/未解決の問い.md)（人間割り込みコメントの扱い）」への一つの解：**人間が raw に書く → AI が ingest → wiki に AI 合成知として反映** という処理サイクルが今回機能した実例

## [2026-05-07] retraction + cleanup | `nishio:` コメントを raw に移して Wiki を AI テキストのみに復元

著者の追加指示「`nishio:` コメントは raw に移し、Wiki は AI が書いたテキストだけの状態に戻せ」を反映：

- 取り消し: [CLAUDE.md](../CLAUDE.md) から「`nishio:` プレフィックス慣習」節を削除（schema 化撤回）
- **移動**: 著者の Q4・Q5 直筆コメントを `raw/2026-05-07-nishio-Q4Q5コメント.txt` に保存（元の挿入位置と文脈付き）
- **削除**: [questions/未解決の問い.md](questions/未解決の問い.md) から `nishio:` 行 2 件を削除し、Wiki を AI 生成テキストのみの状態に復元
- 真の問題は **AI が同一ファイルを編集中に人間がコメントを書きたくなったときどうするか**。これを未解決の問いとして格上げ（→ [Q26](questions/未解決の問い.md)）
- 含意: Wiki と raw の役割分担（CLAUDE.md の 3 層アーキテクチャ）が再確認された。**人間の生コメントは raw、wiki は AI による合成知** という原則を逸脱しない
- 次のセッションで raw → wiki への正規 ingest を行うかは別途判断（Q4・Q5 の substantive 更新候補）

## [2026-05-07] query | Day 15 — Q1 サブトピック「記憶」「やる気」の再フレーミング

- 著者が Q1 で挙げていた書き切れない論点「やる気」「記憶」について、素朴な枠組み自体が LLM 時代に不適切であることを言語化
- 新規ページ:
  - [concepts/想起の設計.md](concepts/想起の設計.md) — 「記憶」を保存と想起に分け、想起側に焦点。LENCHI 第二部の主要概念群を横断する整理
  - [timeline/Day15.md](timeline/Day15.md) — 本セッション
- 更新:
  - [questions/未解決の問い.md](questions/未解決の問い.md) Q1 — 再フレーミングへの参照に書き換え、Q24（記憶=想起の設計）と Q25（プロジェクトが進まない問題）を新設
  - [index.md](index.md) — 想起の設計、Day 15 を登録、active 件数を 22 に更新
- 重要な発見:
  - **本書はすでに「想起の設計」を扱っていた** — 後段としてのWiki / 段階的開示 / ナラティブの価値 / Naive RAG 反省 / フラクタル要約 / 思考の熟成 / コンテキスト維持 はすべて想起設計の各側面
  - 「やる気」概念の解体: 心理資源メタファーが原因（目的不明確 / 道筋不可視 / 認知負荷集中 / 進捗不可視）を隠す。遂行主体は人間とは限らない時代の一般化が必要
- 設計判断:
  - サブトピック再フレーミングは Q24/Q25 として独立化（Q1 内のかっこ書きから昇格）。第一章 / 前書きの章ドラフト見直しの引き金になる
  - 想起の設計を独立概念ページに（既存概念群を束ねるメタ概念として）

## [2026-05-06] schema | 解決済みの問いを別ファイルに分離

- 著者の指摘: 解決したものは解決日時とセットで別のページに移動すべき
- 新規 [questions/解決済みの問い.md](questions/解決済みの問い.md) を作成、Q14・Q16・Q17 を解決日付き（いずれも 2026-05-02）で移動
- [questions/未解決の問い.md](questions/未解決の問い.md) からは Q14・Q16・Q17 を削除（Q 番号は安定識別子なので欠番のまま保持）
- [questions/未解決の問い.md](questions/未解決の問い.md) 冒頭に「アクティブ vs アーカイブの分離」節を追加
- [CLAUDE.md](../CLAUDE.md) のスキーマ記述に分離方針を追記、ディレクトリレイアウトの注記も更新
- [index.md](index.md) で両ファイルを並列に登録、active 件数を 20 に更新
- 設計判断:
  - **部分対応・半解決はアクティブ側に残す**（Q11/Q12/Q20 など、残課題があるため）
  - **Q 番号は両ファイルにまたがって一意**。アーカイブによる欠番は OK（履歴の残し方として番号の連続性より「解決日付きで保存」を優先）
  - Q を「いつ解決したか」が時間軸で navigable になることで、second-class artifact だった解決事例が first-class に昇格

## [2026-05-04] query | Day 14 — 3-Wiki 比較実験と自己観察の fill back

- 著者が同じ問いを 3 Wiki（Karpathy LLM Wiki / ConnectingDots / LENCHI）に並列照会し、差分を 5 観点で分析
- LENCHI Wiki 側で A3 の特徴づけを **自己修正**: 「ingest が新概念ではなく未決 Q 追加として記録される」は不正確 → 正確には「**新概念追加 + 未決 Q 層の状態変化として二重に記録される**」
- 新規ページ:
  - [concepts/Wikiの人格化.md](concepts/Wikiの人格化.md) — wikis-as-personas、手動 orchestrator パターン、5 つの差分観察
  - [timeline/Day14.md](timeline/Day14.md) — 本セッション
- 軽微な更新:
  - [questions/未解決の問い.md](questions/未解決の問い.md) — 冒頭にファイル自体の位置づけ（first-class artifact、二層記録の question layer）を明示
  - [index.md](index.md) — Wikiの人格化、Day 14 を登録
- 設計判断:
  - A3 の特徴づけ修正を Day 14 timeline に記録（自己観察を一級の知的資産として扱う）
  - Wikiの人格化 を独立概念ページに（LENCHI 主題と他 Wiki との対比から、本書全体の理論枠を補強する位置づけ）

## [2026-05-03] ingest | Day 13 — MindTrellis / ConnectingDots / Kozaneba 三者対比

- Source: `raw/2026-05-03-mindtrellis-connectingdots-GPT.txt`（西尾 × ChatGPT GPT-5系の4ラウンド対話、973行）
- 当初 `wiki/concepts/gpt-mindtrellis-connectingdots-20260503.md` として誤配置されていた → `raw/` に改名移動（生対話ログは raw の領分）
- 新規ページ:
  - [timeline/Day13.md](timeline/Day13.md) — 三者対比と5週間アクションプランの記録
  - [concepts/ConnectingDots.md](concepts/ConnectingDots.md) — 西尾自身の並走設計システム。**事実・関係・解釈・物語・表示の4層分離**（Dots/Relations/Stories/Views）。LENCHI Wiki と「同じ問題への別アプローチ」
  - [entities/MindTrellis.md](entities/MindTrellis.md) — 2026年研究システム（arXiv:2604.23129）。AI と人間が同じ知識グラフを共同編集。「AI 生成構造を暫定物として扱う」設計思想
- 軽微な更新:
  - [entities/Kozaneba.md](entities/Kozaneba.md) — 隣接システム MindTrellis / ConnectingDots との関係節を追加。Kozaneba は ConnectingDots の View の一種、独自性は「前言語的な構造化」
  - [concepts/ナラティブの価値.md](concepts/ナラティブの価値.md) — ConnectingDots を「6軸損失問題への別アプローチ」として明示。LENCHI は raw/wiki 二層、ConnectingDots は Story 層で対応
  - [questions/未解決の問い.md](questions/未解決の問い.md) — Q19 に MindTrellis を追加、Q23（ConnectingDots プロジェクトと LENCHI Wiki の連動）を新設
  - [index.md](index.md) — 新概念1件、新エンティティ1件、Day 13、新 raw ファイルを登録、外部研究カテゴリを新設、問い数を 23 に更新
- 設計判断:
  - **MindTrellis をエンティティ化**: 特定の研究システムでありエンティティページが妥当（[Q19](questions/未解決の問い.md) で挙げた他の研究 RAG / ReAct / MemGPT 等は概念ページ内の言及のみだが、MindTrellis は LENCHI と接続点が深い）
  - **ConnectingDots を概念ページに**: 西尾の設計思想であり実装はこれから。エンティティ（実体）ではなく設計パターン
  - **5週間アクションプラン自体は ingest しない**: LENCHI 側で週次追跡するかは [Q23](questions/未解決の問い.md) で著者と要否を判断

## [2026-05-03] lint | Day 12 後の Wiki 健康診断と前向き整備

実施項目: 孤児ページ、古い主張、欠落概念、章ドラフトの「次にやるべきこと」鮮度、未解決の問い更新状況。

### 発見

- **A. 孤児ページなし** — 全 19 概念・14 エンティティが最低 4 件の incoming reference。
- **B. 古い主張**: index.md の現行モデル分類で 2024/2026 区分が弱い。発散と収束.md の「課題」節が時系列読みにくい。KJ法とLLM.md の GPT-4o 観察は 2024 年のままで Q10 関連。第二章.md の Naive RAG 構想が Day 12 Session B/C の Modern RAG への構造変化を反映していない。
- **C. 欠落概念**: **Claude Code** が頻出するが独立エンティティページなし。Plurality / ブロードキャスティングは独立化不要（既存集約で十分）。
- **D. 章ドラフト鮮度**: 前書き・第一章・第二章の「残課題」が Day 12 進展を反映していない。第二部 導入章の見取り図は更新済み。
- **E. 未解決の問い**: 最新（直近で Q14/16/17 解決、Q15/19/20/21/22 新設、Q3/Q4 に LLM Wiki 追加）。

### 実施した整備

1. 新規 [entities/ClaudeCode.md](entities/ClaudeCode.md) — Skills / CLAUDE.md / auto memory / memory tool / filesystem access を時系列で整理、LLM Wiki の先行的実装として位置づけ、NISHIOアシスタントとの対比、関連概念へのリンク。
2. [index.md](index.md) — 2024 期モデル群に「歴史記録として保存」注記、2026 現行モデルを「第二部以降の主役」に改名、新カテゴリ「エージェント基盤」を追加し Claude Code を登録。
3. [chapters/第二章.md](chapters/第二章.md) — 残課題冒頭に「構造的な再考が必要」の Lint 注記を追加、節 3 を NISHIO アシスタント＋Claude Code + Wiki の二段構成に書き換え、節 5 に [後段としてのWiki](concepts/後段としてのWiki.md)・[段階的開示](concepts/段階的開示.md) を追記。
4. [chapters/前書き.md](chapters/前書き.md) と [chapters/第一章.md](chapters/第一章.md) — 残課題に Day 12 進展への接続項目（[Q13](questions/未解決の問い.md) / [Q15](questions/未解決の問い.md)）を追加。
5. [concepts/発散と収束.md](concepts/発散と収束.md) — 「何が課題か」節を 2024 年期の観察として明示し、5 候補をそれぞれ年代タグ付きに整理。
6. 本 Lint 結果を log.md に記録（このエントリ）。

### 設計判断

- 2024 年期の章ドラフト本文（前書き・第一章・第二章の本文部）は **書誌的事実として保存** し更新しない。残課題セクションのみ Lint 注記を追加。
- Plurality は独立エンティティ化しない。本書主題から外れるため [デジタル民主主義](entities/デジタル民主主義.md) と [ブロードリスニング](concepts/ブロードリスニング.md) 内の集約で十分。

## [2026-05-02] query | NISHIO アシスタントと Claude Code + LLM Wiki を「同じ機能の別実装」として位置づけ

- 著者の指摘: 「NISHIO アシスタントの『特化した記憶を持って話し相手になる』性質も、LLM Wiki とセットになった Claude Code によって実現されている」
- 整理: 両者は **同じ機能の別実装**。NISHIO アシスタントは **Naive RAG 型**、Claude Code + LLM Wiki は **段階的開示型**。これは Day 12 Session B の「Naive RAG → Modern RAG」構造変化が個人知識アシスタントにも当てはまる構図
- 更新:
  - [questions/未解決の問い.md](questions/未解決の問い.md) Q4 — 中間層の 2 選択肢（A: NISHIO アシスタント、B: Claude Code + LLM Wiki）を明示
  - [entities/NISHIOアシスタント.md](entities/NISHIOアシスタント.md) — 別実装としての Claude Code + LLM Wiki を比較表で対比、発散用の窓口としての継続価値と、著者自身の知的生産パートナーとしての主役交代を整理
  - [concepts/有限化と無限ネットワーク.md](concepts/有限化と無限ネットワーク.md) — 「接続装置の進化」節を追加。2024 年 vs 2026 年の中間層を比較

## [2026-05-02] query | LLM Wiki を Q3（収束支援）の第 4 候補として位置づけ

- 著者の指摘: 「この収束支援は現状 LLM Wiki がとても有望」
- [Q3](questions/未解決の問い.md) の解候補に LLM Wiki を **第 4 候補（現状もっとも有望）** として追加
- [concepts/発散と収束.md](concepts/発散と収束.md) に「LLM Wiki による収束支援」節を新設。三段構えで整理：
  1. 概念抽出そのものが収束操作
  2. 段階的開示で overview ↔ 詳細の往復
  3. 後段としての Wiki が並列発散を時間をかけて吸収・収束
- 従来の 4 候補（コンテキスト幅／フラクタル要約／KJ法／Kozaneba）との関係を「Wiki がそれらを **束ねるメタ装置**」として整理
- [chapters/第二部-LLM_Wikiの導入.md](chapters/第二部-LLM_Wikiの導入.md) の見取り図に「収束支援装置としての LLM Wiki」節を追加候補として登録

## [2026-05-02] ingest | Day 12 Session C — Q14・Q17 解決、ナラティブの価値 言語化

- Sources: 3 ファイル
  - `raw/nishio-激動の2024年5月下旬.1hop.txt`（27ページ）— Q14 補強
  - `raw/blu3mo-fractal_reader.2hop.txt`（10ページ）— Q17 補強
  - `raw/nishio-直線的でない時間.1hop.txt`（10ページ）— 思考の熟成 補強、ナラティブの価値 発見
- Q14 を **解決**: ブロードリスニング本そのもののプロセスログは混ぜない、付随 Wiki と「情報処理」誌寄稿は参照対象
- Q17 を **解決**: Fractal Reader システム実体・コスト構造・派生構想（非対称なエディタ）を反映
- 新規ページ:
  - [concepts/ナラティブの価値.md](concepts/ナラティブの価値.md) — wiki化で失われる6次元（暗黙知／順序／動機／記憶／共感／意味の生成）。**LENCHI の `raw/` + `wiki/` 二層分離設計の理論的根拠** として位置づけた
  - [concepts/ブロードリスニング.md](concepts/ブロードリスニング.md) — 集団における知的生産性向上。LENCHI 主題の集団版
  - [entities/ブロードリスニング本.md](entities/ブロードリスニング本.md) — 並走中の別書籍プロジェクト（2026-09 出版予定）
  - [timeline/Day12.md](timeline/Day12.md) Session C — 本セッションの記録
- 大幅更新:
  - [concepts/フラクタル要約.md](concepts/フラクタル要約.md) — Fractal Reader 実体・アルゴリズム・コスト・派生構想（非対称なエディタ）
  - [entities/青山柊太朗.md](entities/青山柊太朗.md) — Fractal Reader 運営の「経営者は意思決定が仕事」体験的気づき、ブロードリスニング本への共著関与
  - [entities/デジタル民主主義.md](entities/デジタル民主主義.md) — 中断動機の詳細タイムライン（2024-05-13〜2024-07-25）
  - [entities/西尾泰和.md](entities/西尾泰和.md) — システム理解力の系譜に「集団スケール」（階層組織 2018 → 個人情報とマネタイズ 2019 → LLMがもたらす組織構造の変化 2023 → ブロードリスニング 2024）を追加
  - [concepts/思考の熟成.md](concepts/思考の熟成.md) — ジェンドリン哲学のシータ図、主体客体交換、ストーリーの交差点で機構を補強
- 軽微な更新:
  - [chapters/第二部-LLM_Wikiの導入.md](chapters/第二部-LLM_Wikiの導入.md) — 見取り図に「ナラティブの価値と二層分離」節を追加
  - [questions/未解決の問い.md](questions/未解決の問い.md) — Q14・Q17 を解決に格下げ、Q21（個人/集団の知的生産の橋渡し）と Q22（ブロードリスニング本付随 Wiki の比較取り込み）を新設
  - [index.md](index.md) — 新概念2件、新エンティティ1件、Day 12 Session C、新 raw 3ファイルを登録、問い数を 22 に更新
- 重要な発見: **ナラティブの価値の 6 次元整理が、LENCHI の `raw/` 改変禁止原則の事後的根拠を提供する**。これは Karpathy の LLM Wiki への重要な批評的補足として第二部本論で扱う価値がある（→ [chapters/第二部-LLM_Wikiの導入.md](chapters/第二部-LLM_Wikiの導入.md) に節を予約）
- 設計判断:
  - 「ストーリーの交差点がアトムになる」は独立ページにせず [思考の熟成](concepts/思考の熟成.md) の機構補強として記述（同一の機構に対する別表現と判断）
  - 安野貴博、関治之、Audrey Tang、tokoroten 等の人物は独立エンティティページにせず [デジタル民主主義](entities/デジタル民主主義.md) と [ブロードリスニング](concepts/ブロードリスニング.md) のタイムライン内で言及（LENCHI の主題と直接関係しないため）

## [2026-05-02] ingest | Day 12 Session B — Q16 検証（GPT 5.5 Pro サーベイ）

- Source: `raw/2026-05-02-Q16検証-GPT.txt`（西尾 × ChatGPT GPT-5系の3ラウンド対話、当初 `a.txt` として置かれ後に改名）
- 動機: [Day 12](timeline/Day12.md) で残した [Q16](questions/未解決の問い.md)（Karpathy LLM Wiki の歴史的位置づけ検証）への回答が得られた
- Q16 を **解決（概ね妥当・条件付き）** に格下げ
- 新規ページ:
  - [timeline/Day12.md](timeline/Day12.md) Session B — Q16 検証セッションの記録
  - [concepts/段階的開示.md](concepts/段階的開示.md) — Progressive Disclosure。Nielsen / Shneiderman の HCI 原理から Skills、LLM Wiki までの系譜を整理。本書の中心概念に格上げ
- 大幅更新:
  - [concepts/RAG.md](concepts/RAG.md) — Naive RAG とそのバックラッシュ、Advanced/Modular RAG、Contextual Retrieval、LLM Wiki / Claude Code との関係を新節として追加
  - [concepts/コンテキスト維持.md](concepts/コンテキスト維持.md) — Karpathy 帰属節を Day 12 Session B 検証済みの精密版に置き換え（API memory tool / Skills / auto memory の時系列訂正を含む）
  - [chapters/第二部-LLM_Wikiの導入.md](chapters/第二部-LLM_Wikiの導入.md) — 「Karpathy 帰属の補正」節を検証済みの内容に差し替え。本論見取り図に「段階的開示と外部記憶の系譜」節を追加
- 軽微な更新:
  - [concepts/フラクタル要約.md](concepts/フラクタル要約.md) — 段階的開示への接続を関連概念に追加
  - [questions/未解決の問い.md](questions/未解決の問い.md) — Q16 を解決に格下げ、Q19（外部記憶研究系譜の本文組み込み）と Q20（raw ファイル命名規約）を新設
  - [index.md](index.md) — 段階的開示、Day 12 Session B、新 raw ファイルを登録、問い数を 20 に更新
- 設計判断:
  - 「filesystem access の進歩がソースコード領域から需要を生んだ」という著者の重要観察は、独立ページではなく [段階的開示](concepts/段階的開示.md) 内の一節として記録（系譜の枝として位置づくため）
  - 研究文献（A-MEM、Lost in the Middle、Contextual Retrieval 等）は Wiki に名前だけ記録し、各論文の本格的読解は別 ingest として Q19 に登録

## [2026-05-02] ingest | 青山柊太朗（blu3mo）のプロフィール、フラクタル要約帰属の正確化

- Source: `raw/blu3mo-自分について2024.1hop.txt`（Scrapbox `自分について2024` 中心の1-hopエクスポート、15ページ）
- 動機: 直前の Day 12 ingest で著者は [フラクタル要約](concepts/フラクタル要約.md) のオリジネーターを「青山君」と言及。エージェントが下の名前を「諒」と推測して記載したのは誤り。本資料により **青山柊太朗（あおやま しゅうたろう / blu3mo / Bluemo）** であると確定。
- 新規ページ: [entities/青山柊太朗.md](entities/青山柊太朗.md) — Columbia大CS+哲学副専攻、孫正義育英財団1期、IPA未踏2020、柳井正財団6期生、国立情報学研究所「情報科学の達人」1期。研究テーマ "Asymmetric Reality"。情報科学の達人時代に Saliencyを用いた授業映像要約の研究を行っており、フラクタル要約の系譜が確認できる。
- 修正:
  - [concepts/フラクタル要約.md](concepts/フラクタル要約.md) — 「青山（諒）」を「青山柊太朗（blu3mo）」に修正、エンティティへリンク、研究系譜（Saliency要約→フラクタル要約）を追記
  - [timeline/Day12.md](timeline/Day12.md) — 同様に修正（2か所）
  - [questions/未解決の問い.md](questions/未解決の問い.md) Q17 — 同様に修正、青山の Scrapbox を入口とする取り込み手順を補足
  - [index.md](index.md) — 人物に青山柊太朗を追加、raw 資料に新ファイルを登録
- 設計判断: 青山の研究テーマ全体（Asymmetric Reality / Kineto / asym-chat / 弾性同期）は LENCHI の主題と思想的に隣接するが、本書プロジェクトに直接素材として取り込むものではないため、エンティティページ内の「LENCHIと思想的に交差する点」節で接続点だけ明示する形に留めた。

## [2026-05-02] ingest | Day 12 — Wiki初読・並列実行・概念の再定義

- Source: `raw/2026-05-02.txt`（著者が Wiki を新幹線で初通読しながら書いたメモ）
- 新規ページ:
  - [timeline/Day12.md](timeline/Day12.md)
  - [concepts/後段としてのWiki.md](concepts/後段としてのWiki.md) — Wikiを下流に置くことで上流の探索が並列化される
  - [concepts/思考の熟成.md](concepts/思考の熟成.md) — 「放置」ではなく異経路で同じ場所に辿り着くことが熟成の機構
- 更新ページ:
  - [concepts/フラクタル要約.md](concepts/フラクタル要約.md) — 青山（当初「諒」と誤記、後の ingest で **青山柊太朗 / blu3mo** と訂正）のアイデアであるという出典追加。一般AI要約との対比考察を取り込み候補に
  - [concepts/コンテキスト維持.md](concepts/コンテキスト維持.md) — Karpathyの位置づけを「単発発明」から「漸進的有用化の言語化」に補正、Claude Code Skills が早期形態という補助仮説を追加、後段としてのWikiへの接続
  - [concepts/LLM時代の知的生産.md](concepts/LLM時代の知的生産.md) — 「人間×AI協働」前提を明示し、AI単独完結時代に「趣味としての知的生産本」が残る可能性を追加
  - [concepts/創発的アプローチ.md](concepts/創発的アプローチ.md) — 思考の熟成へのリンク追加
  - [entities/デジタル民主主義.md](entities/デジタル民主主義.md) — 中断動機の補足（ブロードリスニング＝集団の知的生産性向上）
  - [entities/西尾泰和.md](entities/西尾泰和.md) — システム理解力の系譜（プログラム挙動→言語→言語史→知的生産→LLM時代）
  - [chapters/第二部-LLM_Wikiの導入.md](chapters/第二部-LLM_Wikiの導入.md) — 「後段としてのWiki」節と「Karpathy帰属の補正」節を追加
  - [overview.md](overview.md) — 「プロジェクトの性格」節を新設（書籍プロジェクトという呼称の不正確さの明示、改訂版10年後の想定）
  - [questions/未解決の問い.md](questions/未解決の問い.md) — Q14を「部分再開」に格上げ（情報処理原稿の取り込み候補化）。Q15（人間×AI前提の妥当性）、Q16（Karpathyの歴史的位置づけ検証）、Q17（青山のフラクタル要約考察取り込み）、Q18（後段としてのWikiの実例化）を新設
  - [index.md](index.md) — 新概念2件、Day 12、新raw資料を登録
- 設計判断: 著者の「概念ページが面白い／他人の視線での整理」観察は独立ページ化せず、Day 12 のキー観察として記録（Wiki読書の固有価値の論点だが、概念として取り出すには未成熟）

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
