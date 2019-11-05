---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 090cf98612c6c549c733e54f9dcbf74442b30fbd
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442265"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="463da-102">Microsoft Quantum Development Kit (QDK) のインストール</span><span class="sxs-lookup"><span data-stu-id="463da-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="463da-103">Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="463da-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="463da-104">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="463da-104">The QDK consists of:</span></span>

- <span data-ttu-id="463da-105">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="463da-105">the Q# programming language</span></span>
- <span data-ttu-id="463da-106">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="463da-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="463da-107">Q# で記述された量子操作を実行するホスト アプリケーション (Python または .NET 言語で記述)</span><span class="sxs-lookup"><span data-stu-id="463da-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="463da-108">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="463da-108">tools to facilitate your development</span></span>

<span data-ttu-id="463da-109">選択した開発環境に応じて、さまざまなインストール手順があります。</span><span class="sxs-lookup"><span data-stu-id="463da-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="463da-110">以下のセクションから環境を選択してください。</span><span class="sxs-lookup"><span data-stu-id="463da-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="463da-111">Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="463da-111">Develop with Python</span></span>

<span data-ttu-id="463da-112">Python 用の qsharp パッケージを使用すると、Python 内から Q# の演算と関数を簡単にシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="463da-112">The qsharp package for Python makes it easy to simulate Q# operations and functions from within Python.</span></span> <span data-ttu-id="463da-113">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="463da-113">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python that provides the core functionality for compiling and simulating Q# operations.</span></span>

1. <span data-ttu-id="463da-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="463da-114">Pre-requisites</span></span>

    - <span data-ttu-id="463da-115">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="463da-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="463da-116">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="463da-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="463da-117">.NET Core SDK 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="463da-117">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="463da-118">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="463da-118">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="463da-119">`qsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="463da-119">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="463da-120">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="463da-120">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="463da-121">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="463da-121">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - <span data-ttu-id="463da-122">Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="463da-122">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="463da-123">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="463da-123">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="463da-124">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="463da-124">Verify the output.</span></span> <span data-ttu-id="463da-125">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="463da-125">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="463da-126">Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="463da-126">Develop with Jupyter notebooks</span></span>

<span data-ttu-id="463da-127">教育機関向けの設定、科学的研究所、およびオンラインベースのコラボレーション プログラミングで好まれる Jupyter Notebook では、命令、メモ、その他のコンテンツと共に、Q# コードを含むインプレース コード実行が提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="463da-127">A favorite of academic settings, scientific labs, and online-based collaborative programming, Jupyter Notebooks offer in-place code execution—now including Q# code—along with instructions, notes, and other content.</span></span>  <span data-ttu-id="463da-128">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463da-128">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="463da-129">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="463da-129">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>


1. <span data-ttu-id="463da-130">前提条件</span><span class="sxs-lookup"><span data-stu-id="463da-130">Pre-requisites</span></span>

    - <span data-ttu-id="463da-131">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="463da-131">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="463da-132">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="463da-132">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="463da-133">.NET Core SDK 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="463da-133">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="463da-134">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="463da-134">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="463da-135">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="463da-135">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="463da-136">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="463da-136">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="463da-137">コマンド ラインに表示されている URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="463da-137">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="463da-138">例: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="463da-138">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="463da-139">Q# カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="463da-139">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="463da-140">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="463da-140">Run this cell of the notebook:</span></span>

        ![Q# コードを含む Jupyter Notebook セル](~/media/install-guide-jupyter.png)

        <span data-ttu-id="463da-142">セルの出力に `SayHello` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463da-142">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="463da-143">Jupyter Notebook で実行すると、Q# コードがコンパイルされ、ノートブックから検出した操作の名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="463da-143">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="463da-144">新しいセルで、`%simulate` マジックを使用して、作成した演算の量子コンピューターでの実行をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="463da-144">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

        ![%simulate マジックのある Jupyter Notebook セル](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="463da-146">呼び出した演算の結果 (この場合は空) と共に、メッセージが画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="463da-146">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>


## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="463da-147">Visual Studio を使用した Windows での C# の開発</span><span class="sxs-lookup"><span data-stu-id="463da-147">Develop with C# on Windows, using Visual Studio</span></span>

<span data-ttu-id="463da-148">Visual Studio には、開発者がアプリケーションを構築する際にガイドするコード補完や構文の強調表示などの優れた機能が用意されており、Q# プログラムの充実した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="463da-148">Visual Studio offers a rich environment for developing Q# programs, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="463da-149">Q# Visual Studio 拡張機能には、構文の強調表示や IntelliSense のサポートに加えて、Q# のファイルおよびプロジェクトのテンプレートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="463da-149">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting and IntelliSense support.</span></span>


1. <span data-ttu-id="463da-150">前提条件</span><span class="sxs-lookup"><span data-stu-id="463da-150">Pre-requisites</span></span>

    - <span data-ttu-id="463da-151">.NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="463da-151">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="463da-152">Q# Visual Studio 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="463da-152">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="463da-153">[Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="463da-153">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="463da-154">拡張機能を Visual Studio に追加する</span><span class="sxs-lookup"><span data-stu-id="463da-154">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="463da-155">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="463da-155">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="463da-156">新しい Q# アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="463da-156">Create a new Q# application</span></span>

        - <span data-ttu-id="463da-157">**[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="463da-157">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="463da-158">検索ボックスに、「`Q#`」と入力します</span><span class="sxs-lookup"><span data-stu-id="463da-158">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="463da-159">**[Q# Application]\(Q# アプリケーション\)** を選択します</span><span class="sxs-lookup"><span data-stu-id="463da-159">Select **Q# Application**</span></span>
        - <span data-ttu-id="463da-160">**[次へ]** を選択します</span><span class="sxs-lookup"><span data-stu-id="463da-160">Select **Next**</span></span>
        - <span data-ttu-id="463da-161">アプリケーションの名前と格納する場所を選択します</span><span class="sxs-lookup"><span data-stu-id="463da-161">Choose a name and location for your application</span></span>
        - <span data-ttu-id="463da-162">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="463da-162">Select **Create**</span></span>

    - <span data-ttu-id="463da-163">プロジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="463da-163">Inspect the project</span></span>

        <span data-ttu-id="463da-164">2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="463da-164">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="463da-165">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="463da-165">Run the application</span></span>

        - <span data-ttu-id="463da-166">**[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="463da-166">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="463da-167">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="463da-167">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="463da-168">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463da-168">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-visual-studio-code"></a><span data-ttu-id="463da-169">Visual Studio Code を使用した C# での開発</span><span class="sxs-lookup"><span data-stu-id="463da-169">Develop with C#, using Visual Studio Code</span></span>

<span data-ttu-id="463da-170">Visual Studio Code (VS Code) には、開発者がアプリケーションを構築する際にガイドするコード補完や構文の強調表示などの優れた機能が用意されており、Windows、Linux、Mac などの複数のコンピューター環境にわたって Q# プログラムの開発用の充実した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="463da-170">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="463da-171">Q# VS Code 拡張機能には、構文の強調表示と Q# コード スニペットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="463da-171">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

<span data-ttu-id="463da-172">Visual Studio Code (VS Code) には、開発者がアプリケーションを構築する際にガイドするコード補完や構文の強調表示などの優れた機能が用意されており、Windows、Linux、Mac などの複数のコンピューター環境にわたって Q# プログラムの開発用の充実した環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="463da-172">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs across many multiple computer environments, including Windows, Linux and Mac, offering great features like code completion and syntax highlighting that guide the developer in building their applications.</span></span>  <span data-ttu-id="463da-173">Q# VS Code 拡張機能には、構文の強調表示と Q# コード スニペットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="463da-173">The Q# VS Code extension contains syntax highlighting, and Q# code snippets.</span></span>

1. <span data-ttu-id="463da-174">前提条件</span><span class="sxs-lookup"><span data-stu-id="463da-174">Pre-requisites</span></span>

   - [<span data-ttu-id="463da-175">VS Code</span><span class="sxs-lookup"><span data-stu-id="463da-175">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="463da-176">.NET Core SDK 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="463da-176">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="463da-177">Quantum VS Code 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="463da-177">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="463da-178">[VS Code 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールする</span><span class="sxs-lookup"><span data-stu-id="463da-178">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="463da-179">量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="463da-179">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="463da-180">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="463da-180">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="463da-181">**[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="463da-181">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="463da-182">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="463da-182">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="463da-183">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="463da-183">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="463da-184">新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="463da-184">Create a new project:</span></span>

        - <span data-ttu-id="463da-185">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="463da-185">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="463da-186">**[Q#:Create New Project]\(新しいプロジェクトの作成\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="463da-186">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="463da-187">アプリケーションの作成先となるファイル システム上の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="463da-187">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="463da-188">プロジェクトが作成されたら、 **[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="463da-188">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="463da-189">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="463da-189">Run the application:</span></span>

        - <span data-ttu-id="463da-190">**[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="463da-190">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="463da-191">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="463da-191">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="463da-192">複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="463da-192">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="463da-193">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="463da-193">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="463da-194">`dotnet` コマンド ライン ツールを使用した C# での開発</span><span class="sxs-lookup"><span data-stu-id="463da-194">Develop with C#, using the `dotnet` command-line tool</span></span>

<span data-ttu-id="463da-195">もちろん、単に .NET Core SDK と QDK プロジェクト テンプレートをインストールして、コマンド ラインから Q# プログラムを構築して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="463da-195">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="463da-196">前提条件</span><span class="sxs-lookup"><span data-stu-id="463da-196">Pre-requisites</span></span>

    - [<span data-ttu-id="463da-197">.NET Core SDK 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="463da-197">.NET Core SDK 3.0 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="463da-198">.NET 用量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="463da-198">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="463da-199">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="463da-199">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="463da-200">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="463da-200">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="463da-201">新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="463da-201">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="463da-202">新しいアプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="463da-202">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="463da-203">アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="463da-203">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="463da-204">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="463da-204">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="463da-205">`Hello quantum world!` という出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="463da-205">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="463da-206">次の手順</span><span class="sxs-lookup"><span data-stu-id="463da-206">What's next?</span></span>

<span data-ttu-id="463da-207">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="463da-207">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
