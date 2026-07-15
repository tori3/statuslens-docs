# StatusLens – データ取り扱い・プライバシーに関する声明

_最終更新: 2026-07-15_

[English version](PRIVACY.md) | 日本語版

StatusLens は Atlassian Forge プラットフォーム上で動作し、**Atlassian のインフラの外に
データを送信・保存することは一切ありません**(外部 egress ゼロ)。

## 保存するデータ

| データ | 保存場所 | 保持期間 |
|---|---|---|
| レポートのフィルタ設定(JQL・期間・ステータス選択) | Atlassian Forge Storage(プロジェクト単位) | ユーザーが変更するまで |
| レポート集計結果のキャッシュ(課題キーとステータス別滞留秒数) | Atlassian Forge Storage | 15 分(TTL) |

## 保存しないデータ

- 課題の内容(サマリ・説明・コメント・添付など)は**保存しません**。表示のたびに Jira API から取得します
- 個人データ(氏名・メールアドレス等)は**収集・保存しません**
- Cookie・外部アナリティクス・トラッキングは使用しません

## 権限(スコープ)

- `read:jira-work` — 課題と変更履歴(changelog)の読み取り。滞留時間の計算に使用
- `storage:app` — 上記のフィルタ設定・キャッシュの保存

## お問い合わせ

データの取り扱いに関する質問は statuslens.security@en-rai.net または
[GitHub Issues](https://github.com/tori3/statuslens-docs/issues) までお寄せください。
