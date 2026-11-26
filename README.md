# Full-Focus-Timer-web

Android アプリ「**Full Focus Timer**」（開発者：`fooDev`）の利用規約・プライバシーポリシーおよび多言語 FAQ を公開する GitHub Pages リポジトリです。

## 公開 URL / Published URLs

- **Terms & Privacy Policy — English (Default / Root):** https://foodev-7777.github.io/Full-Focus-Timer-web/
- **利用規約・プライバシーポリシー — 日本語 (Japanese):** https://foodev-7777.github.io/Full-Focus-Timer-web/ja/
- **FAQ — English:** https://foodev-7777.github.io/Full-Focus-Timer-web/faq/
- **よくある質問 (FAQ) — 日本語 (Japanese):** https://foodev-7777.github.io/Full-Focus-Timer-web/ja/faq/
- **Remote Config JSON (App Operations):** https://foodev-7777.github.io/Full-Focus-Timer-web/config.json

## ファイル構成 / Repository Structure

| ファイル | 言語 | 説明 |
| :--- | :--- | :--- |
| `index.md` | English | 利用規約・プライバシーポリシー（英語版・ルートデフォルト） |
| `ja/index.md` | 日本語 | 利用規約・プライバシーポリシー（日本語版） |
| `faq/index.md` | English | よくある質問・FAQ（英語版） |
| `ja/faq/index.md` | 日本語 | よくある質問・FAQ（日本語版） |
| `config.json` | JSON (6言語対応) | アプリ Remote Config 用静的設定ファイル（規約バージョン・緊急お知らせ配信） |
| `README.md` | 日本語 / EN | 公開 URL・構成・運用仕様・改訂履歴 |

## Remote Config (`config.json`) 運用仕様

アプリ起動時にバックグラウンド（非同期・タイムアウト付き）で `config.json` を取得します。取得失敗・オフライン時はローカルキャッシュおよびアプリ内蔵デフォルト値にフォールバックするため、アプリ起動をブロックしません。

| キー | 型 | 説明 |
| :--- | :--- | :--- |
| `terms_version` | `Int` | 最新の利用規約バージョン。アプリ内蔵 `AppConfig.TERMS_VERSION` との最大値を実効バージョンとして採用し、ユーザー同意済みバージョンが未満の場合に再同意ダイアログを表示します。 |
| `announcement.id` | `String` | お知らせの一意 ID（例: `2026-12-maintenance`）。ユーザーが閉じると端末内に既読 ID が保存され、同じ ID では再表示されません。 |
| `announcement.enabled` | `Boolean` | `true` のときのみアプリ内にお知らせを表示します（タイマー実行中は集中を妨げないため非表示）。 |
| `announcement.severity` | `String` | 重要度（`info` / `warning`）。 |
| `announcement.title` | `Object` | 言語コード（`en`, `ja`, `de`, `fr`, `es`, `it`）ごとのタイトル。該当言語が空・未設定の場合は `en` にフォールバックします。 |
| `announcement.message` | `Object` | 言語コード（`en`, `ja`, `de`, `fr`, `es`, `it`）ごとの本文。該当言語が空・未設定の場合は `en` にフォールバックします。 |
| `announcement.action_url` | `String` | 任意の外部リンク URL（`https://` のみ許可。空文字の場合はボタン非表示）。 |

## 改訂履歴 / Revision History

| Version | 改定日 / Date | 変更内容 / Summary |
| :--- | :--- | :--- |
| **Version 1.0** | 2026-03-27（2026年3月27日） | 初版制定（日本語版 利用規約・プライバシーポリシー公開） |
| **Version 2.0** | 2026-11-24（2026年11月24日） | 多言語化、GDPR / UK GDPR 対応、および M2 機能・FAQ 整備：<br>- ルート（`index.md`）を英語版、`/ja/`（`ja/index.md`）を日本語版として整備し、相互言語切替リンク・目次アンカー・FAQ リンクを追加<br>- 多言語 FAQ ページ（`faq/index.md` / `ja/faq/index.md`）を新規作成（強制シールド、通知・省電力設定、プレミアム買い切り、購入復元、返金、応援チップ、広告・プライバシー設定とクラッシュレポート同意連動、データバックアップ、お問い合わせ）<br>- 利用規約第3条に買い切り（One-time / Lifetime）プレミアムライセンスおよび任意の消費型応援チップ（機能解放なし・原則返金不可・強行法規留保）を明記<br>- プライバシーポリシー第4〜8項に **Firebase Crashlytics**（起動時無効・UMP `canRequestAds` 同意連動・プライバシー設定からの撤回で停止）、**Google Play Billing Library**（決済情報は Google Play 処理・開発者非取得）、**Google Play In-App Updates API** を追記し、既存の Google AdMob / UMP / In-App Review およびローカル保存・Android Auto Backup と完全整合<br>- GDPR / UK GDPR 必須項目（データ管理者 `fooDev`、第6条法的根拠、第7条 UMP 同意管理・アプリ内プライバシー設定からの変更/撤回、第8条/COPPA 子どものプライバシー、第15〜22条・第77条 データ主体の権利と監督機関への不服申立権、第5章 域外移転保護措置、保存期間）を日英双方に整備<br>- 利用規約第5条・第8条に EU/EEA・英国等の強行的な消費者保護法規の留保条項を追記、連絡先メールアドレスの `mailto:` リンク修正 |
| **Version 2.1** | 2026-11-25（2026年11月25日） | アプリ運用向け Remote Config 静的 JSON（`config.json`）を追加（利用規約バージョン管理・6言語対応の緊急お知らせ配信機能、M3 #20 対応） |

## お問い合わせ / Contact

- **Developer / Data Controller:** fooDev
- **Email:** [fullfocustimerdev@gmail.com](mailto:fullfocustimerdev@gmail.com)
