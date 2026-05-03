# 第二部 導入 — LLM Wiki を記憶として知的生産を再起動する

- 完成度: **40%**（解説の初稿、2026-05-01）
- 著者: [西尾泰和](../entities/西尾泰和.md)
- ステータス: 第二部の起点となる解説。執筆を進めるうちに前後の節が立ち上がる想定（[創発的アプローチ](../concepts/創発的アプローチ.md)）

## この章の位置づけ

本書 LENCHI は 2024 年 4 月に着手し、同年 12 月の [Day 10](../timeline/Day10.md) を最後に休止していた。約 1 年半の中断を経て、本日 **2026-05-01** に再起動する。
中断の主な理由は、著者が並走していた [デジタル民主主義](../entities/デジタル民主主義.md) の推進活動に時間を割いていたためである。その活動は一段落し、関連する書籍を別途執筆中で **2026 年 9 月に出版予定** となった。LENCHI を再び動かす条件が整ったので、ここで再起動する。

第二部はこの再起動と同時に開く。第一部（[前書き](前書き.md)・[第一章](第一章.md)・[第二章](第二章.md)・[講演](講演.md)）が **「LLM 時代の知的生産という問いの提示」** だったとすれば、第二部はその問いに **長期プロジェクト運用という側面から答える** 本論である。中心には、Andrej Karpathy が言語化した **LLM Wiki** というパターンの導入がある。

## なぜ LLM Wiki なのか — 2024 年に欠けていたもの

[Day 1](../timeline/Day1.md) から [Day 10](../timeline/Day10.md) までを振り返ると、**コンテキストが失われ続ける** という問題が一貫して現れていた。

- [Day 2](../timeline/Day2.md) ではコンテキスト圧迫で前段の合意が忘れられた。
- [Day 3 再起動](../timeline/Day3.md) で「次の LLM に引き継ぐべき記憶」をリスト化する習慣ができた。
- [Day 6](../timeline/Day6.md) では、別の Claude インスタンスに会話を要約させて本体に戻すという中継術にまで発展した。
- そして [Day 10](../timeline/Day10.md) では、過去原稿全体を **[o1 pro](../entities/o1pro.md)** に渡して総合振り返りをさせた。これは事実上「半年分の記憶を一度に注入する」運用であり、毎回やるには重い。

私はその場しのぎの引き継ぎ資料を毎回つくっていた。これらはすべて、後から見ればひとつの欠けたピースを補おうとしていた——**プロジェクトの記憶を、セッションをまたいで、増分的に積み上げ、永続化させる仕組み**。

Karpathy の [LLM Wiki](../../llm-wiki.md) は、まさにこの欠落への解として読める。

> Instead of just retrieving from raw documents at query time, the LLM **incrementally builds and maintains a persistent wiki** … The knowledge is compiled once and then *kept current*, not re-derived on every query.

毎回ゼロから検索・統合する RAG と違い、LLM が **書き続ける Wiki** が一次資料と質問の間に挟まる。クロスリファレンスはすでに張られている。矛盾はすでに記録されている。新しい資料を投入しても、Wiki に **積み上がる**。

## 本書の主題との一致

このパターンは、本書の核となる主張——**LLM はパートナーであって道具ではない**——と切れ目なく接続する。Karpathy は次のように書いている：

> Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass. The wiki stays maintained because the cost of maintenance is near zero.

人間が放棄する **「面倒な手入れ」** こそが LLM の引き受ける部分だ、という構図である。これは私の以前からの主張（[エンジニアの知的生産術](../entities/エンジニアの知的生産術2018.md) における「中断可能な設計」「学びのサイクル」）と整合する。**人間が決めるのは、何を読むか・何を問うか・何を意味づけるか**。それ以外のクロスリファレンスや要約整備は LLM が回す。

私自身は [Scrapbox](../entities/Scrapbox.md)（現 Cosense）を 7 年運用し、約 2 万記事の蓄積を持つ。そこには **[社会的トリガー](../concepts/社会的トリガー.md)** によって過去の自分と再会する仕組みが組み込まれている。LLM Wiki は同じ思想を、**LLM が書き手・読み手の両方** をやる形に拡張したものだ。Scrapbox がリンク特化の記法でネットワーク化を加速したように、LLM Wiki は LLM の編集力で同じネットワークを **生かし続ける**。

## 何が変わるか

具体的に、再起動後の運用は次のように変える。

1. 新しい資料は `raw/` に置き、LLM がそれを Wiki の既存ページに **統合** する。要約だけでなく、関連エンティティ・概念ページの更新と、矛盾点の明示を伴う。
2. 私（西尾）が問いを投げると、LLM は Wiki から答え、**その答えそのものも Wiki ページに加える**。質問・比較・新たな発見は揮発させず、知識ベースに沈殿させる。
3. 各 Day の最後に作っていた「引き継ぎ資料」は、この Wiki そのものに置き換わる。引き継ぎは **常時** 行われる。
4. [Obsidian](https://obsidian.md/) でグラフ・リンク辿りを行い、LLM 側は CLI またはエディタ内エージェントとして編集する（[llm-wiki.md](../../llm-wiki.md) のワークフロー）。

## 第二部で書くこと

第二部のおおまかな見取り図は次のようになる。本章はその導入で、後続節は [Day 11 以降](../timeline/Day11.md) で執筆する：

- **本章（導入）** — LLM Wiki を導入する判断と、その理由
- **記憶の3層構造** — `raw/` / `wiki/` / `CLAUDE.md` の役割分担。なぜこれが [コンテキスト維持](../concepts/コンテキスト維持.md) への根本解になるか
- **[ナラティブの価値](../concepts/ナラティブの価値.md) と二層分離** — wiki化は 6 軸のうち 4〜5 軸を犠牲にして「参照可能性」を得る変換である。だから `raw/`（ナラティブ保存・改変禁止）と `wiki/`（概念抽出）の二層分離が必要。Karpathy LLM Wiki への重要な批評的補足
- **[段階的開示](../concepts/段階的開示.md) と外部記憶の系譜** — Nielsen / Shneiderman の HCI 原理から、RAG / Generative Agents / MemGPT / Voyager / A-MEM、Skills、LLM Wiki まで。**Naive RAG への反省**（[RAG](../concepts/RAG.md)）を経て段階的開示の必要性が浮上した経緯
- **Ingest の作法** — 新しい資料を読ませ、既存ページに統合させる手順。[ニーズ駆動の生成](../concepts/ニーズ駆動の生成.md) と接続
- **Query の作法** — 答えを揮発させない。Wiki への沈殿が複利で効く
- **Lint の作法** — LLM 自身に Wiki の健康診断をさせる。孤児ページ・矛盾・欠落の検出
- **[後段としてのWiki](../concepts/後段としてのWiki.md) — Wiki が下流にあることが上流の探索を並列化する** — [Day 12](../timeline/Day12.md) で言語化された節。ChatGPT Pro × LLM Wiki の組み合わせを実例に
- **収束支援装置としての LLM Wiki**（[発散と収束](../concepts/発散と収束.md) [Q3](../questions/未解決の問い.md) への回答）— 概念抽出そのものが収束操作、段階的開示で overview↔詳細の往復、後段としての Wiki が並列発散を時間をかけて吸収。従来の 4 候補（コンテキスト幅／フラクタル要約／KJ法／Kozaneba）を **束ねるメタ装置** として位置づけ
- **Wiki と書籍の関係** — 有限化された書籍が、背後の無限ネットワークと LLM Wiki に読者を接続する設計（[有限化と無限ネットワーク](../concepts/有限化と無限ネットワーク.md)）

[Day 10](../timeline/Day10.md) で [o1 pro](../entities/o1pro.md) が提案した **「実践可能なガイドライン」** への落とし込みは、第二部全体を貫く方針として採用する。

## Karpathy の貢献の正しい位置づけ（[Day 12](../timeline/Day12.md) Session A で提起、Session B で検証）

本章は便宜上「Karpathy が言語化したパターン」の導入として書いているが、このパターンは **彼一人の発明ではない**。LLM が賢くなったこととコンテキスト幅が広くなったことによって、ある種のやり方の有用性がジワジワと上がってきた——その到達点を彼が綺麗に言語化した、という認識のほうが正確である。

[Day 12 Session B](../timeline/Day12.md) に [GPT-5 系](../entities/GPT-5系.md) でサーベイ検証した結果、より精密な版はこうなる：

> **Claude Code の filesystem access と coding agent 需要が、「ファイルを外部記憶として置き、grep/glob/read/bash で必要時に探索する」運用を自然に育てた。Skills はその上に、metadata → SKILL.md → scripts/resources という明示的な [段階的開示](../concepts/段階的開示.md) を与えた。auto memory はその後、Claude Code 内で作業文脈を自動保存・想起する方向に進んだ。一方、API memory tool は Skills より少し前に出ており、これは Claude Code auto memory とは分けて扱うべきである。Karpathy の LLM Wiki は、これらの流れを知識管理・wiki 保守に寄せた統合形として理解できる。**

着目点：

- Karpathy の LLM Wiki は **意味知識・出典付き統合知識** の外部化、Claude Code Skills は **手続き知識・作業手順** の外部化、というように **目的物が違う**。共通するのは「必要時だけ読む [段階的開示](../concepts/段階的開示.md)」という設計原理。
- ソースコードが先に **ファイルシステム上に構造化されていた** ことが、外部記憶＋探索パターンを実用化した。文書知識（LLM Wiki）も Markdown + ディレクトリへ寄せることで同じ恩恵を受ける。
- 長コンテキスト化だけでは解けない（Lost in the Middle）。**よいインデックス + 必要時に深く読む** の組み合わせが本質。

本書は LLM Wiki を「現時点での最良の言語化」として採用するが、**手法そのものの起源を 2025 年の Karpathy に帰属させると歴史認識を歪める**点に注意する。研究系譜（RAG → ReAct → Reflexion → MemGPT → Generative Agents → Voyager → A-MEM）は本書の本論で参照する。

## 出典・参照

- 元パターン: [llm-wiki.md](../../llm-wiki.md)（Andrej Karpathy）
- 関連概念: [コンテキスト維持](../concepts/コンテキスト維持.md)、[創発的アプローチ](../concepts/創発的アプローチ.md)、[社会的トリガー](../concepts/社会的トリガー.md)、[有限化と無限ネットワーク](../concepts/有限化と無限ネットワーク.md)
- 並走プロジェクト: [デジタル民主主義](../entities/デジタル民主主義.md)
- 再起動の経緯: [Day 11](../timeline/Day11.md)
