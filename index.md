# 【2026年最新】AIコーディングアシスタント・エージェント完全網羅レポート
## 〜次世代IDEから自律型CLI、オープンソースBYOKツールまで徹底比較〜

### 1. エグゼクティブ・サマリー（はじめに）
2026年現在、AIによるソフトウェア開発支援は、単なる「Tabキーによる1行補完」の時代を完全に脱却し、リポジトリ全体を自律的に書き換える**「Agentic（エージェント型）ワークフロー」**へと移行しました。

本レポートでは、開発者のシェアを二分するAI特化型コードエディタ（Cursor、Windsurf等）をはじめ、急成長を遂げるオープンソース・BYOK（APIキー持込）型エージェント（Cline、Kilo Code、Aider等）、エンタープライズに特化した高セキュリティプラットフォーム、そして低コストで圧倒的な推論力を誇る中国系新興モデルにいたるまで、現在市場で選択可能な主要18サービスを徹底的に調査・比較しました。

---

### 2. 主要AIコーディングツール比較マトリックス

| サービス名 | カテゴリ | 何向きか | 月額料金(USD) | JPY換算(1ドル=150円) | 主な使えるモデル | VS Code対応か？ | 主な特徴 | Proプラン使用量目安 | 補足 |
|------------|----------|----------|---------------|---------------------|------------------|----------------|----------|---------------------|------|
| **Cursor** | AIコードエディタ | ソフトウェア開発者・プログラマー（特にAI支援で高速開発したい人） | Pro: $20/mo | ¥3,000 | Claude 4.6 Sonnet, Claude Opus, GPT-5シリーズ, Gemini 3.x, Composer 2.5, Grok Buildなど | はい（VS Codeのフォーク） | VS Code互換フルIDE、Tab補完無制限、Agent/Composer（自然言語で大規模編集）、Cloud Agents、MCPs/Skills、プロジェクト全体理解、大規模リファクタリング | $20分のAPI使用量（Claude Sonnetで約200〜250回程度、Geminiで500回以上可能）。Tab補完は無制限 | Proが最も人気。重いAgent利用者はPro+ ($60)やUltra ($200)を推奨。使用量超過時は従量課金可能 |
| **Windsurf** | AIコードエディタ | ソフトウェア開発者・プログラマー（特にAgenticワークフローやコストパフォーマンスを重視する人） | Pro: $20/mo（以前$15程度の情報もあり、現在$20が主流） | ¥3,000 | SWE-1.6 / SWE-1.5（自社最適化モデル）, Claude Sonnet/Opus 4.x, GPT-5シリーズ, Gemini 3.x など | はい（VS Codeのフォーク） | Cascade（多段階推論Agent）、高速Tab補完、無制限inline edits、プロジェクト全体コンテキスト、ライブプレビュー、terminal-aware機能、クリーンなUI | Proで標準クォータ（daily/weekly refresh）＋500 credits相当程度（モデルによる）。SWEシリーズは効率的で長く使える。Tab補完無制限 | Windsurf（旧Codeium系、現在Devin Desktop関連）はCursorの強力な競合。無料ティアが実用的（25 credits + 無制限Tab）。Proはコストパフォーマンス高め。重度利用者はMax ($200)推奨 |
| **Zed Pro** | AIコードエディタ | 速度と軽量さを重視する開発者・パフォーマンス重視のプログラマー（Rustネイティブで超高速編集を求める人） | Pro: $10/mo | ¥1,500 | Claude Opus/Sonnet 4.xシリーズ, GPT-5.5 / 5.4, Gemini 3.x, Grok Code, Mistralなど（Zed-hosted + BYOキー + Ollamaローカル対応） | いいえ（独自エディタ、VS Codeキーバインド対応） | Rust製超高速エディタ、無制限Edit Predictions（Tab補完）、Agenticワークフロー、Parallel Agents、コラボレーション機能、Ollamaローカルモデル完全対応、GPU加速 | $5相当の月間トークンクレジット込み（超過分はAPI価格+10%従量課金）。デフォルト月間支出上限設定可能（例: 合計$20程度） | 無料プランでも基本利用可能（制限付き）。Editor自体は永久無料。Cursor/Windsurf（VS Codeフォーク）に対し「純粋な高速エディタ」として差別化。拡張性はVS Codeほど豊富ではないが、速度と軽さが最大の強み |
| **Antigravity** | AIコードエディタ | Agentic開発・マルチエージェントワークフローを重視する開発者（複雑プロジェクトやオーケストレーションを求める人） | Pro: $20/mo（Google AI Proプランにバンドル） | ¥3,000 | Gemini 3.x Pro/Flashシリーズ, Claude Sonnet/Opus 4.x, GPT-OSS-120Bなど | はい（VS Codeのフォーク） | Agent Manager（複数並行エージェント）、Mission Control、ブラウザ操作・terminal連携、Planning Mode、vibe coding対応、Geminiネイティブ統合 | Proで高額クレジット/レートリミット（Gemini Flash多めで日常使い十分、Opus/Claude高コストモデルは制限あり）。週次/時間リフレッシュ制 | Google公式Agent-first IDE。無料ティアが比較的太っ腹（プレビュー時）。Ultra ($250) で超高制限+特典。Cursor/Windsurfの強力競合でマルチエージェントが差別化点。セキュリティ懸念 of 過去あり |
| **Trae (TRAE)** | AIコードエディタ | コストパフォーマンス・美麗UI・Agentic開発を重視する開発者（ByteDance製、無料/低価格で高性能モデルを使いたい人） | Lite: $3/mo<br>Pro: $10〜$20/mo（プランによる） | ¥450<br>¥1,500〜¥3,000 | Claude 3.5/4.x Sonnet/Opus, GPT-5シリーズ, Gemini 3.x, DeepSeek, MiniMax, Kimi, 自社/カスタムモデル（BYO対応） | はい（VS Codeフォーク） | 美しいUI/UX、Builder Mode（自動プロジェクト生成）、SOLO Mode（タスク完全自動化）、CUE（超賢いTab補完）、カスタムAgentチーム構築、MCPツール統合、プレビュー/ブラウザ連携、多言語（中英強め） | Proで$20前後のBasic Usage + Bonus（モデルによる。Claude/GPT高コストモデルは消費早め、DeepSeek/Gemini系で長持ち）。無制限Autocomplete（プランによる）、SOLO concurrent tasks増加 | ByteDance製の強力無料/低価格競合。無料ティアでもClaude/GPT高性能モデルにアクセス可能（制限あり）。Lite $3から実用的。Pro+ ($30) / Ultra ($100) で高制限。プライバシー（ByteDance）に関する議論あり。公式: [trae.ai](https://www.trae.ai/) |
| **GitHub Copilot** | AIコード補完ツール | GitHubエコシステムを活用する開発者・チーム開発者（特にコード補完とChat/Agentを日常的に使う人） | Pro: $10/mo<br>Pro+: $39/mo | ¥1,500<br>¥5,850 | GPT-5シリーズ (Codex含む), Claude Sonnet/Opus 4.x, Gemini 3.x など（プランにより選択制限あり） | はい（VS Code拡張として最高の統合） | 無制限インライン補完（コード補完はクレジット消費なし）、Copilot Chat、Agentモード、コードレビュー、CLI統合、GitHubネイティブ連携 | Pro: 月額$10分のAI Credits（約1,500 credits相当）。補完は無制限だがChat/Agent/Reviewが消費対象。Pro+は約7,000 creditsで大幅増。超過分は従量課金 | **学生はGitHub Copilot Studentプラン（無料）** で無制限補完＋限定クレジットが利用可能だが、Pro/Pro+へのアップグレードは現在新規申込一時停止中（既存ユーザーはアップグレード可）。補完は基本無制限だが高機能Agent/Chatはクレジット制限が厳しく、重い利用で早く尽きやすい。2026年6月からusage-based billing（AI Credits制）に完全移行 |
| **Claude Code** | AIコードエージェント / ターミナルツール | Agentic開発・大規模コードベース作業を重視する開発者（ターミナル/CLI中心、プロジェクト全体自動化したい人） | Pro: $20/mo<br>Max 5x: $100/mo<br>Max 20x: $200/mo | ¥3,000<br>¥15,000<br>¥30,000 | Claude Opus 4.x / Sonnet 4.x シリーズ（Haikuも使用可） | はい（公式VS Code拡張あり + Cursorなど対応） | ターミナル/CLIネイティブAgent、ファイル読み書き・コマンド実行・Git操作自動化、プロジェクト全体理解（1M+トークンコンテキスト）、Plan & Edit、Sub-agents、多Agentオーケストレーション、IDE統合 | Pro: 5時間ごとリセットの使用量（Sonnet中心で中程度のAgentセッション数十回程度）。Claude Codeはトークン消費が大きく、Opus多用で早く制限到達。Maxプランで大幅増 | Anthropic公式Agenticツール。Proでアクセス可能だがヘビーユースはMax推奨（API消費ベース）。Cursor/WindsurfなどのIDEと併用が人気。無料ティアでも限定利用可。使用量超過時は追加クレジット購入可能Claude Codeはトークン消費が激しいため、Sonnet中心・.claudeignore活用で効率化必須 |
| **OpenAI Codex** | AIコードエージェント / ターミナルツール | Agentic開発・CLI中心の自動化を重視する開発者（タスク丸投げ・クラウド実行・PR生成を求める人） | ChatGPT Plus: $20/mo<br>Pro: $200/mo | ¥3,000<br>¥30,000 | GPT-5.5 / 5.4 Codexシリーズ（自社最適化モデル） | はい（公式VS Code拡張 + Cursor/Windsurf対応） | Rust製CLI（オープンソース）、クラウドサンドボックス実行、GitHub PR自動生成、ブラウザ/デスクトップアプリ、Steer Mode、プロジェクト全体Agent、タスク非同期実行 | Plus: 限定クレジット（週数回〜数十回のAgentセッション）。Pro: 6x以上容量（ヘビーユース向け）。トークン課金制で重いタスクは消費激しい（平均$100-200/月目安） | ChatGPTプランに含まれるAgentツール。Claude Codeの直接競合。CLI無料（APIキー必要）。2026年4月からトークンベース課金に移行。CursorなどIDEと併用が人気。無料/Goプランでも限定利用可 |
| **Aider** | AIコードペアプログラミング（ターミナルCLI） | ターミナル中心の開発者・コストを最小限に抑えたい人・オープンソース好き（Git連携を活かしたペアプログラミングを好む人） | 無料（オープンソース）<br>API使用料のみ | ¥0<br>（APIによる） | Claude 3.7/4.x Sonnet/Opus, GPT-5/oシリーズ, DeepSeek, Gemini, Ollamaローカルモデルなど（ほぼ全てのLLM対応、BYOキー） | いいえ（ターミナルCLI中心。VS Code/Neovim拡張や併用可能） | Gitネイティブ連携（自動commit）、リポジトリ全体マッピング、多ファイル編集、コードテスト自動化、100+言語対応、軽量・高速、.aiderignore対応 | API使用量のみ（Sonnet/GPT-4o中心で中程度利用：$10〜30/mo、重度利用：$50〜100+/mo）。ローカルOllama使用で実質¥0 | 完全無料オープンソース（Apache 2.0）。サブスクリプションなし。Claude CodeやCodexの軽量代替として人気。モデル柔軟性が高く、コストコントロールしやすい。ターミナルワークフローを好む上級者向け。CursorなどIDEと併用が一般的 |
| **Cline** | AIコードエージェント（オープンソースVS Code拡張） | コントロール重視・透明性が高いAgentワークフローを求める開発者（ステップバイステップ承認、人間-in-the-loop、コスト管理したい人） | 無料（ツール本体）<br>API使用料のみ（BYOK）<br>Teams: $20/user/mo（初回10席無料） | ¥0<br>（APIによる）<br>¥3,000/user | Claude 4.x Sonnet/Opus, GPT-5シリーズ, Gemini 3.x, DeepSeek, Ollamaローカルなど（30+プロバイダ対応） | はい（公式VS Code拡張、JetBrains/Cursor/Windsurf/Zed対応も拡大中） | Plan/Actモード、MCPツール統合、ブラウザ操作・terminal実行、ファイル編集、Checkpoints、Spend Limit設定、完全オープンソース（Apache 2.0） | API料金のみ（Sonnet中心の中規模タスク：$5〜20/mo程度、重度利用で$50+/mo）。Gemini/DeepSeekで大幅コストダウン可能 | 元Claude Dev。5M+インストールの人気オープンソースAgent。無料で高機能、BYOKで柔軟。Roo Codeの元祖。使用量はコンテキストサイズとモデルで大きく変動。公式: [cline.bot](https://cline.bot/) |
| **Roo Code** | AIコードエージェント（VS Code拡張） | 多モード・チーム開発・構造化されたAgentワークフローを求める人（元Clineフォーク） | 無料（ツール本体、2026年5月15日時点で拡張はアーカイブ/シャットダウン済み）<br>旧Teams: $99/mo flat | ¥0<br>（APIによる）<br>旧¥14,850 | Claude/GPT/Geminiなど（BYOK） | はい（VS Code中心） | Multi-Modes（Code/Architect/Ask/Debug/Custom）、多Agentペルソナ、クラウド機能（旧）、カスタムワークフロー | API料金のみ（類似Cline）。重度利用で変動大 | Clineのフォークとして登場したが、2026年5月15日に拡張/クラウドサービスをシャットダウン（RoomoteクラウドAgentへピボット）。現在はコミュニティフォーク（Zoo Codeなど）が代替として存在。歴史的比較対象として記載 |
| **Kilo Code** | AIコードエージェント（オープンソースVS Code拡張） | 柔軟性・コストコントロール・多モデル対応を重視する開発者（BYOK/オープンソース好き、Cline/Roo Codeからの移行者） | 本体: 無料<br>Kilo Pass Starter: $19/mo<br>Pro: $49/mo<br>Expert: $199/mo | ¥0<br>¥2,850<br>¥7,350<br>¥29,850 | 500+モデル（Claude 4.x Opus/Sonnet, GPT-5.5, Gemini 3.x, DeepSeek, Grok, Ollamaローカルなど）BYOK完全対応 | はい（公式VS Code拡張、JetBrains/CLI/Cloud対応） | Multi-Mode（Architect/Coder/Debuggerなど）、inline autocomplete、MCPツール統合、ブラウザ/terminal自動化、並行Agent、完全オープンソース（Apache 2.0）、ゼロマークアップ | API使用料のみ（BYOKの場合）。Kilo Pass Proでボーナスクレジット付き（中程度利用：$20〜60/mo程度）。Gemini/DeepSeek系で低コスト、長持ち | Cline/Roo Codeの進化版/統合フォーク。無料で高機能、500+モデル対応が最大の強み。Kilo Passは任意（クレジット購入で割引）。ヘビーユースはBYOK or 上位プラン。公式: [kilo.ai](https://kilo.ai/) |
| **SuperMaven** | AIコード補完ツール | 超高速・低遅延のコード補完を重視する開発者（大規模コードベースで高速補完を求める人） | Pro: $10/mo<br>Team: $10/user/mo | ¥1,500<br>¥1,500/user | 自社最適化モデル（高速推論）、ChatでGPT-4o / Claude 3.5/4.x Sonnetなど（BYOキー対応） | はい（公式VS Code拡張 + JetBrains / Neovim対応） | 業界最速クラス補完（~250ms）、1Mトークン超大規模コンテキスト、スタイル適応、Chat機能（$5クレジット込み）、大規模コードベース対応 | Pro: 無制限補完 + $5 Chatクレジット（超過は従量）。高速モデル中心で日常使い十分 | 高速補完に特化したCopilot代替。無料ティアでも実用的（コンテキスト制限あり）。Cursorに買収・統合の噂ありだが2026年6月時点で独立サービス継続中。補完速度と大規模コンテキストが最大の強み |
| **Tabnine** | AIコード補完ツール / エンタープライズAIコーディングプラットフォーム | プライバシー・セキュリティ・エンタープライズ準拠を重視する開発者・企業（オンプレミス/プライベートデプロイ希望、大規模チーム） | Code Assistant: $39/user/mo（年契約）<br>Agentic Platform: $59/user/mo | ¥5,850/user<br>¥8,850/user | 自社プライベートモデル + Claude 4.x / GPT-5 / Gemini 3.x など複数選択可能（BYO対応） | はい（公式VS Code拡張 + JetBrains / Eclipse / Visual Studio対応） | プライバシー重視（オンプレ/Air-gapped対応）、コードベース学習、Chat + 補完、Agent機能、企業ガバナンス、Jira連携、無制限補完 | 基本無制限（プランによる）。Chat/Agent使用は高額プランで優遇。使用量制限は緩め | 個人向け無料/低価格プランは縮小・終了傾向で、主に企業向け（$39〜）。プライバシーとコンプライアンスが最大の強み。個人開発者はCursor/Windsurf/Kilo Codeなどの方がコスパ良い場合が多い。公式: [tabnine.com/pricing](https://www.tabnine.com/pricing/) |
| **Amazon Q Developer** | AIコードアシスタント / IDE拡張 | AWSエコシステムを活用する開発者・企業（セキュリティ・コンプライアンス重視、大規模コードベース、クラウドネイティブ開発） | Pro: $19/user/mo | ¥2,850/user | Claude 4.x Sonnet/Opus（主統合）, 自社最適化モデル, Amazon Titanなど（AWSモデル中心） | はい（公式VS Code拡張 + JetBrains / Visual Studio対応） | インライン補完、Agentic coding（自然言語でタスク実行）、コード変換（Java/.NET）、セキュリティスキャン、AWSサービス最適化、Chat、MCPツール統合 | Pro: 1,000 agentic requests/月 + 4,000 LOC transformation/月（超過$0.003/LOC）。補完は実質無制限寄り | AWS公式ツール。企業向けセキュリティ・SSO・IP indemnityが強み。新規サブスクリプションは2026年5月15日以降制限（既存継続可）。2027年4月末にIDEサポート終了予定（Kiro移行推奨）。個人開発者は無料ティアでも試せるが制限あり |
| **DeepSeek** | AIモデル / コーディングプラットフォーム | コストパフォーマンスを最重視する開発者（API + オープンソースツールで低価格高性能モデルを使いたい人） | API従量課金（サブスクなし）<br>Chat: 無料ティアあり | ¥0（基本）<br>中程度利用: $2〜10/mo | DeepSeek V4 Pro / Flash（自社主力）、V3シリーズ、Coderモデルなど | はい（VS Code拡張、Deep Code CLI、Kilo Code / Cline / Continue.dev など多ツール対応） | 超低価格API（V4 Flash: ~$0.14/$0.28 per 1M tokens）、1Mコンテキスト、Reasoning/Thinkingモード、Deep Code（オープンソースCLI Agent）、高性能コーディング特化 | API使用量のみ（V4 Flash/Proで中規模Agent作業: $2〜15/mo程度。重度利用でも$30〜80/mo以内で収まるケース多数） | 主にモデル提供者。フルIDEではなくAPI + 各種ツール（Deep Code CLI、VS Code拡張）と組み合わせる形。Claude/GPTの10分の1程度のコストで同等性能が出やすいと2026年現在非常に人気。BYOKでCline/Kilo/Continue/Aiderなどに最適。公式: [platform.deepseek.com](https://platform.deepseek.com/) |
| **OpenCode Go** | AIコードエージェント（サブスクリプション） | 低コストで高性能オープンソース/中国系モデルを使いたい開発者（OpenCodeユーザー、コストパフォーマンス重視） | Goプラン: $5（初月）→ $10/mo | ¥750（初月）→ ¥1,500 | GLM-5.1 / Kimi K2.6 / Qwen 3.x / MiniMax M2.7 / DeepSeek V4 など（中国系高性能モデル中心、定期更新） | はい（OpenCode公式VS Code拡張対応 + 他のエージェントも利用可） | OpenCode本体（オープンソースCLI/TUI/Desktop）と組み合わせ、低価格で信頼できるagenticモデル提供、75+プロバイダ対応、BYOKも可 | $10で5時間ごと $12相当使用 + 週$30 / 月$60相当（モデルによる。GLM/Kimiなどで中規模タスク数百回可能）。超過は制限あり | OpenCode（無料オープンソースAgent）の公式低価格モデルバンドル。OpenCode本体は永久無料（BYOK推奨）。Goは「安価で安定した高性能モデル」を求める人に最適。Cursor/Claude Codeの低価格代替として人気急上昇中。公式: [opencode.ai/go](https://opencode.ai/go) |
| **Qwen (Qwen Code)** | AIコードエージェント（オープンソースCLI） | 低コスト・高性能中国系モデルを活用したい開発者（ターミナル中心、コストパフォーマンス重視、OpenCode/DeepSeekユーザー） | 本体: 無料（オープンソース）<br>Alibaba Cloud Coding Plan: Lite ~$10/mo / Pro ~$50/mo | ¥0<br>¥1,500 / ¥7,500 | Qwen3.7-Max / Qwen3-Coder-Plus / Qwen3.7-Plus など（自社高性能モデル中心） | はい（VS Code拡張対応 + Zed / JetBrains） | ターミナルファーストAgent、SubAgents・Skills内蔵、大規模コードベース理解、Plan & Act、多ステップ自動化、Qwenモデル最適化 | Coding Plan Lite/Proで数万〜9万リクエスト/月相当（Qwen3-Coderモデル中心で中〜大規模タスク数百回可能）。API従量も超安価（V4系で$数/月で十分） | Alibaba公式オープンソースAgent（Claude Code/Aider類似）。本体永久無料、費用はAlibaba CloudのCoding Plan or API従量。DeepSeek並みの低価格高性能が強み。ローカル/他プロバイダ（OpenRouterなど）も柔軟対応。公式: [qwen.ai/qwencode](https://qwen.ai/qwencode) |
| **Z.ai (GLM Coding Plan)** | AIモデルプロバイダ / Coding Plan | 低コスト・高性能中国系モデル（GLMシリーズ）をAgentツールで使いたい開発者（コストパフォーマンス重視、Cline/Kilo/OpenCode/Claude Codeユーザー） | Lite: ~$6-10/mo<br>Pro: ~$30/mo<br>Max: ~$80/mo | ¥900-1,500<br>¥4,500<br>¥12,000 | GLM-5.1 / GLM-5 / GLM-5-Turbo, GLM-4.7 / 4.6シリーズ（コーディング特化） | はい（Cline, Kilo Code, Continue.dev, OpenCode, Claude Codeなど20+ツール対応） | GLMモデル最適化Coding Plan、Agenticワークフロー対応、MCPツール統合、安価で高レートリミット（promptベース）、多ツール互換性 | Pro: 600 prompts/5時間程度（Liteは120 prompts）。中規模Agentタスク数百回可能、超過はプランによるリフレッシュ | Zhipu AI/GLM公式のCoding専用サブスクリプション。本体ツールではなく「モデル+クォータ提供」。DeepSeek/Qwen並みの低価格が強みで、Cline/Kilo/AiderなどオープンソースAgentと組み合わせるのが主流。API従量も超安価。公式: [z.ai/subscribe](https://z.ai/subscribe) |
| **Codeium (Windsurf)** | AIコーディングアシスタント / IDE・拡張機能 | コストを抑えて高品質なインライン補完を使いたい個人開発者、またはオンプレミスや強固なセキュリティ（データ不保持）を求める企業・チーム | **Individual:** $0 (無料)<br>**Pro:** $15/mo<br>**Teams:** $30/user/mo<br>**Enterprise:** $60+/user/mo | ¥0<br>¥2,250<br>¥4,500<br>¥9,000〜 | Codeium独自カスタムモデル（低遅延・高精度）、SWE-1.5、その他主要LLM（Chat/Agent用、Claude 3.5 SonnetやGPT-4o等、プランにより可変） | **はい**（VS Code拡張機能として完全対応。JetBrains, Neovim等主要IDE/エディタ20種以上にも対応） | 個人向けは**期間制限なしの永続無料プラン**（Unlimited補完）が最大の強み。企業向けにはソースコードを一切学習・保持しない「Zero-Data Retention」や、オンプレミス／Air-gapped（完全オフライン環境）へのデプロイを網羅する圧倒的なセキュリティ性。 | **Pro:** 月あたり500クレジット。高度なマルチファイルAgent（Cascade機能）やChat、リファクタリングを中〜大規模プロジェクトで日常的に回せる容量。なお、**インラインコード補完（Tab）自体は全プラン無制限**。 | 元々はGitHub Copilotの強力な無料代替エディタ拡張として急成長。現在はAIネイティブIDE「Windsurf Editor」（VS Codeのフォーク）の展開に伴い、ブランドや拡張機能名も「Windsurf Plugin」へ統合が進んでいる。個人開発者がコストゼロで実用的な環境を作る際の定番。公式: [codeium.com](https://codeium.com) |
| **Sourcegraph (Cody)** | AIコーディングアシスタント / 大規模コード検索・管理（エンタープライズ） | 膨大なマイクロサービスや多数のリポジトリ（マルチリポジトリ）を抱え、システム全体の構造をAIに正確に把握させたい大規模組織・エンタープライズ企業向け | **Enterprise:** $59/user/mo<br>（※年間契約ベース。個別交渉やボリューム割引あり。個人向けのFree/Proは提供終了） | ¥8,850/月<br>（ユーザーあたり） | Anthropic Claudeシリーズ（Claude 3.5 Sonnet / Opus等）、OpenAI GPT-4o、その他オンプレミス・独自ホストモデル（柔軟に切り替え可能） | **はい**（VS Code拡張機能、JetBrains、Visual Studio、Webブラウザ、CLIに完全対応） | 最大の強みは**「マルチリポジトリ・コンテキスト（複数リポジトリの横断解析）」**。CursorやCopilotが「開いているワークスペース」しか見られないのに対し、背後のSourcegraph検索エンジンと連携し、最大10以上の別リポジトリの依存関係やAPI構造を横断して100万トークンの広大な窓で解析。 | **非該当**（個人向けProプランは2025年7月に終了）。現在のEnterpriseプランは、組織全体でプール・共有される「AIクレジットシステム」を採用しており、月ごとのリフレッシュや繰り越しが契約に基づいて管理される。 | 2025年後半、個人向けのCody Free/Proプランを廃止し、大規模コードベース向けのEnterprise（$59/人/月〜）へ完全一本化。個人ユーザーの移行先としては、無料の「Amp」という新プロダクトを公式が提供。企業向けとしては、特定の機密コードを外部LLMへ送らない「Context Filters」など、業界最高峰のセキュリティを誇る。公式: [sourcegraph.com](https://sourcegraph.com) |
| **Perplexity** | AI対話型検索エンジン（Answer Engine） / リサーチアシスタント | 最新情報のネットリサーチ、技術ドキュメントの比較調査、市場分析、学術リサーチなど、正確なソース（引用元）を伴う情報収集を高速化したいすべての開発者・ビジネスパーソン | **Free:** $0 (無料)<br>**Pro:** $20/mo<br>**Enterprise Pro:** $40/user/mo | ¥0<br>¥3,000<br>¥6,000 | Default (独自モデル), GPT-4o, Claude 3.5 Sonnet, Sonar (Perplexityカスタム推論モデル), その他最新の主要フラグシップLLM | **いいえ**（公式のコーディング拡張機能はなし。ただし、ブラウザやサードパーティ製のAPI連携、MCPツール等経由でVS Code環境と限定的な情報共有は可能） | 検索結果のすべての情報に**明確な引用元（ソース）リンク**を表示する元祖AI検索。ProプランではWeb上を自律的に探索して網羅的なレポートを自動生成する「Deep Research / Pages」機能が強力。PDFやソースコードなどのマルチモーダルなファイルアップロード解析にも対応。 | **Pro:** 1日あたり**約600回のPro検索（旧Copilot検索）**が可能。2026年現在、最上位モデル（Claude 3.5やGPT-4o）を使用した高度なステップバイステップ検索やマルチモーダル解析を日常的に回すのに十分な容量。 | 単なる「チャットAI」ではなく「信頼できる検索エンジン」として確固たる地位を確立。2025年後半に法人向けの「Enterprise Pro」を本格展開し、社内ドキュメント（Notion、Google Drive等）とWebの情報を一括横断検索できる機能が追加された。コーディングの直接補完（Tabキー補完）ではなく、技術仕様の調査やエラー原因の深掘りといった「リサーチフェーズ」で最強の威力を発揮する。公式: [perplexity.ai](https://perplexity.ai) |
| **Kimi (Kimi Code / Moonshot AI)** | AIコーディングエージェント / 大規模コンテキスト処理（長文特化） | 超広大なコンテキスト（200万〜数千万トークン窓）を活かし、ターミナルやIDE上でリポジトリ全体を自律的に探索・一括リファクタリングさせたい「Agentic（エージェント型）ワークフロー」重視の開発者 | **Moderato (Entry):** $15/mo<br>**Pro:** $20/mo<br>**Max 5x:** $100/mo<br>**Max 20x:** $200/mo | ¥2,250<br>¥3,000<br>¥15,000<br>¥30,000 | Kimi K2.6（最新1兆パラメータMoEモデル）、Kimi K2、Kimi-Chatシリーズ | **はい**（「Kimi Code VS Code Extension」が公式提供されているほか、ACP（Agent Client Protocol）経由で各種エディタに対応） | 2026年最新の「Kimi K2.6」を搭載。ターミナルとIDEを往復する自律型CLI（Kimi Code CLI）を軸に、**マルチファイル編集、シェルコマンド自動実行、ビルド・テストの自律的な反復修正（最大4,000ステップの連続実行）**が最大の強み。Claude Opus級の推論力を数分の一の低コスト（API層）で叩き出せる圧倒的な破壊力。 | **Pro:** 5時間のローリング窓内で約40〜45メッセージ（トークン換算約44K tokens/5hr）。中規模リファクタリング等の重いエージェントワークフローを回すと1〜2時間で上限に達するケースがあるため、ガチ利用には週次・月次の制限が大幅に緩和される「Max 5x/20x」が推奨される。 | 中国のAIユニコーン「Moonshot AI」が展開する国際ブランド。2026年現在、GitHub Copilotのような単なる「インライン補完（Tab）」の枠を超え、Claude Code ya Aiderのような「ターミナル自律動作型エージェント」の低コストな代替・最右翼として定着。API単体（OpenAI互換）の従量課金も100万入力トークンあたり0.60ドル前後と極めて安価。公式: [kimik2ai.com/kimi-code](https://kimik2ai.com/kimi-code/) |
| **Qwen3-Coder-Next** | ローカルLLM (オープンウェイト) | 高度な自律型エージェント開発、リポジトリ一括修正 | $0.00 (本体無料) | 0円 (電気代のみ) | Qwen3-Coder-Next (MoE) | **対応** (Ollama/Cline経由) | 80B総パラメータながら3Bアクティブの超効率MoE設計。最新のエージェント向け訓練（80万件の実行タスク学習）により、Clineでの自律デバッグ能力が極めて高い。 | **RTX 4090 (24GB) 以上** または Macの統一メモリ32GB以上 | 256kの巨大なコンテキスト窓を持ち、複数ファイルにまたがるコードベースの読み込みも破綻しにくい。 |
| **Gemma 4 12B** | ローカルLLM (オープンウェイト) | ラップトップでの軽快なコード生成、マルチモーダル開発 | $0.00 (本体無料) | 0円 (電気代のみ) | Gemma 4 12B | **対応** (Ollama/Continue経由) | エンコーダーレスの新世代マルチモーダルモデル。12Bという手軽なサイズでありながら、画像や音声の直接インプットに対応し、上位モデルに近い推論速度とコード生成力を発揮。 | **RTX 4070 Ti Super / 4080 (16GB)** または Macの統一メモリ16GB以上 | 16GBクラスのVRAMで量子化版（Q4_K_Mなど）がフルスピードで動くため、一般PCでのローカル開発の筆頭候補。 |
| **DeepSeek-Coder-V2-Lite** | ローカルLLM (オープンウェイト) | 日常的なインライン補完（Autocomplete）、高速なチャット | $0.00 (本体無料) | 0円 (電気代のみ) | DeepSeek-Coder-V2-Lite (16B) | **対応** (Ollama/Continue経由) | 16BのMoE（アクティブ2.4B）で、インラインのコード保管（Tab補完）において圧倒的な爆速レスポンスを誇る。FIM（Fill-in-the-Middle）タスクに最適化。 | **RTX 4060 Ti 16GB / 4070 (12GB)** あれば快適、メインメモリ併用なら8GB〜も可 | Continue拡張機能の「Autocomplete」側に指定するモデルとして、現在もローカル環境では鉄板の軽さ。 |
| **Llama 3.1 / 3.3 8B** | ローカルLLM (オープンウェイト) | 低スペック環境での基本的なコード相談、スクリプト作成 | $0.00 (本体無料) | 0円 (電気代のみ) | Llama-3.1-8B-Instruct など | **対応** (Ollama/Cline経由) | 汎用モデルながらコード耐性も高く、何より動作が軽量。指示への追従性が高く、ローカルでの初めてのコーディングアシスタント環境構築に最適。 | **RTX 3060 / 4060 (8GB)** のエントリーグラボで余裕で動作 | VRAM 8GBのゲーミングノートPC等でもサクサク動くため、最も敷居が低い。 |
| **CodeLlama 34B** | ローカルLLM (オープンウェイト) | じっくり考えさせる複雑なアルゴリズムの実装・リファクタ | $0.00 (本体無料) | 0円 (電気代のみ) | CodeLlama-34b-Instruct | **対応** (Ollama経由) | 34Bの単一パラメータ（Dense）モデル。ステップ数の多い複雑なロジックの組み立てや、厳密なコード構文が求められる場面で粘り強い回答を出せる。 | **RTX 3090 / 4090 (24GB)** または GPU2枚挿し | モデルサイズが大きいため、VRAM 24GBがないと生成速度（Tokens per second）が一気に落ちて実用性が下がる。 |


---

## 1. 2026年6月現在の市場トレンド分析

AIコーディング市場は、クラウドベースの定額サブスクリプションと、完全に独立したローカルLLM（オンデバイス実行）の二極化、およびそれらを柔軟に組み合わせるハイブリッド型の運用へと進化しています。

### 自律型（Agentic）ワークフローの成熟

単なる1行補完（Tab補完）の領域は完全にコモディティ化し、現在は「リポジトリ全体の解析」「エラーログからの自律的なデバッグ」「テストコードの自動生成と合格までのループ実行」を行うエージェント機能が標準となりました。CursorのComposer 2.5や、オープンソースのClineが提供するPlan & Act環境がその代表例です。

### ローカルLLMの飛躍的進化とハードウェア要件の変化

2026年現在、ローカル環境（PC上）で動作するオープンモデルの性能は、かつてのクラウド専用フラグシップモデルに匹敵するレベルに達しています。
特筆すべきは、2026年2月リリースの「Qwen3-Coder-Next」が持つリポジトリ規模の理解力（広大なコンテキスト窓）と、同年6月に発表された「Gemma 4 12B」の圧倒的なメモリ効率です。Gemma 4 12Bは、従来であれば膨大なリソースを必要とした高度な推論とマルチモーダル処理を、わずか16GBのVRAM（またはApple Siliconのユニファイドメモリ）という「一般的なノートPC環境」で実現可能にしました。

これにより、開発者は機密性の高い商用コードを外部のクラウドAPIに送信することなく、完全オフラインかつゼロコスト（電気代のみ）で安全にエージェント開発環境を構築・運用できるようになっています。

---

## 3. 総評価および技術選定指針

2026年のソフトウェア開発におけるAIツールの選定は、開発規模、機密保持の必要性、そして手元にある計算資源（GPU資産）によって明確に最適解が分かれます。

### クラウド完結型（スピード・手軽さ重視）

機密保持の制約が比較的緩く、最も洗練されたUXと最大の推論速度を求める場合は、Cursor（Proプラン）の1択となります。複数ファイルの同時書き換えにおける文脈理解の正確性は依然としてトップクラスであり、インフラの管理コストが一切かからないメリットは非常に大きいです。

### オープンソース・BYOK型（コストパフォーマンス・透明性重視）

サブスクリプションの固定費を最適化したい場合、**Cline**や**Aider**を基盤とし、ここに**DeepSeek API**などの格安な外部コーディング特化APIを接続する手法が最も合理的です。これにより、月額数百円から千円程度の極めて低い従量課金のみで、大手有料IDEと同等以上のマルチファイル自動編集能力を手に入れることができます。

### 完全ローカル型（セキュリティ・完全オフライン重視）

企業の機密ソースコードを扱う環境や、インターネット接続が制限された環境では、オープンソースの拡張機能（Cline等）に**Ollama**や**LM Studio**を経由してローカルLLMを接続する構成が最強の選択肢となります。

* **16GB VRAM環境（RTX 4080 / Apple Silicon 16GB以上）**:
新星である**Gemma 4 12B**、または**Qwen2.5-Coder-7B/32Bの量子化版**が最適です。特にGemma 4 12Bは、ノートPCクラスのスペックでも動作するように設計されており、ローカル実行時のもたつきを感じさせない低遅延なレスポンスを提供します。
* **24GB〜48GB VRAM環境（RTX 4090単体、または複数差し）**:
**Qwen3-Coder-Next**のミドル〜フルサイズモデルの運用が可能になります。256Kを超える巨大なコンテキストをオンメモリで処理できるため、ローカルでありながら「プロジェクト全体のコードベースを丸ごとAIに読み込ませてリファクタリングさせる」という、前世代では不可能だった高度な自律開発ワークフローが現実のものとなります。

---

### 具体的な参照元・引用元

[GitHub Blog: GitHub Copilot is moving to usage-based billing (April 27, 2026)](https://github.blog/news-insights/company-news/github-copilot-is-moving-to-usage-based-billing/)
[GitHub Features: Copilot Plans & Pricing (2026)](https://github.com/features/copilot/plans)
[Morph LLM / AI Perks: OpenAI Codex Pricing & Competitor Comparison (2026)](https://www.morphllm.com/codex-pricing)
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