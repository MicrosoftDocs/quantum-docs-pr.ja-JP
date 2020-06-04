---
title: 'Quantum Development Kit (QDK) を使用して Q # プロジェクトを作成する方法について説明します。'
description: '選択した開発環境の QDK と Q # を使用して、quantum 開発用のプロジェクトを初期化します'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8019b32a3290e2d45124ebb1eb75395f6cb758db
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327528"
---
# <a name="create-a-q-project-in-your-development-environment"></a><span data-ttu-id="20cf0-103">開発環境で Q # プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="20cf0-103">Create a Q# project in your development environment</span></span>

<span data-ttu-id="20cf0-104">QDK で Q # プロジェクトを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-104">Learn how to create a Q# project with the QDK.</span></span>

<span data-ttu-id="20cf0-105">Q # プロジェクトには、クォンタムコードを含む Q # ファイルと、クォンタムプログラムを実行するホストプログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="20cf0-105">A Q# project contains Q# files containing quantum code, as well as a host program to run the quantum program.</span></span> <span data-ttu-id="20cf0-106">ホストプログラムは、C# などの .NET 言語、または Python で記述できます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-106">You can write the host program in .NET languages such as C#, or in Python.</span></span> <span data-ttu-id="20cf0-107">また、IQ # kernel を使用して Jupyter Notebook で Q # コードを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-107">You can also run Q# code in a Jupyter Notebook using the IQ# kernel.</span></span>

<span data-ttu-id="20cf0-108">以下のセクションで、開発環境と言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-108">Choose your development environment and language from the sections below:</span></span>

* [<span data-ttu-id="20cf0-109">Python</span><span class="sxs-lookup"><span data-stu-id="20cf0-109">Python</span></span>](#create-a-python-project)
* [<span data-ttu-id="20cf0-110">Q# Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="20cf0-110">Q# Jupyter Notebooks</span></span>](#create-a-q-jupyter-notebook-project)
* [<span data-ttu-id="20cf0-111">Visual Studio を使用した C#</span><span class="sxs-lookup"><span data-stu-id="20cf0-111">C# with Visual Studio</span></span>](#create-a-c-project-on-windows-using-visual-studio)
* [<span data-ttu-id="20cf0-112">VS Code を使用した C#</span><span class="sxs-lookup"><span data-stu-id="20cf0-112">C# with VS Code</span></span>](#create-a-c-project-using-vs-code)
* [<span data-ttu-id="20cf0-113">コマンドラインを使用した C#</span><span class="sxs-lookup"><span data-stu-id="20cf0-113">C# with the command line</span></span>](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a><span data-ttu-id="20cf0-114">Python プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="20cf0-114">Create a Python project</span></span>

1. <span data-ttu-id="20cf0-115">前提条件</span><span class="sxs-lookup"><span data-stu-id="20cf0-115">Pre-requisites</span></span>

     * <span data-ttu-id="20cf0-116">[Python 用 Quantum 開発キット](xref:microsoft.quantum.install.python)をインストールする</span><span class="sxs-lookup"><span data-stu-id="20cf0-116">Install the [Quantum Development Kit for Python](xref:microsoft.quantum.install.python)</span></span>

1. <span data-ttu-id="20cf0-117">プロジェクトのフォルダーを作成し、そのフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-117">Create a folder for your project, and navigate to that folder</span></span>

1. <span data-ttu-id="20cf0-118">という名前の Q # ファイルを作成 `Operation.qs` し、そのファイルに q # コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-118">Create a Q# file called `Operation.qs`, and add your Q# code to it.</span></span> <span data-ttu-id="20cf0-119">例:</span><span class="sxs-lookup"><span data-stu-id="20cf0-119">For example:</span></span>

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. <span data-ttu-id="20cf0-120">という名前の python ホストファイルを作成し、 `host.py` Q # 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-120">Create a python host file called `host.py` to call your Q# operation.</span></span> <span data-ttu-id="20cf0-121">例:</span><span class="sxs-lookup"><span data-stu-id="20cf0-121">For example:</span></span>

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. <span data-ttu-id="20cf0-122">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-122">Run the program:</span></span>

    ```bash
    python host.py
    ```

1. <span data-ttu-id="20cf0-123">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-123">Verify the output.</span></span> <span data-ttu-id="20cf0-124">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-124">Your program should output the following lines:</span></span>

    ```bash
    Hello from quantum world!
    0
    ```

<span data-ttu-id="20cf0-125">これで、quantum プログラムの開発を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-125">You can now continue to develop your quantum program.</span></span>

## <a name="create-a-q-jupyter-notebook-project"></a><span data-ttu-id="20cf0-126">Q # Jupyter Notebook プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="20cf0-126">Create a Q# Jupyter Notebook project</span></span>

1. <span data-ttu-id="20cf0-127">前提条件</span><span class="sxs-lookup"><span data-stu-id="20cf0-127">Pre-requisites</span></span>

    * <span data-ttu-id="20cf0-128">[Jupyter notebook 用の Quantum 開発キットを](xref:microsoft.quantum.install.jupyter)インストールする</span><span class="sxs-lookup"><span data-stu-id="20cf0-128">Install the [Quantum Development Kit for Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)</span></span>

1. <span data-ttu-id="20cf0-129">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-129">Run the following command to start the notebook server:</span></span>

    ```bash
    jupyter notebook
    ```

1. <span data-ttu-id="20cf0-130">コマンド ラインに表示されている URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-130">Browse to the URL shown on the command line.</span></span> <span data-ttu-id="20cf0-131">例: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span><span class="sxs-lookup"><span data-stu-id="20cf0-131">For example: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]</span></span>

1. <span data-ttu-id="20cf0-132">Jupyter ページがブラウザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-132">A Jupyter page appears in the browser.</span></span> <span data-ttu-id="20cf0-133">[**ファイル**] タブで [**新しい**q #] を選択し、  >  **Q#** q # カーネルを使用して Jupyter Notebook を作成します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-133">On the **Files** tab, select **New** > **Q#** to create a Jupyter Notebook with a Q# kernel.</span></span> <span data-ttu-id="20cf0-134">最初の notebook セルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-134">Add the following code to the first notebook cell:</span></span>

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. <span data-ttu-id="20cf0-135">[**セル**の実行] [セル] を選択し  >  **Run Cells**て、notebook を実行します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-135">Select **Cell** > **Run Cells** to run the notebook.</span></span> <span data-ttu-id="20cf0-136">`SayHello`は、すぐにセルの出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-136">`SayHello` will soon appear in the cell output:</span></span>

    ![Q # コードを含むセルを Jupyter Notebook](~/media/install-guide-jupyter.png)

    <span data-ttu-id="20cf0-138">Jupyter Notebook で実行すると、Q # コードがコンパイルされ、ノートブックは検出した操作の名前を出力します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-138">When running in Jupyter Notebooks, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>

1. <span data-ttu-id="20cf0-139">新しいセルで、`%simulate` マジックを使用して、作成した演算の量子コンピューターでの実行をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="20cf0-139">In a new cell, simulate the execution in a quantum computer of the operation you just created by using the `%simulate` magic:</span></span>

    ![% シミュレートマジックを含むセルを Jupyter Notebook](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="20cf0-141">呼び出した演算の結果 (この場合は空) と共に、メッセージが画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-141">You should see the message printed on the screen along with the result of the operation you invoked (in this case, empty).</span></span>

<span data-ttu-id="20cf0-142">他の Q # 操作を追加して、量子開発を続けることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="20cf0-142">You can now add other Q# operations to continue your quantum development.</span></span>

## <a name="create-a-c-project-on-windows-using-visual-studio"></a><span data-ttu-id="20cf0-143">Visual Studio を使用した Windows での C# プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="20cf0-143">Create a C# project on Windows, using Visual Studio</span></span>

1. <span data-ttu-id="20cf0-144">前提条件</span><span class="sxs-lookup"><span data-stu-id="20cf0-144">Pre-requisites</span></span>

    * <span data-ttu-id="20cf0-145">[Visual Studio 用の Quantum Development Kit 拡張機能](xref:microsoft.quantum.install.cs)をインストールする</span><span class="sxs-lookup"><span data-stu-id="20cf0-145">Install the [Quantum Development Kit extension for Visual Studio](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="20cf0-146">新しい Q# アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="20cf0-146">Create a new Q# application</span></span>

    * <span data-ttu-id="20cf0-147">ファイルの**File**  ->  **新しい**  ->  **プロジェクト**にアクセス</span><span class="sxs-lookup"><span data-stu-id="20cf0-147">Go to **File** -> **New** -> **Project**</span></span>
    * <span data-ttu-id="20cf0-148">検索ボックスに、「`Q#`」と入力します</span><span class="sxs-lookup"><span data-stu-id="20cf0-148">Type `Q#` in the search box</span></span>
    * <span data-ttu-id="20cf0-149">**[Q# Application]\(Q# アプリケーション\)** を選択します</span><span class="sxs-lookup"><span data-stu-id="20cf0-149">Select **Q# Application**</span></span>
    * <span data-ttu-id="20cf0-150">**[次へ]** を選択します</span><span class="sxs-lookup"><span data-stu-id="20cf0-150">Select **Next**</span></span>
    * <span data-ttu-id="20cf0-151">アプリケーションの名前と格納する場所を選択します</span><span class="sxs-lookup"><span data-stu-id="20cf0-151">Choose a name and location for your application</span></span>
    * <span data-ttu-id="20cf0-152">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="20cf0-152">Select **Create**</span></span>

1. <span data-ttu-id="20cf0-153">プロジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="20cf0-153">Inspect the project</span></span>

    <span data-ttu-id="20cf0-154">2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="20cf0-154">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

1. <span data-ttu-id="20cf0-155">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="20cf0-155">Run the application</span></span>

    * <span data-ttu-id="20cf0-156">デバッグ**Debug**を  ->  **行わないデバッグ開始**の選択</span><span class="sxs-lookup"><span data-stu-id="20cf0-156">Select **Debug** -> **Start Without Debugging**</span></span>
    * <span data-ttu-id="20cf0-157">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-157">You should see the text `Hello quantum world!` printed to a console window.</span></span>

<span data-ttu-id="20cf0-158">Visual Studio を使用して、量子開発を続けることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="20cf0-158">You can now continue your quantum development using Visual Studio</span></span>

> [!NOTE]
> * <span data-ttu-id="20cf0-159">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20cf0-159">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <a name="create-a-c-project-using-vs-code"></a><span data-ttu-id="20cf0-160">VS Code を使用して C# プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="20cf0-160">Create a C# project, using VS Code</span></span>

1. <span data-ttu-id="20cf0-161">前提条件</span><span class="sxs-lookup"><span data-stu-id="20cf0-161">Pre-requisites</span></span>

    * <span data-ttu-id="20cf0-162">[VS Code 用の Quantum Development Kit 拡張機能](xref:microsoft.quantum.install.cs)をインストールする</span><span class="sxs-lookup"><span data-stu-id="20cf0-162">Install the [Quantum Development Kit extension for VS Code](xref:microsoft.quantum.install.cs)</span></span>

1. <span data-ttu-id="20cf0-163">新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-163">Create a new project:</span></span>

    * <span data-ttu-id="20cf0-164">**ビュー**  ->  **コマンドパレット**にアクセス</span><span class="sxs-lookup"><span data-stu-id="20cf0-164">Go to **View** -> **Command Palette**</span></span>
    * <span data-ttu-id="20cf0-165">[ **Q #: 新しいプロジェクトの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-165">Select **Q#: Create New Project**</span></span>
    * <span data-ttu-id="20cf0-166">**スタンドアロンコンソールアプリケーション**の選択</span><span class="sxs-lookup"><span data-stu-id="20cf0-166">Select **Standalone console application**</span></span>
    * <span data-ttu-id="20cf0-167">アプリケーションの作成先となるファイル システム上の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-167">Navigate to the location on the file system where you would like to create the application</span></span>
    * <span data-ttu-id="20cf0-168">プロジェクトが作成されたら、**[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="20cf0-168">Click on the **Open new project...** button, once the project has been created</span></span>

1. <span data-ttu-id="20cf0-169">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-169">Run the application:</span></span>

    * <span data-ttu-id="20cf0-170">ターミナルの**Terminal**  ->  **新しいターミナル**にアクセス</span><span class="sxs-lookup"><span data-stu-id="20cf0-170">Go to **Terminal** -> **New Terminal**</span></span>
    * <span data-ttu-id="20cf0-171">「`dotnet run`」と入力します</span><span class="sxs-lookup"><span data-stu-id="20cf0-171">Enter `dotnet run`</span></span>
    * <span data-ttu-id="20cf0-172">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-172">You should see the following text in the output window `Hello quantum world!`</span></span>

<span data-ttu-id="20cf0-173">Visual Studio Code を使用して、quantum の開発を続けることができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="20cf0-173">You can now continue your quantum development using Visual Studio Code.</span></span>

> [!NOTE]
> * <span data-ttu-id="20cf0-174">複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="20cf0-174">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="20cf0-175">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20cf0-175">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a><span data-ttu-id="20cf0-176">コマンドラインツールを使用して C# プロジェクトを作成する `dotnet`</span><span class="sxs-lookup"><span data-stu-id="20cf0-176">Create a C# project, using the `dotnet` command-line tool</span></span>

1. <span data-ttu-id="20cf0-177">前提条件</span><span class="sxs-lookup"><span data-stu-id="20cf0-177">Pre-requisites</span></span>

    * <span data-ttu-id="20cf0-178">[コマンドライン用の Quantum 開発キット](xref:microsoft.quantum.install.standalone)をインストールする</span><span class="sxs-lookup"><span data-stu-id="20cf0-178">Install the [Quantum Development Kit for the command line](xref:microsoft.quantum.install.standalone)</span></span>

1. <span data-ttu-id="20cf0-179">新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="20cf0-179">Create a new application</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. <span data-ttu-id="20cf0-180">新しいアプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="20cf0-180">Navigate to the new application directory</span></span>

    ```bash
    cd <project name>
    ```

    <span data-ttu-id="20cf0-181">アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="20cf0-181">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

1. <span data-ttu-id="20cf0-182">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="20cf0-182">Run the application</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="20cf0-183">`Hello quantum world!` という出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-183">You should see the following output: `Hello quantum world!`</span></span>

<span data-ttu-id="20cf0-184">これで、コマンドラインツールを使用して、クォンタム開発を続行できます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-184">You now continue your quantum development, using command line tools.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20cf0-185">次の手順</span><span class="sxs-lookup"><span data-stu-id="20cf0-185">Next steps</span></span>

<span data-ttu-id="20cf0-186">お好みの環境でプロジェクトを作成したので、量子開発を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="20cf0-186">Now that you have created a project in your preferred environment, you can continue your quantum development.</span></span>
