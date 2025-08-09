# powerbi-project-dashboard
# Power BI プロジェクト進捗ダッシュボード

## 概要
Power BI を用いたプロジェクト進捗ダッシュボードです。
実運用では `data/project_data.csv` を OneDrive/SharePoint に置き、Power BI Service で自動更新を設定します。

## 含まれるファイル
- `data/project_data.csv` — サンプルデータ（CSV）
- `pbix_placeholder.md` — PBIX の作り方手順

## サンプルデータ仕様（project_data.csv）
カラム: Project, TaskID, TaskName, Owner, StartDate, EndDate, ProgressPercent, Status

## Power BI レポート作成手順（短縮版）
1. Power BI Desktop を開く
2. `Get Data` → `Text/CSV` を選び、`data/project_data.csv` を読み込む
3. Power Query で日付カラムを適切な型にする
4. レポート画面で以下を作成:
   - ガント風チャート（Bar chart + Start/Endを使う）
   - KPIカード（平均 ProgressPercent）
   - Stacked bar：Team別 Progress
   - Table: Overdue tasks (EndDate < Today & ProgressPercent < 100)
5. ファイルを保存して `.pbix` としてエクスポート
6. Power BI Service に公開し、データセットの自動更新を OneDrive または SharePoint に紐づける

## デモ画像
