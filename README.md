# タイタニック号 生存者予測分析ノートブック

[![Language](https://img.shields.io/badge/language-Python-blue.svg)](https://www.python.org/)
[![Library](https://img.shields.io/badge/library-Pandas-brightgreen.svg)](https://pandas.pydata.org/)
[![Library](https://img.shields.io/badge/library-Scikit--learn-orange.svg)](https://scikit-learn.org/stable/)

Kaggleの有名コンペティション「**Titanic - Machine Learning from Disaster**」に取り組んだ際の分析ノートブックです。
データ分析の基本的な流れである、**データ読み込み → データ探索 → 前処理 → モデル学習 → 予測** の一連のプロセスをPythonで実装しています。

---

##  概要

このプロジェクトは、タイタニック号の乗客データ（年齢、性別、客室等級など）を元に、機械学習モデルを用いて「その乗客が生存したかどうか」を予測するものです。データ分析の初学者にとって定番の課題であり、実践的なスキルを身につけることを目的としました。

### このノートブックで実施していること

1.  **データの探索的分析 (EDA)**:
    - `pandas`を使用してデータを読み込み、`head()`, `info()`, `describe()`で全体像を把握。
    - `seaborn`と`matplotlib`を用いて、生存率と各特徴量（性別、客室等級、年齢など）との関係を可視化。

2.  **データ前処理**:
    - 不要なカラム（乗客ID, 名前, チケット番号など）の削除。
    - カテゴリカル変数（性別, 乗船港）を数値に変換（Label Encoding, One-Hot Encoding）。
    - 欠損値（年齢, 運賃）を中央値で補完。

3.  **モデル学習と評価**:
    - データを訓練用とテスト用に分割 (`train_test_split`)。
    - **決定木 (`DecisionTreeClassifier`)** と **ランダムフォレスト (`RandomForestClassifier`)** の2つのモデルで学習と評価を実施。
    - `accuracy_score`を用いてモデルの正解率を評価し、精度の向上を確認。

4.  **Kaggleへの提出**:
    - 全ての訓練データを用いてモデルを再学習。
    - テストデータに対して予測を行い、Kaggleの提出形式に合わせた `submission.csv` ファイルを作成。

##  使用技術

-   **言語**: Python 3
-   **ライブラリ**:
    -   Pandas: データ操作・分析
    -   Scikit-learn: 機械学習モデルの構築・評価
    -   Seaborn, Matplotlib: データの可視化

##  結果

-   **決定木モデル**: 正解率 **78.77%**
-   **ランダムフォレストモデル**: 正解率 **81.56%**

ランダムフォレストを用いることで、モデルの予測精度が向上することが確認できました。

##  ファイル構成

```
.
├── Titanic.ipynb     # 分析に使用したJupyter Notebook
├── train.csv         # 訓練用データ
├── test.csv          # テスト用データ
└── submission.csv    # 生成されたKaggle提出用ファイル
