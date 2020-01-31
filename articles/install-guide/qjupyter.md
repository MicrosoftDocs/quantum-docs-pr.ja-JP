---
title: 'Q # Jupyter notebook を使用した開発'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831071"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="62771-102">Q # Jupyter notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="62771-102">Develop with Q# Jupyter notebooks</span></span>

<span data-ttu-id="62771-103">Q # Jupyter Notebook で Q # 操作を開発するには、QDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="62771-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="62771-104">Jupyter Notebook を使用すると、命令、メモ、およびその他のコンテンツと共に、インプレースコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="62771-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="62771-105">この環境は、記述された説明や量子コンピューティングの対話型チュートリアルを使用して Q # コードを記述する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="62771-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="62771-106">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62771-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="62771-107">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="62771-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="62771-108">Q # Jupyter Notebook では、Q # コードのみを実行できます。また、操作を外部ホストプログラム (Python やC#ファイルなど) から呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="62771-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="62771-109">この環境は、外部のクラシックホストプログラムを quantum プログラムと組み合わせることが目的の場合には適していません。</span><span class="sxs-lookup"><span data-stu-id="62771-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="62771-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="62771-110">Pre-requisites</span></span>

    - <span data-ttu-id="62771-111">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="62771-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="62771-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="62771-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="62771-113">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="62771-113">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="62771-114">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="62771-114">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="62771-115">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="62771-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="62771-116">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="62771-116">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="62771-117">Jupyter notebook を開き、コマンドラインから提供された URL をブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="62771-117">To open the Jupyter notebook copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="62771-118">Q# カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="62771-118">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="62771-119">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="62771-119">Run this cell of the notebook:</span></span>

        ![Q# コードを含む Jupyter Notebook セル](~/media/install-guide-jupyter.png)

        <span data-ttu-id="62771-121">セルの出力に `SayHello` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62771-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="62771-122">Jupyter Notebook で実行すると、Q# コードがコンパイルされ、ノートブックから検出した操作の名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="62771-122">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="62771-123">新しいセルで、`%simulate` コマンドを使用して、先ほど作成した操作 (シミュレーター) を実行します。</span><span class="sxs-lookup"><span data-stu-id="62771-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![%simulate マジックのある Jupyter Notebook セル](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="62771-125">画面には、呼び出された操作の結果と共に、メッセージが出力されます (ここでは、操作は単に `Unit` 型を返すため、空のタプル `()` が表示されます)。</span><span class="sxs-lookup"><span data-stu-id="62771-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="whats-next"></a><span data-ttu-id="62771-126">次に、</span><span class="sxs-lookup"><span data-stu-id="62771-126">What's next?</span></span>

<span data-ttu-id="62771-127">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="62771-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
