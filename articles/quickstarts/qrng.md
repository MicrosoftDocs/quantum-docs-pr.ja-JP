---
title: 量子乱数ジェネレーターの作成
description: 量子乱数ジェネレーターを作成することで、重ね合わせなど、基本的量子概念を実証する Q# プロジェクトを構築します。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: b9c8592b1296a7de1b9ad5d0538ad1972ec25e31
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "77906986"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>クイック スタート:Q# で量子乱数ジェネレーターを実装する
Q# で記述された量子アルゴリズムの単純な例が量子乱数ジェネレーターです。 このアルゴリズムでは、量子力学の性質を活用し、乱数を生成します。 

## <a name="prerequisites"></a>前提条件

- Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。
- [Q# プロジェクトを作成する](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Q# 操作を記述する

### <a name="q-operation-code"></a>Q# 操作コード

1. Operation.qs ファイルの内容を次のコードに置き換えます。

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

「[量子コンピューティングとは](xref:microsoft.quantum.overview.what)」という記事で述べたように、キュービットとは、重ね合わせに入ることができる量子情報の単位です。 測定されるとき、キュービットは 0 か 1 だけになります。 ただし、実行中、キュービットの状態は測定で 0 または 1 を読み取る可能性を表わします。 この確率論的な状態が重ね合わせと呼ばれています。 この確率を使用し、乱数を生成できます。

今回の Q# 操作では、Q# ネイティブの `Qubit` データ型を導入します。 `Qubit` は `using` ステートメントでのみ割り当てることができます。 割り当て後、キュービットは常に `Zero` 状態になります。 

`H` 操作を使用することで、`Qubit` を重ね合わせに入れることができます。 キュービットを測定し、その値を読み取るには、`M` 組み込み操作を使用します。

重ね合わせに `Qubit` を入れ、測定することで、コードを呼び出すたびに結果は異なる値になります。 

`Qubit` の割り当てが解除されるとき、`Zero` 状態に明示的に戻す必要があります。戻さない場合、シミュレーターからランタイム エラーが報告されます。 これを実現する簡単な方法は `Reset` を呼び出すことです。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>ブロッホ球でコードを視覚化する

ブロッホ球では、北極は古典的な値 **0** を表し、南極は古典的な値 **1** を表します。 重ね合わせは球上の点で表わすことができます (矢印で表わされています)。 矢印の端が極に近づけば近づくほど、測定時、その極に割り当てられる古典的な値にキュービットがなる確率が高くなります。 たとえば、下の赤い矢印で表わされているキュービットの状態では、測定したとき、値 **0** が与えられる可能性が高くなります。

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

この表現を利用し、コードの動作を視覚化できます。

* まず、状態 **0** で初期化されたキュービットから始め、`H` を適用し、**0** と **1** の確率が同じになる重ね合わせを作成します。

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">


* 次に、キュービットを測定し、出力を保存します。

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

測定の結果は完全にランダムになるため、ランダム ビットが 1 つ取得されました。 この操作を複数回呼び出し、整数を作成できます。 たとえば、操作を 3 回呼び出してランダム ビットを 3 つ取得する場合、ランダムの 3 ビット数 (つまり、0 から 7 までの乱数) を構築できます。

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a>ホスト プログラムを使用した完全な乱数ジェネレーターを作成する

ランダム ビットを生成する Q # 操作ができたので、それを使用して、ホスト プログラムを使用した完全な量子乱数ジェネレーターを作成できます。

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した Python](#tab/tabid-python)
 
 Python から新しい Q# プログラムを実行するには、次のコードを `host.py` として保存します。
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 次に、コマンド ラインから Python ホスト プログラムを実行できます。
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した C#](#tab/tabid-csharp)
 
 C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 次に、コマンド ラインから C# ホスト プログラムを実行できます。
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[Visual Studio 2019 を使用した C#](#tab/tabid-vs2019)

 Visual Studio で C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 その後、F5 キーを押すと、プログラムは実行を開始し、乱数が生成されている新しいウィンドウがポップアップ表示されます。 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
