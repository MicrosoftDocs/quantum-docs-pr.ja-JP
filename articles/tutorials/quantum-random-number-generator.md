---
title: 量子乱数ジェネレーターの作成
description: 量子乱数ジェネレーターを作成することで、重ね合わせなど、基本的量子概念を実証する Q# プロジェクトを構築します。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 18e8975e513a87c0a67a6dbb5586cc7dab5a93fb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275287"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>チュートリアル:Q\# で量子乱数ジェネレーターを実装する

Q# で記述された量子アルゴリズムの単純な例が量子乱数ジェネレーターです。 このアルゴリズムでは、量子力学の性質を活用し、乱数を生成します。

## <a name="prerequisites"></a>前提条件

- Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。
- [コマンド ラインから Q# を使用するため](xref:microsoft.quantum.install.standalone)、または [Python ホスト プログラム](xref:microsoft.quantum.install.python) または [C# ホスト プログラム](xref:microsoft.quantum.install.cs)で使用するために、Q# プロジェクトを作成します。

## <a name="write-a-q-operation"></a>Q# 操作を記述する

### <a name="q-operation-code"></a>Q# 操作コード

1. Program.qs ファイルの内容を次のコードに置き換えます。

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

「[量子コンピューティングについて](xref:microsoft.quantum.overview.understanding)」という記事で述べたように、キュービットとは、重ね合わせに入ることができる量子情報の単位です。 測定されるとき、キュービットは 0 か 1 だけになります。 ただし、実行中、キュービットの状態は測定で 0 または 1 を読み取る可能性を表わします。 この確率論的な状態が重ね合わせと呼ばれています。 この確率を使用し、乱数を生成できます。

今回の Q# 操作では、Q# ネイティブの `Qubit` データ型を導入します。 `Qubit` は `using` ステートメントでのみ割り当てることができます。 割り当て後、キュービットは常に `Zero` 状態になります。 

`H` 操作を使用することで、`Qubit` を重ね合わせに入れることができます。 キュービットを測定し、その値を読み取るには、`M` 組み込み操作を使用します。

重ね合わせに `Qubit` を入れ、測定することで、コードを呼び出すたびに結果は異なる値になります。

`Qubit` の割り当てが解除されるとき、`Zero` 状態に明示的に戻される必要があります。戻されない場合、シミュレーターからランタイム エラーが報告されます。 これを実現する簡単な方法は `Reset` を呼び出すことです。

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>ブロッホ球でコードを視覚化する

ブロッホ球では、北極は古典的な値 **0** を表し、南極は古典的な値 **1** を表します。 重ね合わせは球上の点で表わすことができます (矢印で表わされています)。 矢印の端が極に近づけば近づくほど、測定時、その極に割り当てられる古典的な値にキュービットがなる確率が高くなります。 たとえば、下の赤い矢印で表わされているキュービットの状態では、測定したとき、値 **0** が与えられる可能性が高くなります。

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

この表現を利用し、コードの動作を視覚化できます。

* まず、状態 **0** で初期化されたキュービットから始め、`H` を適用し、**0** と **1** の確率が同じになる重ね合わせを作成します。

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* 次に、キュービットを測定し、出力を保存します。

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

測定の結果は完全にランダムになるため、ランダム ビットが 1 つ取得されました。 この操作を複数回呼び出し、整数を作成できます。 たとえば、操作を 3 回呼び出してランダム ビットを 3 つ取得する場合、ランダムの 3 ビット数 (つまり、0 から 7 までの乱数) を構築できます。


## <a name="creating-a-complete-random-number-generator"></a>完全な乱数ジェネレーターの作成

ランダム ビットを生成する Q# 操作ができたので、それを使用して、完全な量子乱数ジェネレーターを作成できます。 Q# コマンド ライン アプリケーションを使用することも、ホスト プログラムを使用することもできます。



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[Visual Studio または Visual Studio Code を使用する Q# コマンド ライン アプリケーション](#tab/tabid-qsharp)

完全な Q# コマンドライン アプリケーションを作成するには、使用する Q# プログラムに次のエントリ ポイントを追加します。 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

実行可能ファイルは、プロジェクトの構成とコマンドライン オプションに応じて、シミュレーターまたはリソース推定機能で `@EntryPoint()` 属性でマークされた操作または関数を実行します。

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

Visual Studio では、Ctrl キーを押しながら F5 キーを押すだけでスクリプトを実行します。

VS Code では、ターミナルで次のように入力して、Program.qs の初回のビルドを行います。

```dotnetcli
dotnet build
```

以降の実行では、再度ビルドする必要はありません。 これを実行するには、次のコマンドを入力して、Enter キーを押します。

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Visual Studio Code またはコマンド ラインを使用した Python](#tab/tabid-python)

Python から新しい Q# プログラムを実行するには、次のコードを `host.py` として保存します。

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

次に、コマンド ラインから Python ホスト プログラムを実行できます。

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[Visual Studio Code または Visual Studio を使用する C#](#tab/tabid-csharp)

C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

次に、コマンド ラインから C# ホスト プログラムを実行できます (Visual Studio では、F5 キーを押す必要があります)。

```bash
$ dotnet run
The random number generated is 42
```

***
