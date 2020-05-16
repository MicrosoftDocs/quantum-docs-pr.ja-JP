---
title: 'Q # コマンドラインアプリケーションを使用した開発'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e829862521951c50cb42eebf261c803071a95275
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426433"
---
# <a name="develop-with-q-command-line-applications"></a><span data-ttu-id="1b7f4-102">Q # コマンドラインアプリケーションを使用した開発</span><span class="sxs-lookup"><span data-stu-id="1b7f4-102">Develop with Q# command line applications</span></span>

<span data-ttu-id="1b7f4-103">Q # プログラムは、C#、F #、Python などのホスト言語でドライバーを使用しなくても、独自に実行できます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="1b7f4-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="1b7f4-104">Pre-requisites</span></span>

- [<span data-ttu-id="1b7f4-105">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="1b7f4-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="1b7f4-106">インストール</span><span class="sxs-lookup"><span data-stu-id="1b7f4-106">Installation</span></span>

<span data-ttu-id="1b7f4-107">任意の IDE で Q # コマンドラインアプリケーションをビルドできますが、Q # アプリケーションには Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-107">While you can build Q# command line applications in any IDE, we recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="1b7f4-108">これらのツールで開発することで、豊富な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-108">Developing in these tools provides access to rich functionality.</span></span>

<span data-ttu-id="1b7f4-109">VS Code を構成するには:</span><span class="sxs-lookup"><span data-stu-id="1b7f4-109">To configure VS Code:</span></span>

1. <span data-ttu-id="1b7f4-110">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、および Mac) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-110">Download and install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
2. <span data-ttu-id="1b7f4-111">[Microsoft QDK for VS Code を](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)インストールします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-111">Install the [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="1b7f4-112">Visual Studio を構成するには:</span><span class="sxs-lookup"><span data-stu-id="1b7f4-112">To configure Visual Studio:</span></span>

1. <span data-ttu-id="1b7f4-113">.NET Core クロスプラットフォームの開発ワークロードが有効になっている[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-113">Download and install [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 or greater, with the .NET Core cross-platform development workload enabled.</span></span>
2. <span data-ttu-id="1b7f4-114">[Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-114">Download and install the [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit).</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="1b7f4-115">VS Code を使用した Q # での開発</span><span class="sxs-lookup"><span data-stu-id="1b7f4-115">Develop with Q# using VS Code</span></span>

<span data-ttu-id="1b7f4-116">Q # プロジェクトテンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-116">Install the Q# project templates:</span></span>

1. <span data-ttu-id="1b7f4-117">VS Code を開きます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-117">Open VS Code.</span></span>
2. <span data-ttu-id="1b7f4-118">[ **View**  ->  **コマンドパレット**の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-118">Click **View** -> **Command Palette**.</span></span>
3. <span data-ttu-id="1b7f4-119">[ **Q #: Install project templates**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-119">Select **Q#: Install project templates**.</span></span>

<span data-ttu-id="1b7f4-120">**プロジェクトテンプレートが正常にインストール**されると、qdk を独自のアプリケーションやライブラリで使用する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-120">When **Project templates installed successfully** displays, the QDK is ready to use with your own applications and libraries.</span></span>

<span data-ttu-id="1b7f4-121">新しいプロジェクトを作成するには:</span><span class="sxs-lookup"><span data-stu-id="1b7f4-121">To create a new project:</span></span>

1. <span data-ttu-id="1b7f4-122">[ **View**  ->  **コマンドパレット**の表示] をクリックし、[ **Q #: 新しいプロジェクトの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-122">Click **View** -> **Command Palette** and select **Q#: Create New Project**.</span></span>
2. <span data-ttu-id="1b7f4-123">[**スタンドアロンコンソールアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-123">Click **Standalone console application**.</span></span>
3. <span data-ttu-id="1b7f4-124">プロジェクトを保存する場所に移動し、[**プロジェクトの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-124">Navigate to the location to save the project and click **Create Project**.</span></span>
4. <span data-ttu-id="1b7f4-125">プロジェクトが正常に作成されたら、右下にある [**新しいプロジェクトを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-125">When the project is successfully created, click **Open new project...** in the lower right.</span></span>
        
<span data-ttu-id="1b7f4-126">プロジェクトを検査します。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-126">Inspect the project.</span></span> <span data-ttu-id="1b7f4-127">という名前のソースファイルが表示 `Program.qs` されます。これは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-127">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1b7f4-128">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="1b7f4-128">To run the application:</span></span>
1. <span data-ttu-id="1b7f4-129">[**ターミナル**  ->  の**新しいターミナル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-129">Click **Terminal** -> **New Terminal**.</span></span>
2. <span data-ttu-id="1b7f4-130">ターミナルプロンプトで、「」と入力し `dotnet run` ます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-130">At the terminal prompt, enter `dotnet run`.</span></span>
3. <span data-ttu-id="1b7f4-131">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-131">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> <span data-ttu-id="1b7f4-132">複数のルートフォルダーを持つワークスペースは、現在 VS Code Q # 拡張機能ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-132">Workspaces with multiple root folders are not currently supported by the VS Code Q# extension.</span></span> <span data-ttu-id="1b7f4-133">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-133">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="1b7f4-134">Visual Studio を使用した Q # での開発</span><span class="sxs-lookup"><span data-stu-id="1b7f4-134">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="1b7f4-135">Q # アプリケーションを作成して、Visual Studio のインストールを確認し `Hello World` ます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-135">Verify your Visual Studio installation by creating a Q# `Hello World` application.</span></span>

<span data-ttu-id="1b7f4-136">新しい Q # アプリケーションを作成するには:</span><span class="sxs-lookup"><span data-stu-id="1b7f4-136">To create a new Q# application:</span></span>
1. <span data-ttu-id="1b7f4-137">Visual Studio を開き、[**ファイル**] [  ->  **新しい**  ->  **プロジェクト**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-137">Open Visual Studio and click **File** -> **New** -> **Project**.</span></span>
2. <span data-ttu-id="1b7f4-138">`Q#`検索ボックスに「」と入力し、[ **Q # アプリケーション**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-138">Type `Q#` in the search box, select **Q# Application** and click **Next**.</span></span>
3. <span data-ttu-id="1b7f4-139">アプリケーションの名前と場所を入力し、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-139">Enter a name and location for your application and click **Create**.</span></span>


<span data-ttu-id="1b7f4-140">プロジェクトを検査します。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-140">Inspect the project.</span></span> <span data-ttu-id="1b7f4-141">という名前のソースファイルが表示 `Program.qs` されます。これは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-141">You should see a source file named `Program.qs`, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

<span data-ttu-id="1b7f4-142">アプリケーションを実行するには:</span><span class="sxs-lookup"><span data-stu-id="1b7f4-142">To run the application:</span></span>
1. <span data-ttu-id="1b7f4-143">[**デバッグ**] [  ->  **デバッグなしで開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-143">Select **Debug** -> **Start Without Debugging**.</span></span>
2. <span data-ttu-id="1b7f4-144">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-144">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> <span data-ttu-id="1b7f4-145">1つの Visual Studio ソリューション内に複数のプロジェクトがある場合、ソリューションに含まれるすべてのプロジェクトは、ソリューションと同じフォルダー、またはそのサブフォルダーの1つに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-145">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its sub-folders.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="1b7f4-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="1b7f4-146">Next steps</span></span>

<span data-ttu-id="1b7f4-147">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1b7f4-147">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
