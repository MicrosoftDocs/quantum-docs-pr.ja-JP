---
title: Q# コマンド ライン アプリケーションを使用した開発
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884285"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="b47c4-102">Q# コマンド ライン アプリケーションを使用した開発</span><span class="sxs-lookup"><span data-stu-id="b47c4-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="b47c4-103">Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b47c4-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b47c4-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="b47c4-104">Prerequisites</span></span>

- [<span data-ttu-id="b47c4-105">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="b47c4-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="b47c4-106">インストール</span><span class="sxs-lookup"><span data-stu-id="b47c4-106">Installation</span></span>

<span data-ttu-id="b47c4-107">Q# コマンド ライン アプリケーションはどんな IDE でもビルドできますが、Q# アプリケーションでは Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="b47c4-108">これらの環境での開発には、警告、構文の強調表示、プロジェクト テンプレートなど、QDK 拡張機能の豊富な機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b47c4-108">Developing in these environments includes the rich functionality of the QDK extension, which includes warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="b47c4-109">VS Code を構成するには:</span><span class="sxs-lookup"><span data-stu-id="b47c4-109">To configure VS Code:</span></span>

1. <span data-ttu-id="b47c4-110">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="b47c4-111">[Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="b47c4-112">Visual Studio を構成するには:</span><span class="sxs-lookup"><span data-stu-id="b47c4-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="b47c4-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="b47c4-114">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>

<span data-ttu-id="b47c4-115">別の環境の QDK をインストールするには、コマンド ラインで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-115">To install the QDK for another environment, enter in the command line:</span></span>

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a><span data-ttu-id="b47c4-116">Q# を使用した開発</span><span class="sxs-lookup"><span data-stu-id="b47c4-116">Develop with Q#</span></span>

<span data-ttu-id="b47c4-117">お使いの環境に対応するタブの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="b47c4-117">Follow the instructions at the tab corresponding to your environment.</span></span>

### <a name="vs-code"></a>[<span data-ttu-id="b47c4-118">VS Code</span><span class="sxs-lookup"><span data-stu-id="b47c4-118">VS Code</span></span>](#tab/tabid-vscode)

<span data-ttu-id="b47c4-119">Q# プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-119">Install the Q# project templates:</span></span>

1. <span data-ttu-id="b47c4-120">VS Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="b47c4-120">Open VS Code.</span></span>
2. <span data-ttu-id="b47c4-121">**[表示]**  ->  **[コマンド パレット]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-121">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="b47c4-122">**[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-122">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="b47c4-123">**[Project templates installed successfully]\(プロジェクト テンプレートが正常にインストールされました\)** と表示されたら、QDK を自分のアプリケーションとライブラリで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b47c4-123">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="b47c4-124">新しいプロジェクトを作成するには:</span><span class="sxs-lookup"><span data-stu-id="b47c4-124">To create a new project:</span></span>

1. <span data-ttu-id="b47c4-125">**[表示]**  ->  **[コマンド パレット]** をクリックして、 **[Q#:新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-125">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="b47c4-126">**[Standalone console application]\(スタンドアロン コンソール アプリケーション\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-126">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="b47c4-127">プロジェクトを保存する場所に移動して、 **[プロジェクトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-127">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="b47c4-128">プロジェクトが正常に作成されたら、右下にある **[Open new project...]\(新しいプロジェクトを開く...\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-128">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="b47c4-129">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-129">Inspect the project.</span></span> <span data-ttu-id="b47c4-130">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="b47c4-130">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b47c4-131">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="b47c4-131">To run the application:</span></span>
1. <span data-ttu-id="b47c4-132">**[ターミナル]**  ->  **[新しいターミナル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-132">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="b47c4-133">ターミナル プロンプトで、`dotnet run` と入力します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-133">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="b47c4-134">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b47c4-134">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="b47c4-135">複数のルート フォルダーを持つワークスペースは、VS Code の Q# 拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b47c4-135">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="b47c4-136">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b47c4-136">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

### <a name="visual-studio"></a>[<span data-ttu-id="b47c4-137">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b47c4-137">Visual Studio</span></span>](#tab/tabid-vs)

<span data-ttu-id="b47c4-138">Q# の `Hello World` アプリケーションを作成して、Visual Studio のインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-138">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="b47c4-139">新しい Q# アプリケーションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="b47c4-139">To create a new Q# application:</span></span>
1. <span data-ttu-id="b47c4-140">Visual Studio を開き、 **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-140">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="b47c4-141">検索ボックスに `Q#` と入力し、 **[Q# アプリケーション]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-141">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="b47c4-142">アプリケーションの名前と場所を入力して、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b47c4-142">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="b47c4-143">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-143">Inspect the project.</span></span> <span data-ttu-id="b47c4-144">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="b47c4-144">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="b47c4-145">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="b47c4-145">To run the application:</span></span>
1. <span data-ttu-id="b47c4-146">**[デバッグ]**  ->  **[デバッグなしで開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-146">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="b47c4-147">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="b47c4-147">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="b47c4-148">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b47c4-148">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  

### <a name="other-editors-with-the-command-line"></a>[<span data-ttu-id="b47c4-149">コマンド ラインを使用した他のエディター</span><span class="sxs-lookup"><span data-stu-id="b47c4-149">Other editors with the command line</span></span>](#tab/tabid-cmdline)

<span data-ttu-id="b47c4-150">Q# の `Hello World` アプリケーションを作成して、インストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-150">Verify your installation by creating a Q# `Hello World` application.</span></span>

1. <span data-ttu-id="b47c4-151">新しいアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-151">Create a new application:</span></span>
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. <span data-ttu-id="b47c4-152">アプリケーション ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-152">Navigate to the application directory:</span></span>
    ```dotnetcli
    cd runSayHello
    ```

    <span data-ttu-id="b47c4-153">このディレクトリには `Program.qs` という名前のファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="b47c4-153">This directory should now contain a file `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span> <span data-ttu-id="b47c4-154">このテンプレートをテキスト エディターで変更し、独自のクォンタム アプリケーションで上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="b47c4-154">You can modfiy this template with a text editor and overwrite it with your own quantum applications.</span></span> 

3. <span data-ttu-id="b47c4-155">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="b47c4-155">Run the program:</span></span>
    ```dotnetcli
    dotnet run
    ```

4. <span data-ttu-id="b47c4-156">次のように表示されます。`Hello quantum world!`</span><span class="sxs-lookup"><span data-stu-id="b47c4-156">You should see the following text printed: `Hello quantum world!`</span></span>

***

## <a name="next-steps"></a><span data-ttu-id="b47c4-157">次のステップ</span><span class="sxs-lookup"><span data-stu-id="b47c4-157">Next steps</span></span>

<span data-ttu-id="b47c4-158">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b47c4-158">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
