---
title: クォンタム Machine Learning ライブラリを使用した基本的な分類
description: Q#Microsoft QDK の quantum Machine Learning ライブラリを使用して、で記述されたクォンタムシーケンシャル分類器を実行する方法について説明します。
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5dc4614b9992e2c6b9f8ff4b839c0929ec8cab7c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833719"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>基本分類: QDK でデータを分類する

このクイックスタートでは、で記述されたクォンタムシーケンシャル分類器を実行する方法につい Q# Machine Learning て説明します。 

このガイドでは、「」で定義されている分類子構造を使用して、半月のデータセットを使用し Q# ます。

## <a name="prerequisites"></a>前提条件

- Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。
- Q# [Python ホストプログラム](xref:microsoft.quantum.install.python)または[C# ホストプログラム](xref:microsoft.quantum.install.cs)のいずれかのプロジェクトを作成します。

## <a name="host-program"></a>ホストプログラム

ホストプログラムは、次の3つの部分で構成されます。

- データセットを読み込み、モデルの開始パラメーターのセットを選択します。
- トレーニングを実行して、モデルのパラメーターとバイアスを決定します。
- モデルを検証してその精度を確認する

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した Python](#tab/tabid-python)

    Python の分類子であるを実行するには、 Q# 次のコードをとして保存し `host.py` ます。 Q# `Training.qs` このチュートリアルの後半で説明するファイルも必要であることに注意してください。

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    次に、コマンド ラインから Python ホスト プログラムを実行できます。

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した C#](#tab/tabid-csharp)

    C# の分類子であるを実行するには、 Q# 次のコードをとして保存し `Host.cs` ます。 Q# `Training.qs` このチュートリアルの後半で説明するファイルも必要であることに注意してください。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    次に、コマンド ラインから C# ホスト プログラムを実行できます。

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 を使用した C#](#tab/tabid-vs2019)

    Q#Visual Studio で c# から新しいプログラムを実行するには、 `Host.cs` 次の c# コードを含むようにを変更します。 Q# `Training.qs` このチュートリアルの後半で説明するファイルも必要であることに注意してください。

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    F5 キーを押すと、プログラムの実行が開始されます。 新しいウィンドウには、次の結果が表示されます。 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Q \# 分類器コード

次に、ホストプログラムによって呼び出された操作がでどのように定義されているかを見てみましょう Q# 。
次のコードをという名前のファイルに保存 `Training.qs` します。

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

上記のコードで定義されている最も重要な関数と操作は次のとおりです。

- `ClassifierStructure() : ControlledRotation[]` : この関数では、考慮する制御ゲートのレイヤーを追加することによって、サーキットモデルの構造を設定します。 この手順は、シーケンシャルなディープラーニングモデルでのニューロンのレイヤーの宣言に似ています。
- `TrainHalfMoonModel() : (Double[], Double)` : この操作はコードの中核となる部分で、トレーニングを定義します。 ここでは、ライブラリに含まれるデータセットからサンプルを読み込みます。ここでは、トレーニングのハイパーパラメーターと初期パラメーターを設定し、ライブラリに含まれる操作を呼び出してトレーニングを開始し `TrainSequentialClassifier` ます。 パラメーターと、分類子を決定するバイアスを出力します。
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : この操作では、モデルを評価するための検証プロセスを定義します。 ここでは、検証用のサンプル、サンプルごとの測定数、および許容範囲を読み込みます。 検証用に選択されたサンプルのバッチに誤分類の数が出力されます。

## <a name="next-steps"></a>次のステップ

まず、コードを使用して再生し、いくつかのパラメーターを変更してトレーニングにどのように影響するかを確認することができます。 次のチュートリアル「 [独自の分類子の設計](xref:microsoft.quantum.libraries.machine-learning.design)」では、分類子の構造を定義する方法を学習します。
