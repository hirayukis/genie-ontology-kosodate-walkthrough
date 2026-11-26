# Genie Ontology ウォークスルー ― 子育てモックデータ編

Databricks **Genie Ontology** の効果を、Metric View・テーブルコメント・認証タグ・Genie Agent を使わずに確かめるためのノートブックです。使うのは Ontology の2つの入口だけです。

- **Step A: Learned knowledge** ― 定義どおりに書いた SQL をクエリ履歴に残し、Genie が snippet を自動で抽出するかを見る
- **Step B: Pages** ― 用語の公式定義を Page として公開する

データは子育て記録アプリを想定したモックで、乱数シードを固定して生成します。夜泣き、ワンオペ率、病児呼び出し、子育て費用、睡眠充足率といった用語は、解釈が人によって分かれやすいので、それを答えが変わるかどうかの判定に使います。

## 使い方

1. `genie_ontology_kosodate_walkthrough.ipynb` を Databricks ワークスペースにインポートします（Free Edition でも動作確認済み）
2. ウィジェット `step` を `part1` → `stepA` → `stepB` → `cleanup` の順に切り替え、毎回 *Run all* で実行します
3. 各 step のあとに、Genie One で同じ5問を質問し、ノートブック内の正解表と比べます

実行には、SQL ウェアハウスの使用権限と、スキーマを作成する権限が必要です（既定は `workspace.kosodate_log`）。Step B では、アカウントの既定ドメイン「General」に Page を公開します。片付けは `cleanup` で行えます。

参考: https://docs.databricks.com/aws/en/genie/genie-ontology/
