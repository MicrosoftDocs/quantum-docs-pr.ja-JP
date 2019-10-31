---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 3ec53934436b47908fd4d794a98933010f6059a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035309"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ca144-102">Microsoft Quantum Development Kit (QDK) のインストール</span><span class="sxs-lookup"><span data-stu-id="ca144-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ca144-103">Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="ca144-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="ca144-104">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-104">The QDK consists of:</span></span>

- <span data-ttu-id="ca144-105">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="ca144-105">the Q# programming language</span></span>
- <span data-ttu-id="ca144-106">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="ca144-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="ca144-107">Q# で記述された量子操作を実行するホスト アプリケーション (Python または .NET 言語で記述)</span><span class="sxs-lookup"><span data-stu-id="ca144-107">a host application (written in Python or a .NET language) that runs quantum operations written in Q#</span></span>
- <span data-ttu-id="ca144-108">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="ca144-108">tools to facilitate your development</span></span>

<span data-ttu-id="ca144-109">選択した開発環境に応じて、さまざまなインストール手順があります。</span><span class="sxs-lookup"><span data-stu-id="ca144-109">Depending on your chosen development environment, there are different installation steps.</span></span> <span data-ttu-id="ca144-110">以下のセクションから環境を選択してください。</span><span class="sxs-lookup"><span data-stu-id="ca144-110">Choose your environment from the sections below.</span></span>

## <a name="develop-with-python"></a><span data-ttu-id="ca144-111">Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="ca144-111">Develop with Python</span></span>

1. <span data-ttu-id="ca144-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="ca144-112">Pre-requisites</span></span>

    - <span data-ttu-id="ca144-113">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="ca144-113">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="ca144-114">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="ca144-114">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="ca144-115">.NET Core SDK 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="ca144-115">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ca144-116">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="ca144-116">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ca144-117">`qsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="ca144-117">Install the `qsharp` package</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="ca144-118">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="ca144-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ca144-119">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="ca144-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

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

    - <span data-ttu-id="ca144-120">Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca144-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="ca144-121">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca144-121">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="ca144-122">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="ca144-122">Verify the output.</span></span> <span data-ttu-id="ca144-123">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-123">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a><span data-ttu-id="ca144-124">Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="ca144-124">Develop with Jupyter notebooks</span></span>

1. <span data-ttu-id="ca144-125">前提条件</span><span class="sxs-lookup"><span data-stu-id="ca144-125">Pre-requisites</span></span>

    - <span data-ttu-id="ca144-126">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="ca144-126">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="ca144-127">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ca144-127">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="ca144-128">.NET Core SDK 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="ca144-128">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ca144-129">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="ca144-129">Install the `iqsharp` package</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="ca144-130">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="ca144-130">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ca144-131">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="ca144-131">Run the following command to start the notebook server:</span></span>

        ```bash
        jupyter notebook
        ```

    - <span data-ttu-id="ca144-132">コマンド ラインに表示されている URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="ca144-132">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="ca144-133">例: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]</span><span class="sxs-lookup"><span data-stu-id="ca144-133">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

    - <span data-ttu-id="ca144-134">Q# カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ca144-134">Create a Jupyter notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="ca144-135">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca144-135">Run this cell of the notebook:</span></span>

        ![Jupyter Notebook のセル](~/media/install-guide-jupyter.png)

        <span data-ttu-id="ca144-137">セルの出力に `SayHello` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-137">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="ca144-138">Jupyter Notebook で実行すると、Q# コードがコンパイルされ、ノートブックから検出した操作の名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-138">When running in jupyter notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

## <a name="develop-with-c-on-windows-using-visual-studio"></a><span data-ttu-id="ca144-139">Visual Studio を使用した Windows での C# の開発</span><span class="sxs-lookup"><span data-stu-id="ca144-139">Develop with C# on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="ca144-140">前提条件</span><span class="sxs-lookup"><span data-stu-id="ca144-140">Pre-requisites</span></span>

    - <span data-ttu-id="ca144-141">.NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="ca144-141">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="ca144-142">Q# Visual Studio 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="ca144-142">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="ca144-143">[Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ca144-143">Download the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>
    - <span data-ttu-id="ca144-144">拡張機能を Visual Studio に追加する</span><span class="sxs-lookup"><span data-stu-id="ca144-144">Add the extension to Visual Studio</span></span>

1. <span data-ttu-id="ca144-145">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="ca144-145">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ca144-146">新しい Q# アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="ca144-146">Create a new Q# application</span></span>

        - <span data-ttu-id="ca144-147">**[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="ca144-147">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="ca144-148">検索ボックスに、「`Q#`」と入力します</span><span class="sxs-lookup"><span data-stu-id="ca144-148">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="ca144-149">**[Q# Application]\(Q# アプリケーション\)** を選択します</span><span class="sxs-lookup"><span data-stu-id="ca144-149">Select **Q# Application**</span></span>
        - <span data-ttu-id="ca144-150">**[次へ]** を選択します</span><span class="sxs-lookup"><span data-stu-id="ca144-150">Select **Next**</span></span>
        - <span data-ttu-id="ca144-151">アプリケーションの名前と格納する場所を選択します</span><span class="sxs-lookup"><span data-stu-id="ca144-151">Choose a name and location for your application</span></span>
        - <span data-ttu-id="ca144-152">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="ca144-152">Select **Create**</span></span>

    - <span data-ttu-id="ca144-153">プロジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="ca144-153">Inspect the project</span></span>

        <span data-ttu-id="ca144-154">2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="ca144-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="ca144-155">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="ca144-155">Run the application</span></span>

        - <span data-ttu-id="ca144-156">**[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca144-156">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="ca144-157">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="ca144-158">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca144-158">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="develop-with-c-using-vs-code"></a><span data-ttu-id="ca144-159">VS Code を使用した C# での開発</span><span class="sxs-lookup"><span data-stu-id="ca144-159">Develop with C#, using VS Code</span></span>

1. <span data-ttu-id="ca144-160">前提条件</span><span class="sxs-lookup"><span data-stu-id="ca144-160">Pre-requisites</span></span>

   - [<span data-ttu-id="ca144-161">VS Code</span><span class="sxs-lookup"><span data-stu-id="ca144-161">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="ca144-162">.NET Core SDK 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="ca144-162">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ca144-163">Quantum VS Code 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="ca144-163">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="ca144-164">[VS Code 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールする</span><span class="sxs-lookup"><span data-stu-id="ca144-164">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="ca144-165">量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ca144-165">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="ca144-166">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca144-166">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="ca144-167">**[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca144-167">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="ca144-168">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ca144-168">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ca144-169">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="ca144-169">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ca144-170">新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca144-170">Create a new project:</span></span>

        - <span data-ttu-id="ca144-171">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca144-171">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="ca144-172">**[Q#:Create New Project]\(新しいプロジェクトの作成\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca144-172">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="ca144-173">アプリケーションの作成先となるファイル システム上の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="ca144-173">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="ca144-174">プロジェクトが作成されたら、 **[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ca144-174">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="ca144-175">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ca144-175">Run the application:</span></span>

        - <span data-ttu-id="ca144-176">**[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="ca144-176">Go to **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="ca144-177">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-177">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> * > * <span data-ttu-id="ca144-178">複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ca144-178">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="ca144-179">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca144-179">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a><span data-ttu-id="ca144-180">`dotnet` コマンド ライン ツールを使用した C# での開発</span><span class="sxs-lookup"><span data-stu-id="ca144-180">Develop with C#, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="ca144-181">前提条件</span><span class="sxs-lookup"><span data-stu-id="ca144-181">Pre-requisites</span></span>

    - [<span data-ttu-id="ca144-182">.NET Core SDK 2.1 以降</span><span class="sxs-lookup"><span data-stu-id="ca144-182">.NET Core SDK 2.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="ca144-183">.NET 用量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ca144-183">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="ca144-184">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ca144-184">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="ca144-185">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="ca144-185">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="ca144-186">新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="ca144-186">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="ca144-187">新しいアプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="ca144-187">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="ca144-188">アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="ca144-188">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="ca144-189">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="ca144-189">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="ca144-190">`Hello quantum world!` という出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ca144-190">You should see the following output: `Hello quantum world!`</span></span>

## <a name="whats-next"></a><span data-ttu-id="ca144-191">次の手順</span><span class="sxs-lookup"><span data-stu-id="ca144-191">What's next?</span></span>

<span data-ttu-id="ca144-192">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ca144-192">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
