---
title: 'IDE で Q# アプリケーションを使用して開発する'
description: 'コマンド プロンプトから実行される Q# アプリケーションを作成する方法について説明します。'
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: a6823888dcbe8cf79f0045d2615fe8b889dcc7c3
ms.sourcegitcommit: a13c7c86fd52a05cbf129b8dd713d6586ca1cc2c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93376424"
---
# <a name="develop-with-no-locq-applications-in-an-ide"></a><span data-ttu-id="8d8c7-103">IDE で Q# アプリケーションを使用して開発する</span><span class="sxs-lookup"><span data-stu-id="8d8c7-103">Develop with Q# applications in an IDE</span></span>

<span data-ttu-id="8d8c7-104">Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-104">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span> <span data-ttu-id="8d8c7-105">Visual Studio Code (VS Code)、Visual Studio、Visual Studio Codespaces、または任意のエディター/IDE で Q# アプリケーションを開発し、.NET コンソールからアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-105">You can develop Q# applications in Visual Studio Code (VS Code), Visual Studio, Visual Studio Codespaces, or with any editor/IDE and run applications from the .NET console.</span></span> 

## <a name="prerequisites-for-all-environments"></a><span data-ttu-id="8d8c7-106">すべての環境の前提条件</span><span class="sxs-lookup"><span data-stu-id="8d8c7-106">Prerequisites for all environments</span></span>

- [<span data-ttu-id="8d8c7-107">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="8d8c7-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="8d8c7-108">インストール</span><span class="sxs-lookup"><span data-stu-id="8d8c7-108">Installation</span></span>

<span data-ttu-id="8d8c7-109">Q# アプリケーションはどの IDE でもビルドできますが、Q# アプリケーションをローカルで開発する場合は Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="8d8c7-110">Web ブラウザーを使用してクラウドで開発する場合は、Visual Studio Codespaces をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="8d8c7-111">これらの環境での開発では、警告、構文の強調表示、プロジェクト テンプレートなど、QDK 拡張機能の豊富な機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-111">Developing in these environments leverages the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

### <a name="to-configure-for-vs-code"></a><span data-ttu-id="8d8c7-112">VS Code 用に構成するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-112">To configure for VS Code:</span></span>

1. <span data-ttu-id="8d8c7-113">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="8d8c7-114">[Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

### <a name="to-configure-for-visual-studio"></a><span data-ttu-id="8d8c7-115">Visual Studio 用に構成するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-115">To configure for Visual Studio:</span></span>

1. <span data-ttu-id="8d8c7-116">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="8d8c7-117">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

### <a name="to-configure-for-another-environment"></a><span data-ttu-id="8d8c7-118">別の環境用に構成するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-118">To configure for another environment:</span></span> 

1. <span data-ttu-id="8d8c7-119">コマンド プロンプトで、次を入力します</span><span class="sxs-lookup"><span data-stu-id="8d8c7-119">Enter the following at the command prompt</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

### <a name="to-configure-for-visual-studio-codespaces"></a><span data-ttu-id="8d8c7-120">Visual Studio Codespaces 用に構成するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-120">To configure for Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="8d8c7-121">[Azure アカウント](https://azure.microsoft.com/free/)を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-121">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="8d8c7-122">Codespaces 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-122">Create a Codespaces environment.</span></span> <span data-ttu-id="8d8c7-123">[クイックスタート ガイド](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-123">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="8d8c7-124">Codespace を作成するときに、[Git リポジトリ] フィールドに「`microsoft/Quantum`」と入力して、QDK 固有の設定を読み込むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-124">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="8d8c7-125">これで、新しい環境を起動し、[VS Codespaces のクラウド IDE](https://online.visualstudio.com/environments) を使用してブラウザーで開発を開始できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-125">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="8d8c7-126">または、VS Code のローカル インストールを使用して、[リモート環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)として Codespaces を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-126">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>

## <a name="develop-with-no-locq"></a><span data-ttu-id="8d8c7-127">Q# を使用した開発</span><span class="sxs-lookup"><span data-stu-id="8d8c7-127">Develop with Q#</span></span>

<span data-ttu-id="8d8c7-128">お使いの開発環境に対応するタブの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-128">Follow the instructions on the tab corresponding to your development environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="8d8c7-129">VS Code</span><span class="sxs-lookup"><span data-stu-id="8d8c7-129">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="8d8c7-130">新しいプロジェクトを作成するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-130">To create a new project:</span></span>

1. <span data-ttu-id="8d8c7-131">**[表示]**  ->  **[コマンド パレット]** をクリックして、 **[Q#: 新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-131">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="8d8c7-132">**[Standalone console application]\(スタンドアロン コンソール アプリケーション\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-132">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="8d8c7-133">プロジェクトを保存する場所に移動して、 **[プロジェクトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-133">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="8d8c7-134">プロジェクトが正常に作成されたら、右下にある **[Open new project...]\(新しいプロジェクトを開く...\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-134">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="8d8c7-135">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-135">Inspect the project.</span></span> <span data-ttu-id="8d8c7-136">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-136">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="8d8c7-137">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-137">To run the application:</span></span>

1. <span data-ttu-id="8d8c7-138">**[ターミナル]**  ->  **[新しいターミナル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-138">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="8d8c7-139">ターミナル プロンプトで、`dotnet run` と入力します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-139">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="8d8c7-140">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-140">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="8d8c7-141">複数のルート フォルダーを持つワークスペースは、VS Code の Q# 拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-141">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="8d8c7-142">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-142">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="8d8c7-143">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8d8c7-143">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="8d8c7-144">Q# の `Hello World` アプリケーションを作成して、Visual Studio のインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-144">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="8d8c7-145">新しい Q# アプリケーションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-145">To create a new Q# application:</span></span>

1. <span data-ttu-id="8d8c7-146">Visual Studio を開き、 **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-146">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="8d8c7-147">検索ボックスに「`Q#`」と入力し、 **[Q# アプリケーション]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-147">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="8d8c7-148">アプリケーションの名前と場所を入力して、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-148">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="8d8c7-149">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-149">Inspect the project.</span></span> <span data-ttu-id="8d8c7-150">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-150">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="8d8c7-151">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="8d8c7-151">To run the application:</span></span>

1. <span data-ttu-id="8d8c7-152">**[デバッグ]**  ->  **[デバッグなしで開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-152">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="8d8c7-153">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-153">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="8d8c7-154">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-154">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="8d8c7-155">コマンド プロンプトを使用した他のエディター</span><span class="sxs-lookup"><span data-stu-id="8d8c7-155">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="8d8c7-156">Q# の `Hello World` アプリケーションを作成して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-156">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="8d8c7-157">新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="8d8c7-158">アプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="8d8c7-159">このディレクトリには `Program.qs` という名前のファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="8d8c7-160">このテンプレートをテキスト エディターで変更し、独自のクォンタム アプリケーションで上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="8d8c7-161">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="8d8c7-162">次のように表示されます。`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="8d8c7-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="8d8c7-163">次のステップ</span><span class="sxs-lookup"><span data-stu-id="8d8c7-163">Next steps</span></span>

<span data-ttu-id="8d8c7-164">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8d8c7-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
