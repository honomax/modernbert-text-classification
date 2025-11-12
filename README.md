# 長文テキスト分類プログラム
- このプロジェクトでは、CSVファイルの文章データを用いてBERT系モデル（ModernBERT）をテキスト分類に適用しています。
- データ前処理 → モデル学習 → 評価の流れによる全体フローを実装しています。
- Google Colab環境での実行を想定し、Googleドライブ上でモデルの保存・読み込みを行う仕組みです。

# CSVファイルの準備
- ```text```列と```label```列にそれぞれテキスト、数値データが入ったcsvファイルを用意
- ```sample.csv```ファイルを目的に合わせて編集してください
- ```data```ファイル直下に配置

# プログラム概要
- ライブラリのインポート
- CSVデータの読み込み
- シードの固定
- データセットクラスの定義
- モデル・トークナイザの準備
- データ分割（訓練・検証・テスト）
- 層化K分割交差検証の準備・学習
- ベストモデルの保存
-テストデータでの評価

# 使用モデル
- 使用したモデル：answerdotai/ModernBERT-base (詳細URL: https://huggingface.co/answerdotai/ModernBERT-base)
- 長文のコンテキスト(最大8192トークン)を扱える設計

# 実装のポイント
- 乱数シードを固定し再現性の確保に配慮
- 交差検証による評価とFoldごとの平均精度を算出
- モデル保存・ロード時はGoogleドライブ内の指定パスを利用

# ベストモデルの保存
最も良い性能を示したベストモデルは```model```ファイルに配置されます。

## License

This repository includes code and model weights derived from ModernBERT, licensed under the Apache License 2.0.

This project as a whole is licensed under the MIT License.

See the LICENSE and LICENSE-APACHE files for details.
