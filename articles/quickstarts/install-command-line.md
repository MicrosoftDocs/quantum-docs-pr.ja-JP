---
title: Q# コマンド ライン アプリケーションを使用した開発
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274124"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="a8ef9-102">Q# コマンド ライン アプリケーションを使用した開発</span><span class="sxs-lookup"><span data-stu-id="a8ef9-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="a8ef9-103">Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8ef9-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="a8ef9-104">Prerequisites</span></span>

- [<span data-ttu-id="a8ef9-105">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="a8ef9-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="a8ef9-106">インストール</span><span class="sxs-lookup"><span data-stu-id="a8ef9-106">Installation</span></span>

<span data-ttu-id="a8ef9-107">Q# コマンド ライン アプリケーションはどんな IDE でもビルドできますが、Q# アプリケーションでは Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="a8ef9-108">これらのツールで開発すると、豊富な機能を活用することができます。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="a8ef9-109">VS Code を構成するには:</span><span class="sxs-lookup"><span data-stu-id="a8ef9-109">To configure VS Code:</span></span>

1. <span data-ttu-id="a8ef9-110">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="a8ef9-111">[Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="a8ef9-112">Visual Studio を構成するには:</span><span class="sxs-lookup"><span data-stu-id="a8ef9-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="a8ef9-113">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="a8ef9-114">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="a8ef9-115">VS Code を使用した Q# での開発</span><span class="sxs-lookup"><span data-stu-id="a8ef9-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="a8ef9-116">Q# プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="a8ef9-117">VS Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-117">Open VS Code.</span></span>
2. <span data-ttu-id="a8ef9-118">**[表示]**  ->  **[コマンド パレット]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="a8ef9-119">**[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="a8ef9-120">**[Project templates installed successfully]\(プロジェクト テンプレートが正常にインストールされました\)** と表示されたら、QDK を自分のアプリケーションとライブラリで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="a8ef9-121">新しいプロジェクトを作成するには:</span><span class="sxs-lookup"><span data-stu-id="a8ef9-121">To create a new project:</span></span>

1. <span data-ttu-id="a8ef9-122">**[表示]**  ->  **[コマンド パレット]** をクリックして、 **[Q#:新しいプロジェクトの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="a8ef9-123">**[Standalone console application]\(スタンドアロン コンソール アプリケーション\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="a8ef9-124">プロジェクトを保存する場所に移動して、 **[プロジェクトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="a8ef9-125">プロジェクトが正常に作成されたら、右下にある **[Open new project...]\(新しいプロジェクトを開く...\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="a8ef9-126">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-126">Inspect the project.</span></span> <span data-ttu-id="a8ef9-127">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="a8ef9-128">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="a8ef9-128">To run the application:</span></span>
1. <span data-ttu-id="a8ef9-129">**[ターミナル]**  ->  **[新しいターミナル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="a8ef9-130">ターミナル プロンプトで、`dotnet run` と入力します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="a8ef9-131">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="a8ef9-132">複数のルート フォルダーを持つワークスペースは、VS Code の Q# 拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="a8ef9-133">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="a8ef9-134">Visual Studio を使用した Q# での開発</span><span class="sxs-lookup"><span data-stu-id="a8ef9-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="a8ef9-135">Q# の `Hello World` アプリケーションを作成して、Visual Studio のインストールを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="a8ef9-136">新しい Q# アプリケーションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="a8ef9-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="a8ef9-137">Visual Studio を開き、 **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="a8ef9-138">検索ボックスに `Q#` と入力し、 **[Q# アプリケーション]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="a8ef9-139">アプリケーションの名前と場所を入力して、 **[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="a8ef9-140">プロジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-140">Inspect the project.</span></span> <span data-ttu-id="a8ef9-141">`Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="a8ef9-142">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="a8ef9-142">To run the application:</span></span>
1. <span data-ttu-id="a8ef9-143">**[デバッグ]**  ->  **[デバッグなしで開始]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="a8ef9-144">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="a8ef9-145">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="a8ef9-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a8ef9-146">Next steps</span></span>

<span data-ttu-id="a8ef9-147">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a8ef9-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
