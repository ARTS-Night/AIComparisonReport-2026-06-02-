# AIコーディングツール・チャットサービス 究極包括比較レポート (2026年6月版)

本レポートは、2026年6月時点におけるAIコーディングツールおよびチャットサービスの最新情報を網羅し、各サービスの料金体系、利用制限、API連携、VS Code等のエディタ拡張機能への対応状況を詳細に分析したものです。

**※本レポート内の日本円表記は、1ドル = 150円で換算した目安の金額です。**

## 1. 総合比較表（主要ツール全30種以上）

市場の主要なツールをカテゴリ別に整理しました。

| サービス名 | カテゴリ | 月額料金 (USD) | JPY換算 (150円) | 主なモデル | API / BYOK | VS Code対応 | 主な特徴 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Cursor** | 独立IDE | $20 / $60 / $200 | 3,000 / 9,000 / 30,000 | Claude 4.x, GPT-5.x | BYOK一部 | フォーク版 | Agentic体験最高、Composer機能 [1] |
| **Windsurf** | 独立IDE / 拡張 | $15〜20 / Max $200 | 2,250〜3,000 / 30,000 | Claude 4.x, GPT-5.x | BYOK対応 | **公式拡張あり** | Cascade Agent自律性高、Tab無制限、VS Codeフォーク版もあり [2] |
| **Zed Pro** | 独立IDE | $10 | 約1,500円 | Claude 4.x, GPT-5.x | BYOK強力 | 連携可能 | Rust製超高速、Edit Prediction [3] |
| **Antigravity** | 独立IDE | 無料〜$20 | 無料〜3,000円 | Gemini 3.x, Claude 4.6 | BYOK一部 | 不可 | Google製、巨大コンテキスト、並列Agent [4] |
| **Trae** | 独立IDE | $3〜$30 | 450〜4,500円 | Claude/GPT/DeepSeek | BYOK対応 | 不可 | ByteDance製、高コスパ、アダプティブAI [5] |
| **GitHub Copilot** | 拡張機能 | $10 / $39 / $100 | 1,500 / 5,850 / 15,000 | GPT-5.x, Claude | あり | **公式** | **2026/6よりAI Credits制へ完全移行** [6] |
| **Claude Code** | CLI/Agent | $20〜$200 | 3,000〜30,000円 | Claude 4.x (Opus) | API別 | 連携可能 | 推論・大規模コードベース最強 [7] |
| **OpenAI Codex** | 拡張/Platform | $20 / $200〜 | 3,000 / 30,000円〜 | GPT-5.5シリーズ | API提供 | **公式** | Multi-agent、クラウドサンドボックス [8] |
| **Aider** | CLI | 無料 (BYOK) | 無料 (API課金) | 多モデル対応 | BYOK必須 | ターミナル | Git自動コミット最強、CLIの決定版 [9] |
| **Cline / Roo Code** | 拡張機能 | 無料 (BYOK) | 無料 (API課金) | 500+モデル | BYOK必須 | **公式** | Plan & Act Agent、オープンソース最強 [10] |
| **Kilo Code** | 拡張機能 | 無料 (BYOK) | 無料 (API課金) | 500+モデル | BYOK必須 | **公式** | コンテキスト制御に強い新興拡張 [11] |
| **Continue.dev** | 拡張機能 | 無料 (BYOK) | 無料 (API課金) | 多モデル対応 | BYOK必須 | **公式** | カスタマイズ性高、企業向け共有機能 [12] |
| **SuperMaven** | 拡張機能 | $10 | 約1,500円 | 独自モデル | BYOK一部 | **公式** | 100万トークン、超低遅延補完 [13] |
| **Tabnine** | 拡張機能 | $12〜$39 | 1,800〜5,850円 | 独自+多モデル | BYOK対応 | **公式** | プライバシー・オンプレミス重視 [14] |
| **Amazon Q** | 拡張機能 | $19 | 約2,850円 | 独自モデル | あり | **公式** | AWS統合、セキュリティスキャン [15] |
| **DeepSeek** | API/チャット | 基本無料 (従量) | 無料 (従量) | V4 Pro, Coder | OpenAI互換 | 連携可能 | **コスパ最強**、コーディング能力高 [16] |
| **OpenCode Go** | API/CLI | $10 (初月$5) | 1,500円 (750円) | GLM/Qwen/DeepSeek | OpenAI互換 | 連携可能 | 中国系モデルを安価に利用可能 [17] |
| **Qwen** | チャット/API | 基本無料 | 無料 | Qwen 3.7 Max | あり | **公式** | 数学・コーディングに強い [18] |
| **Z.ai Lite** | チャット/API | $18 | 約2,700円 | GLM-5.1 | あり | **公式** | 強力なエージェント機能 [19] |
| **Codeium** | 拡張機能 | 無料〜$12 | 無料〜1,800円 | 独自+DeepSeek | BYOK対応 | **公式** | 無料枠が非常に強力 [20] |
| **Sourcegraph** | 拡張機能 | 無料〜$9 | 無料〜1,350円 | 多モデル対応 | BYOK対応 | **公式** | 大規模リポジトリの理解に特化 [21] |

## 2. 2026年6月の市場トレンドと重要トレンド

2026年6月現在、AIコーディング市場は以下の大きな変化の中にあります。

### ① Agentic（自律型）への完全シフト
単なるコード補完の時代は終わり、「計画→実行→修正→検証」を自律的に行うエージェント機能が標準となりました。
*   **Cursor Composer** や **Windsurf Cascade** は、複数のファイルをまたぐ複雑な修正を自律的に行います。
*   **Claude Code** や **OpenAI Codex** は、高度な推論能力を活かしたエージェント体験を提供します。

### ② GitHub Copilot の「AI Credits」制への移行
2026年6月1日より、GitHub Copilotは従来の「リクエスト数ベース」から、モデルの負荷に応じた「使用量ベース（AI Credits）」へ完全に移行しました。
*   **Proプラン ($10)**: 1,000 Credits
*   **Pro+プラン ($39)**: 3,900 Credits
これにより、ヘビーユーザーは以前よりも早く制限に達する可能性があり、上位プランへの移行や他サービスとの併用が検討されています [6]。

### ③ BYOK (Bring Your Own Key) + 中国系モデルの台頭
コストパフォーマンスを追求するユーザーの間で、**DeepSeek V4** や **Qwen 3.7** などの中国系モデルを、**Cline** や **Aider** などの無料ツールに自前のAPIキー（BYOK）で組み込む手法が一般化しています。これにより、月数ドルのコストで最高峰の性能を享受できます [16]。

### ④ 学生プランからの移行問題
現在、GitHub Copilotの新規Pro/Pro+および学生プランの申し込みが制限されています。既存の学生ユーザーがより高い制限を求めてアップグレードすることが難しくなっており、**Cursor** や **Windsurf**、あるいは **OpenCode** などの代替サービスへの流入が加速しています。

## 3. 注意点と選び方のガイド

*   **VS Codeを使い続けたい場合**: **GitHub Copilot**（安定性）と、**Cline / Roo Code**（エージェント機能）を併用し、必要に応じて **DeepSeek** などの安価なAPIを組み込むのが2026年の「最強構成」です。**Windsurf** も公式拡張機能を提供しており、既存のVS Code環境に「Cascade」エージェントを導入可能です。
*   **最高の開発体験（UX）を求める場合**: **Cursor** または **Windsurf** の有料プランが推奨されます。特に多ファイル編集や自律的なデバッグにおいては、独立IDEならではの統合体験が勝ります。
*   **コストを極限まで抑えたい場合**: **Aider** や **Cline** を使い、**DeepSeek** や **OpenRouter** のAPIで従量課金にするのが最も合理的です。
*   **大規模な既存コードを解析したい場合**: 200万トークン以上のコンテキストを持つ **Antigravity** や **SuperMaven**、あるいは **Sourcegraph Cody** が適しています。

## 参考文献

[1] Cursor · Pricing. (n.d.). [https://cursor.com/pricing](https://cursor.com/pricing)
[2] Windsurf Pricing 2026. (2026, March 23). [https://www.verdent.ai/guides/windsurf-pricing-2026](https://www.verdent.ai/guides/windsurf-pricing-2026)
[3] Zed — Pricing. (n.d.). [https://zed.dev/pricing](https://zed.dev/pricing)
[4] Google Antigravity: The New Best AI Editor?. (n.d.). [https://www.youtube.com/watch?v=j0UPItO6BX4](https://www.youtube.com/watch?v=j0UPItO6BX4)
[5] Trae: Adaptive AI Code Editor. (2025, March 26). [https://www.kdnuggets.com/trae-adaptive-ai-code-editor](https://www.kdnuggets.com/trae-adaptive-ai-code-editor)
[6] GitHub Copilot usage-based billing. (2026, April 27). [https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/)
[7] Claude Code vs Kilo Code (2026). [https://www.morphllm.com/comparisons/kilo-code-vs-claude-code](https://www.morphllm.com/comparisons/kilo-code-vs-claude-code)
[8] OpenAI Codex Pricing. (n.d.). [https://openai.com/codex/pricing](https://openai.com/codex/pricing)
[9] Aider - AI Pair Programming in Your Terminal. [https://aider.chat/](https://aider.chat/)
[10] Cline vs Roo Code. [https://kilo.ai/compare/roo-vs-cline-vs-kilo](https://kilo.ai/compare/roo-vs-cline-vs-kilo)
[11] Kilo Code VS Code Extension. [https://marketplace.visualstudio.com/items?itemName=kilocode.Kilo-Code](https://marketplace.visualstudio.com/items?itemName=kilocode.Kilo-Code)
[12] Continue.dev. [https://continue.dev/](https://continue.dev/)
[13] Supermaven Pricing. [https://supermaven.com/pricing](https://supermaven.com/pricing)
[14] Tabnine Pricing. [https://www.tabnine.com/pricing](https://www.tabnine.com/pricing)
[15] Amazon Q Developer. [https://aws.amazon.com/jp/q/developer/](https://aws.amazon.com/jp/q/developer/)
[16] DeepSeek Platform. [https://deepseek.com/](https://deepseek.com/)
[17] OpenCode. [https://opencode.ai/ja/go](https://opencode.ai/ja/go)
[18] Qwen AI. [https://qwen.ai/](https://qwen.ai/)
[19] GLM Coding Plan. [https://z.ai/subscribe](https://z.ai/subscribe)
[20] Codeium Pricing. [https://codeium.com/pricing](https://codeium.com/pricing)
[21] Sourcegraph Cody. [https://about.sourcegraph.com/cody](https://about.sourcegraph.com/cody)
