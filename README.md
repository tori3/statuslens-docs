<p align="center">
  <img src="assets/statuslens-logo-256.png" width="128" alt="StatusLens logo" />
</p>

<h1 align="center">StatusLens – Time in Status for Jira</h1>

<p align="center">
  「どのステータスで止まっているか」を一目で。日本語対応の Time in Status アプリ<br/>
  See where work gets stuck — time in status for every Jira issue and project.
</p>

---

📘 日本語 | [English](#english)

## StatusLens とは

StatusLens は、Jira 課題が各ステータスにどれだけ滞留したかを可視化する Atlassian Forge アプリです。

- **課題パネル** — 課題画面でステータス別の滞留時間を表示
- **プロジェクトレポート** — 課題×ステータスの滞留時間テーブルと平均値
- **CSV エクスポート** — Excel でそのまま使える UTF-8 BOM 付き
- **日本語 / 英語 UI** — ユーザーの Jira 言語設定に自動で追従

> 🔒 **プライバシー**: 課題データを外部に送信・保存しません。すべての処理は
> Atlassian のインフラ(Forge)内で完結します。保存されるのはフィルタ設定と
> 15 分で失効する集計キャッシュのみです。

## 使い方

### 課題パネル(課題ごとの滞留時間)

1. 任意の課題を開く
2. タイトル下の **「+」ボタンの隣にあるアプリアイコン** をクリック
3. **StatusLens: Time in Status** を選択

ステータスごとの累計滞留時間が表示されます。同じステータスを往復した場合は
合算され、現在のステータスには「現在」バッジが付きます。

### プロジェクトレポート

1. プロジェクトのタブバーで **More（その他）** → **StatusLens: Time in Status**
2. フィルタを設定して **レポート実行**
   - **追加 JQL**(任意): `assignee = currentUser()` のように絞り込み
   - **期間**: 作成日または解決日ベース
   - **対象ステータス**: 未選択なら全ステータスを表示
3. 課題×ステータスの滞留時間テーブルと**平均行**が表示されます(最大 500 課題)
4. **CSV ダウンロード** で出力(表示形式と秒数の両方の列を含みます)

フィルタ条件はプロジェクトごとに保存され、次回訪問時に復元されます。

## FAQ

**Q. 必要な権限は?**
`read:jira-work`(課題と変更履歴の読み取り)と `storage:app`(設定・キャッシュの保存)のみです。

**Q. データはどこに保存されますか?**
課題データ自体は保存しません。フィルタ設定と集計結果キャッシュ(TTL 15分)を
Atlassian Forge のストレージに保存するだけで、外部サーバーは一切使用しません。

**Q. レポートの結果が古い気がします**
高速化のため 15 分間キャッシュが効きます。「キャッシュされた結果を表示しています」
と表示されている場合、フィルタを一度変更して戻すと再計算されます。

**Q. 滞留時間の計算方法は?**
課題の変更履歴(changelog)のステータス遷移から算出します。期間 = 次の遷移時刻 −
当該ステータス開始時刻。現在のステータスは「今」までを計算します。往復した場合は合算です。

## サポート

- 🐛 バグ報告・機能要望: [GitHub Issues](https://github.com/tori3/statuslens-docs/issues)
- ✉️ メール: trammel-orbiter-5p@icloud.com
- 対応言語: 日本語 / English

---

## English

StatusLens visualizes how long your Jira issues spend in each status, built on Atlassian Forge.

- **Issue panel** — per-status time for the issue you're viewing
- **Project report** — issues × statuses table with per-status averages
- **CSV export** — UTF-8 with BOM, Excel-friendly
- **Japanese / English UI** — follows each user's Jira language setting

> 🔒 **Privacy**: your issue data never leaves Atlassian's infrastructure.
> StatusLens stores only filter settings and an aggregate cache that expires
> after 15 minutes — no external servers involved.

### Using the issue panel

1. Open any issue
2. Click the **apps icon next to the "+" button** under the issue title
3. Select **StatusLens: Time in Status**

Time is aggregated across round trips (e.g., an issue that bounced back to
In Review twice), and the current status keeps counting until now.

### Using the project report

1. In your project's tab bar, choose **More** → **StatusLens: Time in Status**
2. Set filters and hit **Run report**
   - **Additional JQL** (optional), **date range** (created/resolved based), and **statuses**
3. Review the issues × statuses table with the **average row** (up to 500 issues)
4. **Download CSV** — includes both human-readable durations and raw seconds

Filters are saved per project and restored on your next visit.

### FAQ

**Q. What permissions does it need?**
Only `read:jira-work` (read issues and changelogs) and `storage:app` (save settings/cache).

**Q. Where is my data stored?**
Issue data is never stored. Only filter settings and a 15-minute aggregate cache
are kept in Atlassian Forge storage. No external servers.

**Q. How is time in status calculated?**
From the issue changelog: duration = next transition time − status entry time.
The current status counts up to now, and repeated visits are summed.

### Support

- 🐛 Bugs & feature requests: [GitHub Issues](https://github.com/tori3/statuslens-docs/issues)
- ✉️ Email: trammel-orbiter-5p@icloud.com
- Support languages: Japanese / English
