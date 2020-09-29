---
title: Q# アプリケーションを使用した開発
description: コマンド プロンプトから実行される Q# アプリケーションを作成する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
no-loc:
- Q#
- $$v
ms.openlocfilehash: 68f530d80e5c5f40dc2bcbb185879c3cb6f93f91
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834416"
---
# <a name="develop-with-no-locq-applications"></a><span data-ttu-id="d854c-103">Q# アプリケーションを使用した開発</span><span class="sxs-lookup"><span data-stu-id="d854c-103">Develop with Q# applications</span></span>

<span data-ttu-id="d854c-104">お使いの環境に対応するタブの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d854c-104">Follow the instructions at the tab corresponding to your environment.</span></span>

<span data-ttu-id="d854c-105">Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d854c-105">Q# programs can run on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d854c-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="d854c-106">Prerequisites</span></span>

- [<span data-ttu-id="d854c-107">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="d854c-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="d854c-108">インストール</span><span class="sxs-lookup"><span data-stu-id="d854c-108">Installation</span></span>

<span data-ttu-id="d854c-109">Q# アプリケーションはどの IDE でもビルドできますが、Q# アプリケーションをローカルで開発する場合は Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d854c-109">While you can build Q# applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for developing your Q# applications locally.</span></span> <span data-ttu-id="d854c-110">Web ブラウザーを使用してクラウドで開発する場合は、Visual Studio Codespaces をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d854c-110">For developing in the Cloud via the web browser, we recommend Visual Studio Codespaces.</span></span> <span data-ttu-id="d854c-111">これらの環境での開発には、警告、構文の強調表示、プロジェクト テンプレートなど、QDK 拡張機能の豊富な機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="d854c-111">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span> 

<span data-ttu-id="d854c-112">VS Code を構成するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-112">To configure VS Code:</span></span>

1. <span data-ttu-id="d854c-113">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="d854c-113">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="d854c-114">[Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d854c-114">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="d854c-115">Visual Studio を構成するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-115">To configure Visual Studio:</span></span>

1. <span data-ttu-id="d854c-116">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d854c-116">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="d854c-117">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="d854c-117">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="d854c-118">Visual Studio Codespaces を構成するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-118">To configure Visual Studio Codespaces:</span></span>

1. <span data-ttu-id="d854c-119">[Azure アカウント](https://azure.microsoft.com/free/)を作成します。</span><span class="sxs-lookup"><span data-stu-id="d854c-119">Create an [Azure account](https://azure.microsoft.com/free/).</span></span>
2. <span data-ttu-id="d854c-120">Codespaces 環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="d854c-120">Create a Codespaces environment.</span></span> <span data-ttu-id="d854c-121">[クイックスタート ガイド](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser)に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d854c-121">Please follow the [quickstart guide](https://docs.microsoft.com/visualstudio/codespaces/quickstarts/browser).</span></span> <span data-ttu-id="d854c-122">Codespace を作成するときに、[Git リポジトリ] フィールドに「`microsoft/Quantum`」と入力して、QDK 固有の設定を読み込むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d854c-122">When creating the Codespace, we recommend to enter `microsoft/Quantum` in the "Git Repository" field to load QDK-specific settings.</span></span>
3. <span data-ttu-id="d854c-123">これで、新しい環境を起動し、[VS Codespaces のクラウド IDE](https://online.visualstudio.com/environments) を使用してブラウザーで開発を開始できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d854c-123">You can now launch your new environment and start developing in the browser via the [VS Codespaces Cloud IDE](https://online.visualstudio.com/environments).</span></span> <span data-ttu-id="d854c-124">または、VS Code のローカル インストールを使用して、[リモート環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)として Codespaces を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d854c-124">Alternatively, it is possible to use your local installation of VS Code and use Codespaces as a [remote environment](https://docs.microsoft.com/visualstudio/online/how-to/vscode).</span></span>


<span data-ttu-id="d854c-125">別の環境の QDK をインストールするには、コマンド プロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d854c-125">To install the QDK for another environment, enter the following at the command prompt:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-no-locq"></a><span data-ttu-id="d854c-126">Q# を使用した開発</span><span class="sxs-lookup"><span data-stu-id="d854c-126">Develop with Q#</span></span>

<span data-ttu-id="d854c-127">お使いの環境に対応するタブの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d854c-127">Follow the instructions on the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="d854c-128">VS Code</span><span class="sxs-lookup"><span data-stu-id="d854c-128">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="d854c-129">新しいプロジェクトを作成するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-129">To create a new project:</span></span>

1. <span data-ttu-id="d854c-130">**[表示]**  ->  **[コマンド パレット]** をクリックして、 **[Q#: 新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d854c-130">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="d854c-131">**[Standalone console application]\(スタンドアロン コンソール アプリケーション\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-131">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="d854c-132">プロジェクトを保存する場所に移動して、 **[プロジェクトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-132">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="d854c-133">プロジェクトが正常に作成されたら、右下にある **[Open new project...]\(新しいプロジェクトを開く...\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-133">When the project is successfully created, click **Open new project...** in the lower right.</span></span>

<span data-ttu-id="d854c-134">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="d854c-134">Inspect the project.</span></span> <span data-ttu-id="d854c-135">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="d854c-135">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="d854c-136">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-136">To run the application:</span></span>

1. <span data-ttu-id="d854c-137">**[ターミナル]**  ->  **[新しいターミナル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-137">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="d854c-138">ターミナル プロンプトで、`dotnet run` と入力します。</span><span class="sxs-lookup"><span data-stu-id="d854c-138">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="d854c-139">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d854c-139">You should see the following text in the output window `Hello quantum world!`</span></span>

> [!NOTE]
> <span data-ttu-id="d854c-140">複数のルート フォルダーを持つワークスペースは、VS Code の Q# 拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d854c-140">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="d854c-141">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d854c-141">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="d854c-142">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d854c-142">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="d854c-143">Q# の `Hello World` アプリケーションを作成して、Visual Studio のインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="d854c-143">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="d854c-144">新しい Q# アプリケーションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-144">To create a new Q# application:</span></span>

1. <span data-ttu-id="d854c-145">Visual Studio を開き、 **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-145">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="d854c-146">検索ボックスに「`Q#`」と入力し、 **[Q# アプリケーション]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-146">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="d854c-147">アプリケーションの名前と場所を入力して、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d854c-147">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="d854c-148">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="d854c-148">Inspect the project.</span></span> <span data-ttu-id="d854c-149">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="d854c-149">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="d854c-150">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="d854c-150">To run the application:</span></span>

1. <span data-ttu-id="d854c-151">**[デバッグ]**  ->  **[デバッグなしで開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d854c-151">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="d854c-152">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="d854c-152">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="d854c-153">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d854c-153">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-prompt"></a>[<span data-ttu-id="d854c-154">コマンド プロンプトを使用した他のエディター</span><span class="sxs-lookup"><span data-stu-id="d854c-154">Other editors with the command prompt</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="d854c-155">Q# の `Hello World` アプリケーションを作成して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="d854c-155">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="d854c-156">プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d854c-156">Install the project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. <span data-ttu-id="d854c-157">新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d854c-157">Create a new application:</span></span>

    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. <span data-ttu-id="d854c-158">アプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d854c-158">Navigate to the application directory:</span></span>

    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="d854c-159">このディレクトリには `Program.qs` という名前のファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="d854c-159">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="d854c-160">このテンプレートをテキスト エディターで変更し、独自のクォンタム アプリケーションで上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="d854c-160">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

1. <span data-ttu-id="d854c-161">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="d854c-161">Run the program:</span></span>

    ```dotnetcli
    dotnet run
    ```

1. <span data-ttu-id="d854c-162">次のように表示されます。`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="d854c-162">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="d854c-163">次のステップ</span><span class="sxs-lookup"><span data-stu-id="d854c-163">Next steps</span></span>

<span data-ttu-id="d854c-164">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d854c-164">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
