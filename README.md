# Hi there, I'm 倉成倖聖

## 自己紹介・取り組みの概要
大阪大学基礎工学部（29年卒予定）の倉成倖聖です。
AIエージェント（Google Antigravity）を活用したWebゲームの企画・継続的な設計・開発に取り組んでいます。

単にAIにコードを生成させるだけでなく、「仕様の言語化」「保守性を意識した段階的なリファクタリング」「開発記録（DEVLOG.md）によるプロセス管理」を徹底し、フレームワーク非依存（ゼロ依存・Pure Vanilla JS）での高速起動や、Web Audio APIによるシンセ波形合成、本番環境（Cloudflare）を壊さないブランチ運用を実践しています。

---

## 制作したゲーム一覧（ポートフォリオ）
すべてのゲームは外部アセット不要でブラウザ上で即座にプレイ可能です。設計の工夫やリファクタリングの過程は各リポジトリの `README.md` および `DEVLOG.md` に記載しています。

| ゲーム名 | 概要・アピールポイント | プレイリンク (Cloudflare) | ソースコード & 開発記録 | 使用技術 |
| :--- | :--- | :--- | :--- | :--- |
| **SUCCESS** | 高校3年間（全144週）の育成シミュレーション。1ターン1個の使用制限によるゲーム内経済バランス調整や、Web Audio APIの自動再生制限・タイマードリフト対策を実装 | [▶️ Play Now](https://success.xcangcheng.workers.dev/) | [📁 Repository](https://github.com/koeita/SUCCESS)<br>[📝 DEVLOG](https://github.com/koeita/SUCCESS/blob/main/DEVLOG.md) | Vanilla JavaScript, HTML5/CSS3, Web Audio API, Cloudflare |
| **LIFE — ひとつの人生** | 0歳から臨終まで1年1ターンで歩む人生シミュレーション。リセマラ防止と強制復帰を行うターン永続化ステートマシン、Canvas APIによる生涯ステータス推移グラフ描画を導入 | [▶️ Play Now](https://life.xcangcheng.workers.dev/) | [📁 Repository](https://github.com/koeita/LIFE)<br>[📝 DEVLOG](https://github.com/koeita/LIFE/blob/main/DEVLOG.md) | Vanilla JavaScript, HTML5 Canvas API, Web Audio API, Cloudflare |
| **密室の謎解き脱出** | インラインSVGとWeb Audio APIのみで構築した本格脱出ゲーム。順列組み合わせ（840通り）による総当たり防止、暗闇モード（蓄光ギミック）、単一状態管理（SSOT）を設計 | [▶️ Play Now](https://escape.xcangcheng.workers.dev/) | [📁 Repository](https://github.com/koeita/escape)<br>[📝 DEVLOG](https://github.com/koeita/escape/blob/main/DEVLOG.md) | Vanilla JavaScript, Inline SVG, Web Audio API, Cloudflare |

---

## 開発フローと技術的なこだわり
* **ゼロ依存（Zero Dependencies）とパフォーマンス**：外部ライブラリや重いフレームワークに頼らず、ピュアな Vanilla JavaScript (ES6+)、Web Audio API、SVG/Canvas で構築。初期ロード時間を極限まで削減し、モバイル・PC問わず0秒起動を実現しています。
* **AIとの協業とリファクタリング**：AIが出力した初期コードの課題（巨大単一関数の肥大化やUIの干渉）を分析し、状態管理（Single Source of Truth）やモジュール分割など保守性の高い構造へとリファクタリングを継続的に実施しています。
* **安全なデプロイ運用**：`main` ブランチを保護するため、機能追加や改修は作業ブランチで行い、Cloudflare のプレビュー環境で動作検証・Playwright による回帰テストを実施してからマージする運用を徹底しています。
* **ドキュメント駆動の開発**：各プロジェクトのルートに仕様書（`README.md`）と逆時系列の開発日記（`DEVLOG.md`）を配置し、直面した課題の分析、解決アプローチ、コミット履歴を克明に追跡できるようにしています。

## 🔧 使用技術・ツール
* **Languages & Core Web:** JavaScript (ES6+), HTML5, CSS3, Web Audio API, HTML5 Canvas API, Inline SVG
* **Infrastructure & Hosting:** Cloudflare Workers / Pages, Git, GitHub
* **Testing & Tools:** Python, Playwright（E2E自動テスト）, Google Antigravity
