---
title: 'Q # + を使用した開発C#'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 1fd829c684502092bb7491b0f46b5f690320c941
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831020"
---
# <a name="develop-with-q--c"></a><span data-ttu-id="d69f9-102">Q # + を使用した開発C#</span><span class="sxs-lookup"><span data-stu-id="d69f9-102">Develop with Q# + C#</span></span>

<span data-ttu-id="d69f9-103">Q # 操作を呼び出すホストC#プログラムを開発するには、qdk をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d69f9-103">Install the QDK to develop C# host programs to call Q# operations.</span></span>

<span data-ttu-id="d69f9-104">Q # は、.NET 言語 (特C#に) を使用して適切に動作するように構築されています。</span><span class="sxs-lookup"><span data-stu-id="d69f9-104">Q# is built to play well with .NET languages--specifically C#.</span></span> <span data-ttu-id="d69f9-105">この組み合わせは、さまざまな開発環境で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-105">You can work with this pairing inside different development environments:</span></span>

- [<span data-ttu-id="d69f9-106">Visual Studio をC#使用した Q # + (Windows)</span><span class="sxs-lookup"><span data-stu-id="d69f9-106">Q# + C# using Visual Studio (Windows)</span></span>](#VS)
- [<span data-ttu-id="d69f9-107">Visual Studio Code を使用C#した Q # + (Windows、Linux、Mac)</span><span class="sxs-lookup"><span data-stu-id="d69f9-107">Q# + C# using Visual Studio Code (Windows, Linux and Mac)</span></span>](#VSC)
- [<span data-ttu-id="d69f9-108">Q # + C# `dotnet` コマンドラインツールの使用</span><span class="sxs-lookup"><span data-stu-id="d69f9-108">Q# + C# using the `dotnet` command-line tool</span></span>](#command)

## <span data-ttu-id="d69f9-109">Visual Studio を使用しC#た Q # + を使用した開発<a name="VS"></a></span><span class="sxs-lookup"><span data-stu-id="d69f9-109">Develop with Q# + C# using Visual Studio <a name="VS"></a></span></span>

<span data-ttu-id="d69f9-110">Visual Studio には、Q # プログラムを開発するための豊富な環境が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d69f9-110">Visual Studio offers a rich environment for developing Q# programs.</span></span> <span data-ttu-id="d69f9-111">Q # Visual Studio 拡張機能には、Q # のファイルとプロジェクトのテンプレートに加え、構文の強調表示、コード補完、IntelliSense のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d69f9-111">The Q# Visual Studio extension contains templates for Q# files and projects as well as syntax highlighting, code completion and IntelliSense support.</span></span>


1. <span data-ttu-id="d69f9-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="d69f9-112">Pre-requisites</span></span>

    - <span data-ttu-id="d69f9-113">.NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="d69f9-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>

1. <span data-ttu-id="d69f9-114">Q# Visual Studio 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="d69f9-114">Install the Q# Visual Studio extension</span></span>

    - <span data-ttu-id="d69f9-115">[Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="d69f9-115">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>

1. <span data-ttu-id="d69f9-116">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="d69f9-116">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="d69f9-117">新しい Q# アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="d69f9-117">Create a new Q# application</span></span>

        - <span data-ttu-id="d69f9-118">**[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-118">Go to **File** -> **New** -> **Project**</span></span>
        - <span data-ttu-id="d69f9-119">検索ボックスに、「`Q#`」と入力します</span><span class="sxs-lookup"><span data-stu-id="d69f9-119">Type `Q#` in the search box</span></span>
        - <span data-ttu-id="d69f9-120">**[Q# Application]\(Q# アプリケーション\)** を選択します</span><span class="sxs-lookup"><span data-stu-id="d69f9-120">Select **Q# Application**</span></span>
        - <span data-ttu-id="d69f9-121">**[次へ]** を選択します</span><span class="sxs-lookup"><span data-stu-id="d69f9-121">Select **Next**</span></span>
        - <span data-ttu-id="d69f9-122">アプリケーションの名前と格納する場所を選択します</span><span class="sxs-lookup"><span data-stu-id="d69f9-122">Choose a name and location for your application</span></span>
        - <span data-ttu-id="d69f9-123">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="d69f9-123">Select **Create**</span></span>

    - <span data-ttu-id="d69f9-124">プロジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="d69f9-124">Inspect the project</span></span>

        <span data-ttu-id="d69f9-125">2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="d69f9-125">You should see that two files have been created: `Driver.cs`, which is the C# host application; and `Operation.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

    - <span data-ttu-id="d69f9-126">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="d69f9-126">Run the application</span></span>

        - <span data-ttu-id="d69f9-127">**[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-127">Select **Debug** -> **Start Without Debugging**</span></span>
        - <span data-ttu-id="d69f9-128">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-128">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="d69f9-129">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69f9-129">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  

## <span data-ttu-id="d69f9-130">Visual Studio Code を使用したC# Q # + を使用した開発<a name="VSC"></a></span><span class="sxs-lookup"><span data-stu-id="d69f9-130">Develop with Q# + C# using Visual Studio Code <a name="VSC"></a></span></span>

<span data-ttu-id="d69f9-131">Visual Studio Code (VS Code) は、Windows、Linux、および Mac で Q # プログラムを開発するための豊富な環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-131">Visual Studio Code (VS Code) offers a rich environment for developing Q# programs on Windows, Linux and Mac.</span></span>  <span data-ttu-id="d69f9-132">Q # の VS Code 拡張機能には、Q # 構文の強調表示、コード補完、Q # コードスニペットのサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d69f9-132">The Q# VS Code extension includes support for Q# syntax highlighting, code completion, and Q# code snippets.</span></span>

1. <span data-ttu-id="d69f9-133">前提条件</span><span class="sxs-lookup"><span data-stu-id="d69f9-133">Pre-requisites</span></span>

   - [<span data-ttu-id="d69f9-134">VS Code</span><span class="sxs-lookup"><span data-stu-id="d69f9-134">VS Code</span></span>](https://code.visualstudio.com/download)
   - [<span data-ttu-id="d69f9-135">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="d69f9-135">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="d69f9-136">Quantum VS Code 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="d69f9-136">Install the Quantum VS Code extension</span></span>

    - <span data-ttu-id="d69f9-137">[VS Code 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールする</span><span class="sxs-lookup"><span data-stu-id="d69f9-137">Install the [VS Code extension](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)</span></span>

1. <span data-ttu-id="d69f9-138">量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d69f9-138">Install the Quantum project templates:</span></span>

   - <span data-ttu-id="d69f9-139">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-139">Go to **View** -> **Command Palette**</span></span>
   - <span data-ttu-id="d69f9-140">**[Q #: プロジェクトテンプレートのインストール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-140">Select **Q#: Install project templates**</span></span>

    <span data-ttu-id="d69f9-141">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d69f9-141">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="d69f9-142">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="d69f9-142">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="d69f9-143">新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-143">Create a new project:</span></span>

        - <span data-ttu-id="d69f9-144">**[表示]**  ->  **[コマンド パレット]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-144">Go to **View** -> **Command Palette**</span></span>
        - <span data-ttu-id="d69f9-145">**[Q #: 新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-145">Select **Q#: Create New Project**</span></span>
        - <span data-ttu-id="d69f9-146">**スタンドアロンコンソールアプリケーション**の選択</span><span class="sxs-lookup"><span data-stu-id="d69f9-146">Select **Standalone console application**</span></span>
        - <span data-ttu-id="d69f9-147">アプリケーションの作成先となるファイル システム上の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-147">Navigate to the location on the file system where you would like to create the application</span></span>
        - <span data-ttu-id="d69f9-148">プロジェクトが作成されたら、 **[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d69f9-148">Click on the **Open new project...** button, once the project has been created</span></span>

    - <span data-ttu-id="d69f9-149">VS Code のC#拡張機能をまだインストールしていない場合は、ポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-149">If you don't already have the C# extension for VS Code installed, a pop-up will appear.</span></span> <span data-ttu-id="d69f9-150">拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d69f9-150">Install the extension.</span></span> 

    - <span data-ttu-id="d69f9-151">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-151">Run the application:</span></span>

        - <span data-ttu-id="d69f9-152">**ターミナル** -> **新しいターミナル**にアクセスする</span><span class="sxs-lookup"><span data-stu-id="d69f9-152">Go to **Terminal** -> **New Terminal**</span></span>
        - <span data-ttu-id="d69f9-153">「`dotnet run`」と入力します</span><span class="sxs-lookup"><span data-stu-id="d69f9-153">Enter `dotnet run`</span></span>
        - <span data-ttu-id="d69f9-154">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-154">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="d69f9-155">複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d69f9-155">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="d69f9-156">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d69f9-156">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <span data-ttu-id="d69f9-157">`dotnet` コマンドラインツールをC#使用した Q # + を使用した開発<a name="command"></a></span><span class="sxs-lookup"><span data-stu-id="d69f9-157">Develop with Q# + C# using the `dotnet` command-line tool <a name="command"></a></span></span>

<span data-ttu-id="d69f9-158">もちろん、単に .NET Core SDK と QDK プロジェクト テンプレートをインストールして、コマンド ラインから Q# プログラムを構築して実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-158">Of course, you can also build and run Q# programs from the command line by simply installing the .NET Core SDK and the QDK project templates.</span></span> 

1. <span data-ttu-id="d69f9-159">前提条件</span><span class="sxs-lookup"><span data-stu-id="d69f9-159">Pre-requisites</span></span>

    - [<span data-ttu-id="d69f9-160">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="d69f9-160">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

1. <span data-ttu-id="d69f9-161">.NET 用量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d69f9-161">Install the Quantum project templates for .NET</span></span>

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    <span data-ttu-id="d69f9-162">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d69f9-162">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>

1. <span data-ttu-id="d69f9-163">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="d69f9-163">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="d69f9-164">新しいアプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="d69f9-164">Create a new application</span></span>

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - <span data-ttu-id="d69f9-165">新しいアプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d69f9-165">Navigate to the new application directory</span></span>

       ```bash
       cd runSayHello
       ```

    <span data-ttu-id="d69f9-166">アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="d69f9-166">You should see that two files have been created, along with the project files of the application: a Q# file (`Operation.qs`) and a C# host file (`Driver.cs`).</span></span>

    - <span data-ttu-id="d69f9-167">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="d69f9-167">Run the application</span></span>

        ```bash
        dotnet run
        ```

        <span data-ttu-id="d69f9-168">`Hello quantum world!` という出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-168">You should see the following output: `Hello quantum world!`</span></span>

    
## <a name="whats-next"></a><span data-ttu-id="d69f9-169">次に、</span><span class="sxs-lookup"><span data-stu-id="d69f9-169">What's next?</span></span>

<span data-ttu-id="d69f9-170">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d69f9-170">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
