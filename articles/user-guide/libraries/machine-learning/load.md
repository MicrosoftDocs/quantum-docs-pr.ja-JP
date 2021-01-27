---
title: 典型的データを読み込んでいます
description: Microsoft Quantum Development Kit (QDK) を使用して、独自のデータセットを読み込んで分類器モデルをトレーニングする方法について説明します。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856451"
---
# <a name="load-and-classify-your-own-datasets"></a>独自のデータセットを読み込んで分類する

この短いチュートリアルでは、独自のデータセットを読み込んで、Quantum 開発キット (QDK) で分類器モデルをトレーニングする方法について説明します。

データの格納には、 [JSON ファイル](https://en.wikipedia.org/wiki/JSON) などの標準化されたシリアル化形式を使用することを強くお勧めします。
このような形式では、Python や .NET エコシステムなどのさまざまなフレームワークとの高い互換性が提供されます。
特に、サンプルから直接コードをコピーして貼り付けることができるように、データの読み込みにテンプレートを使用することをお勧めします。

## <a name="template-for-loading-your-datasets"></a>データセットを読み込むためのテンプレート

$N = $2 のトレーニングデータセット $ (x, y) $ があるとします。この場合、$x $ の各インスタンス $x _i $ には、$x _ {i1} $、$x _ {i2} $、$x _ {i3} $ という3つの特徴があります。
検証データセットの構造は同じです。
これらの datsets は `data.json` 、次のようなファイルで表すことができます。

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>テンプレートを使用した例

さまざまな猫や犬の高さと重みを持つ小さなデータセットがあるとします。 このデータセットは、モデルのトレーニングには非常に小さなものですが、データセットを読み込むプロセスを示すのに十分です。

| 高さ (m) | Weight (kg) | 動物 |
|-----------|------------|--------|
| 0.54      | 30         | Dog    |
| 0.30      | 8          | 猫    |
| 0.91      | 44         | Dog    |
| 0.86      | 31          | Dog    |
| 0.32      | 5         | 猫    |
| 0.25      | 4          | 猫    |

手順です。

- まず、データセットをトレーニングと検証に分割する必要があります。 このケースでは、最初の3つのサンプルでトレーニングを行い、残りのサンプルで検証を行うことができます。 一般に、トレーニングデータの不要なバイアスを避けるために、トレーニングと検証のデータセットをランダムにサンプリングすることをお勧めします。
- 次に、各クラスに数値ラベルを割り当てる必要があります。 現時点では、QML ライブラリは二項分類の問題のみを使用することに注意してください。 ここでは、ラベル0をクラスに割り当て、 `Dog` 番号1をクラスに割り当てます `Cat` 。
- 最後に、データセットのデータを使用して、テンプレートに入力します。 大規模なデータセットの場合は、特定のデータセットからテンプレートを自動的に生成するための小さなスクリプトを作成する必要があることに注意してください。 このスクリプトは、データセットの元の形式によって異なります。

データセットの場合、 `data.json` ファイルは次のようになります。

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>データを読み込む

データを JSON ファイルとしてシリアル化したら、選択したホスト言語で提供される JSON ライブラリを使用して、データを読み込むことができます。

### <a name="python"></a>[Python](#tab/tabid-python)

Python には、JSON でシリアル化されたデータを操作するための [組み込み `json` パッケージ](https://docs.python.org/3.7/library/json.html) が用意されています。

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

.NET Core プラットフォームは、JSON でシリアル化されたデータを処理するための[ `System.Text.Json` パッケージ](https://www.nuget.org/packages/System.Text.Json)を提供します。

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>次のステップ

これで、独自のデータセットを使用して独自の実験の実行を開始する準備が整いました。 さまざまな分類子とデータセットを試し、結果を共有するコミュニティに投稿してください。
