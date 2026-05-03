# Claude Code

Anthropic のターミナルベース・コーディングエージェント。2025 年 2 月の research preview を起点に、**Skills / CLAUDE.md / auto memory / memory tool / filesystem access** といった機能群が積み上がり、結果として **長期プロジェクトの外部記憶を保守・利用するエージェント** になった。本書プロジェクト LENCHI 自身が Claude Code 上で運用されている。

## プロジェクトでの役割

- **本書プロジェクト LENCHI 自身の運用基盤**。`raw/` を読み、`wiki/` を編集し、`CLAUDE.md` のスキーマに従って ingest / query / lint を回す主体。
- [Karpathy の LLM Wiki](../../llm-wiki.md) の **先行的な実装** として位置づけられる（[Day 12 Session B](../timeline/Day12.md) のサーベイ検証）。Karpathy 自身は wiki という抽象化を提唱したが、Claude Code は機能の総体としてそれに近い運用を可能にしていた。

## 主要構成要素（時系列順）

| 時期 | 要素 | 役割 |
| --- | --- | --- |
| 2024-11-25 | Anthropic MCP 発表 | 外部システム接続の標準プロトコル |
| 2025-02-24 | Claude Code research preview | bash + file editing tool を使うコーディングエージェント |
| 2025-09-29 | API memory tool beta | 会話をまたいで情報保存・参照（**Skills より前**） |
| 2025-10-16 | Agent Skills / Claude Code Skills | instructions・scripts・resources を [段階的開示](../concepts/段階的開示.md) で読み込む |
| 2026-02-05 | Claude Code auto memory 初期 | 作業中の文脈を自動保存・想起（**Skills より後**） |
| 2026-02-26 | auto-memory 明示化 | `/memory` で管理 |
| 2026-03-12 | `autoMemoryDirectory` 設定追加 | auto memory の保存先指定 |

「memory tool」と「auto memory」は別物として扱う必要がある（Day 12 Session B での訂正）。

## 設計原理

- **filesystem access** — `grep`/`glob`/`read`/`bash` で必要時にファイルを探索。ソースコードがもともとファイルシステム上に構造化されていた事実が、この方式の実用化を強く後押しした（[Day 12 Session B](../timeline/Day12.md) の著者観察）。
- **[段階的開示](../concepts/段階的開示.md)（Progressive Disclosure）** — Skills は metadata → SKILL.md → resources/scripts の三段階。常時ロードは name/description だけ。
- **CLAUDE.md による永続スキーマ** — プロジェクトごとに「振る舞いの規約」を Markdown で書き、起動時に常時読み込まれる。LENCHI の `CLAUDE.md` はこの仕組みを利用して 3 層アーキテクチャと運用フロー（ingest / query / lint）を定義している。

## NISHIO アシスタント との対比

「特化した記憶を持って話し相手になる」という機能は、2024 年は [NISHIOアシスタント](NISHIOアシスタント.md)（カスタムGPT、Naive RAG）で実現されていた。2026 年には Claude Code + [LLM Wiki](../../llm-wiki.md) が **同じ機能の別実装**（[段階的開示](../concepts/段階的開示.md) 型）として成立した（[Q4](../questions/未解決の問い.md)、[NISHIOアシスタント](NISHIOアシスタント.md) 内の比較表参照）。

これは [Day 12 Session B](../timeline/Day12.md) で整理した「Naive RAG → Modern RAG」の構造変化が、個人知識アシスタントの設計にもそのまま当てはまる例。

## 関連エンティティ・概念

- [Claude4系](Claude4系.md) — Claude Code の中で動く現行モデル群（Opus 4.7、Sonnet 4.6 等）
- [後段としてのWiki](../concepts/後段としてのWiki.md) — Claude Code 上で初めて実用に耐える運用が成立した
- [段階的開示](../concepts/段階的開示.md) — 中核設計原理
- [コンテキスト維持](../concepts/コンテキスト維持.md) — Claude Code は構造解の実装担当
- [RAG](../concepts/RAG.md) — Modern RAG / agentic retrieval の文脈で対比される

## 出典

- raw: `2026-05-02-Q16検証-GPT.txt`（[Day 12 Session B](../timeline/Day12.md) の GPT 5.5 Pro サーベイ）
- 公式: Anthropic "Effective context engineering for AI agents"、"Equipping agents for the real world with Agent Skills"、Claude Code docs（changelog 含む）
