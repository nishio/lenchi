# GPT-5 系（OpenAI, 2025-2026）

[OpenAI](https://openai.com/) の現行フロンティアモデル世代。

## リリース時系列

- **2025-08-07** **GPT-5** — 高速モデル・深い推論モデル・両者を切り替えるリアルタイムルーターの3層システム。コーディング、数学、ライティング、ヘルス、視覚知覚など広範に大幅向上。
- **2025-12-11** GPT-5.2 — 「専門知識業務向けに最も有能」と位置づけ。スプレッドシート作成、プレゼン資料、長コンテキスト、ツール使用、複数ステップのプロジェクトに改善。
- **2026-04-23** **GPT-5.5** ← 本 Wiki 構築時点で最新フロンティア。Greg Brockman が「a new class of intelligence」と紹介。Pro 版も同時。

## LENCHI にとっての含意

- [GPT-4 / o1 系](ChatGPT.md)（2024 年期の観察対象）からの主な変化:
  - **ルーター方式**: GPT-5 のシステム構成（高速モデル + 推論モデル + ルーター）は、[発散と収束](../concepts/発散と収束.md) のモデル使い分けを **モデル内部** で吸収する設計。これは LENCHI が外部から行っていた使い分けの一部を不要にする。
  - **ツール使用と長コンテキスト**の強化により、[NISHIOアシスタント](NISHIOアシスタント.md) のような RAG カスタムアプリの作り直しの動機になりうる（[未解決の問い Q12](../questions/未解決の問い.md)）。
  - 2024 年期に観察された GPT-4 の「脱線傾向」はルーター方式と長コンテキストで緩和されている見込み。
- 一方で、本 Wiki の編集・対話には現状 [Claude 4 系](Claude4系.md) を主に使用。GPT-5 系を併用するかは [西尾](西尾泰和.md) の選択。

## 出典

- [Introducing GPT-5 \| OpenAI](https://openai.com/index/introducing-gpt-5/)
- [Introducing GPT-5.2 \| OpenAI](https://openai.com/index/introducing-gpt-5-2/)
- [OpenAI launches GPT-5.5 — The New Stack](https://thenewstack.io/openai-launches-gpt-5-5-calling-it-a-new-class-of-intelligence/)
- [OpenAI releases GPT-5.5 — TechCrunch](https://techcrunch.com/2026/04/23/openai-chatgpt-gpt-5-5-ai-model-superapp/)

Sources:
- [Introducing GPT-5 \| OpenAI](https://openai.com/index/introducing-gpt-5/)
- [Introducing GPT-5.2 \| OpenAI](https://openai.com/index/introducing-gpt-5-2/)
- [OpenAI launches GPT-5.5, calling it "a new class of intelligence" — The New Stack](https://thenewstack.io/openai-launches-gpt-5-5-calling-it-a-new-class-of-intelligence/)
