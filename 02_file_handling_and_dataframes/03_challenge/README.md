## **チャレンジ3: Pandasによるアイリスのデータセットの探索と特徴量エンジニアリング**

**目的**: アイリスのデータセットの探索と拡張を通じて、Pandasを使用したデータ操作、特徴量エンジニアリング、分析について理解を深めます。

**概要**: 
アイリスのデータセットは、機械学習や統計学の分野で従来から使われています。150種類のアイリスの花の観察結果 (ガクの長さ、ガクの幅、花弁の長さ、花弁の幅の測定値など) と、品種の分類で構成されています。品種には、アイリス・セトーサ (Iris Setosa)、アイリス・バーシコラー (Iris Versicolour)、アイリス・ヴァージニカ (Iris Virginica) などがあります。

**タスク**

1. **データの読み込みと概要**
    - アイリスのデータセットをDataFrameに読み込みます (以下に手順を記載)。
    - 概要として最初の5行を表示します。
2. **データのクリーニングと検証**
    - 欠損値またはnull値の存在を確認します。
    - 各列のデータ型を確認します (例: 測定値の場合は数値型)。
3. **基本的な分析と基本統計量**
    - 数値型の各特徴量について、基本統計量 (平均値、中央値、標準偏差) を計算します。
    - DataFrameを新規作成します。各行が1つの特徴量を表し、各列に計算した統計情報を格納するようにします。これをCSV形式で出力します。
4. **特徴量エンジニアリング**
    - 新しい列 **`sepal_area`** (ガクの面積) を追加します。この値は、ガクの長さ×ガクの幅で算出します。
    - 別の列 **`petal_area`** (花弁の面積) も追加します。この値は、花弁の長さ×花弁の幅で算出します。
    - これらの新しい特徴量の基本統計量を算出し、統計情報のDataFrameに追加します。
5. **データのフィルタリング** 
    1. 与えられた基準にもとづいてデータをフィルタリングする関数を書きます (例: ある列の値がしきい値を下回る行を除外する)。
6. **データのエクスポート**
    1. DataFrameをCSV形式で保存します。 
    2. このチャレンジの成果物は自動採点されませんが、GitHubにプッシュする際に自分のDataFrameを含めるようにしてください。 

### アイリスのデータセットの読み込み

**データの読み込み**

- **`pip install scikit-learn`** コマンドを使用して **`scikit-learn`** をインストールします (まだインストールしていない場合)。
- **`sklearn.datasets`** からアイリスのデータセットを読み込みます。

```python
# 必要なライブラリをインポートする
import pandas as pd
from sklearn import datasets

# アイリスのデータセットを読み込み、DataFrameに変換する
iris = datasets.load_iris()
iris_df = pd.DataFrame(iris.data, columns=iris.feature_names)

# 品種の列を追加し、0～2の番号を記入する (各番号が異なる品種を表す)
iris_df['species'] = iris.target
```

- アイリスのデータセットに関する詳細情報
    - https://scikit-learn.org/stable/auto_examples/datasets/plot_iris_dataset.html (英語)