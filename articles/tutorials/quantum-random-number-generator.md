---
title: 量子乱数ジェネレーターの作成
description: Q#クォンタムの乱数ジェネレーターを作成することによって、法則のような基本的なクォンタムの概念を示すプロジェクトをビルドします。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
no-loc:
- Q#
- $$v
ms.openlocfilehash: d80f1c640ac7ddb0104ccbbb6de6d0e26ba05fd6
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863621"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a>チュートリアル:Q\# で量子乱数ジェネレーターを実装する

で記述されたクォンタムアルゴリズムの簡単な例 Q# は、クォンタム乱数ジェネレーターです。 このアルゴリズムでは、量子力学の性質を活用し、乱数を生成します。

## <a name="prerequisites"></a>前提条件

- Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。
- Q# [ Q# アプリケーション](xref:microsoft.quantum.install.standalone)、 [Python ホストプログラム](xref:microsoft.quantum.install.python)、または[C# ホストプログラム](xref:microsoft.quantum.install.cs)のいずれかのプロジェクトを作成します。

## <a name="write-a-no-locq-operation"></a>操作を記述する Q#

### <a name="no-locq-operation-code"></a>Q# 操作コード

1. Program.qs ファイルの内容を次のコードに置き換えます。

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

「[量子コンピューティングについて](xref:microsoft.quantum.overview.understanding)」という記事で述べたように、キュービットとは、重ね合わせに入ることができる量子情報の単位です。 測定されるとき、キュービットは 0 か 1 だけになります。 ただし、実行中、キュービットの状態は測定で 0 または 1 を読み取る可能性を表わします。 この確率論的な状態が重ね合わせと呼ばれています。 この確率を使用し、乱数を生成できます。

この操作では、 Q# `Qubit` にネイティブなデータ型を導入 Q# します。 `Qubit` は `using` ステートメントでのみ割り当てることができます。 割り当て後、キュービットは常に `Zero` 状態になります。 

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

これで、ランダムなビットを生成する操作ができるようになりました。これを Q# 使用して、完全なクォンタム乱数ジェネレーターを構築できます。 アプリケーションを使用することも、 Q# ホストプログラムを使用することもできます。



### <a name="no-locq-applications-with-visual-studio-or-visual-studio-code"></a>[Q# Visual Studio または Visual Studio Code を使用したアプリケーション](#tab/tabid-qsharp)

完全なアプリケーションを作成するには Q# 、次のエントリポイントをプログラムに追加し Q# ます。 

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

### <a name="python-with-visual-studio-code-or-the-command-prompt"></a>[Visual Studio Code またはコマンドプロンプトを使用した Python](#tab/tabid-python)

Python から新しいプログラムを実行するには Q# 、次のコードをとして保存し `host.py` ます。

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

次に、コマンドプロンプトから Python ホストプログラムを実行します。

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[Visual Studio Code または Visual Studio を使用する C#](#tab/tabid-csharp)

C# から新しいプログラムを実行するには Q# 、 `Driver.cs` 次の c# コードを含むようにを変更します。

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

次に、コマンドプロンプトから C# ホストプログラムを実行できます (Visual Studio では、F5 キーを押す必要があります)。

```bash
$ dotnet run
The random number generated is 42
```

***
