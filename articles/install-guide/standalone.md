---
title: 'ドライバーとホスト言語を使用せずに Q # プログラムを実行する'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: e83acaf10af952da06abf4737ad2ec91f1cf1b8e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82706803"
---
# <a name="q-command-line-applications"></a><span data-ttu-id="43367-102">Q # コマンドラインアプリケーション</span><span class="sxs-lookup"><span data-stu-id="43367-102">Q# Command Line Applications</span></span>

<span data-ttu-id="43367-103">Q # プログラムは、C#、F #、Python などのホスト言語でドライバーを使用しなくても、独自に実行できます。</span><span class="sxs-lookup"><span data-stu-id="43367-103">Q# programs can be executed on their own, without a driver in a host language like C#, F#, or Python.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="43367-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="43367-104">Pre-requisites</span></span>

- [<span data-ttu-id="43367-105">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="43367-105">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)

## <a name="installation"></a><span data-ttu-id="43367-106">インストール</span><span class="sxs-lookup"><span data-stu-id="43367-106">Installation</span></span>

<span data-ttu-id="43367-107">任意の IDE で Q # コマンドラインアプリケーションをビルドできますが、Q # アプリケーションには Visual Studio Code (VS Code) または Visual Studio IDE を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="43367-107">While you can build Q# command line applications in any IDE, we highly recommend using Visual Studio Code (VS Code) or Visual Studio IDE for your Q# applications.</span></span> <span data-ttu-id="43367-108">VS Code または Visual Studio と QDK Visual Studio Code 拡張機能を使用すると、豊富な機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="43367-108">By using VS Code or Visual Studio and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

- <span data-ttu-id="43367-109">[VS Code](https://code.visualstudio.com/download)のインストール (Windows、Linux、および Mac)</span><span class="sxs-lookup"><span data-stu-id="43367-109">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
- <span data-ttu-id="43367-110">VS Code またはの [QDK 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="43367-110">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) OR</span></span>
- <span data-ttu-id="43367-111">.NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3</span><span class="sxs-lookup"><span data-stu-id="43367-111">[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3, with the .NET Core cross-platform development workload enabled</span></span>
- <span data-ttu-id="43367-112">[Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードしてインストールする</span><span class="sxs-lookup"><span data-stu-id="43367-112">Download and install the [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)</span></span>


## <a name="develop-with-q-using-vs-code"></a><span data-ttu-id="43367-113">VS Code を使用した Q # での開発</span><span class="sxs-lookup"><span data-stu-id="43367-113">Develop with Q# using VS Code</span></span>

<span data-ttu-id="43367-114">量子プロジェクト テンプレートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="43367-114">Install the Quantum project templates:</span></span>

- <span data-ttu-id="43367-115">**表示** -> **コマンド パレット**にアクセス</span><span class="sxs-lookup"><span data-stu-id="43367-115">Go to **View** -> **Command Palette**</span></span>
- <span data-ttu-id="43367-116">[ **Q#: Install project templates**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="43367-116">Select **Q#: Install project templates**</span></span>

<span data-ttu-id="43367-117">これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="43367-117">You now have the Quantum Development Kit installed and ready to use in your own applications and libraries.</span></span>
- <span data-ttu-id="43367-118">新しいプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="43367-118">Create a new project:</span></span>
  - <span data-ttu-id="43367-119">**表示** -> **コマンド パレット**にアクセス</span><span class="sxs-lookup"><span data-stu-id="43367-119">Go to **View** -> **Command Palette**</span></span>
  - <span data-ttu-id="43367-120">**[Q#: Create New Project]\(Q#: 新しいプロジェクトの作成\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="43367-120">Select **Q#: Create New Project**</span></span>
  - <span data-ttu-id="43367-121">**[Standalone console application]\(スタンドアロンコンソールアプリケーション\)**の選択</span><span class="sxs-lookup"><span data-stu-id="43367-121">Select **Standalone console application**</span></span>
  - <span data-ttu-id="43367-122">アプリケーションの作成先となるファイル システム上の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="43367-122">Navigate to the location on the file system where you would like to create the application</span></span>
  - <span data-ttu-id="43367-123">プロジェクトが作成されたら、**[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="43367-123">Click on the **Open new project...** button, once the project has been created</span></span>
        
- <span data-ttu-id="43367-124">プロジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="43367-124">Inspect the project</span></span>
  - <span data-ttu-id="43367-125">"Created" という名前`Program.qs`のファイルが表示されます。このファイルは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。</span><span class="sxs-lookup"><span data-stu-id="43367-125">You should see that a file called `Program.qs` created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="43367-126">アプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="43367-126">Run the application:</span></span>
  - <span data-ttu-id="43367-127">**ターミナル** -> **新しいターミナル**にアクセス</span><span class="sxs-lookup"><span data-stu-id="43367-127">Go to **Terminal** -> **New Terminal**</span></span>
  - <span data-ttu-id="43367-128">「`dotnet run`」と入力します</span><span class="sxs-lookup"><span data-stu-id="43367-128">Enter `dotnet run`</span></span>
  - <span data-ttu-id="43367-129">出力ウィンドウに `Hello quantum world!` というテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="43367-129">You should see the following text in the output window `Hello quantum world!`</span></span>


> [!NOTE]
> * <span data-ttu-id="43367-130">複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="43367-130">Workspaces with multiple root folders are not currently supported by the Visual Studio Code extension.</span></span> <span data-ttu-id="43367-131">1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43367-131">If you have multiple projects within one VS Code workspace, all projects need to be contained within the same root folder.</span></span>

## <a name="develop-with-q-using-visual-studio"></a><span data-ttu-id="43367-132">Visual Studio を使用した Q # での開発</span><span class="sxs-lookup"><span data-stu-id="43367-132">Develop with Q# using Visual Studio</span></span>

<span data-ttu-id="43367-133">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="43367-133">Verify the installation by creating a `Hello World` application</span></span>

- <span data-ttu-id="43367-134">新しい Q# アプリケーションを作成する</span><span class="sxs-lookup"><span data-stu-id="43367-134">Create a new Q# application</span></span>
  - <span data-ttu-id="43367-135">**ファイル** -> の**新しい** -> **プロジェクト**にアクセス</span><span class="sxs-lookup"><span data-stu-id="43367-135">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="43367-136">検索ボックスに、「`Q#`」と入力します</span><span class="sxs-lookup"><span data-stu-id="43367-136">Type `Q#` in the search box</span></span>
  - <span data-ttu-id="43367-137">**[Q# Application]\(Q# アプリケーション\)** を選択します</span><span class="sxs-lookup"><span data-stu-id="43367-137">Select **Q# Application**</span></span>
  - <span data-ttu-id="43367-138">**次**を選択</span><span class="sxs-lookup"><span data-stu-id="43367-138">Select **Next**</span></span>
  - <span data-ttu-id="43367-139">アプリケーションの名前と格納する場所を選択します</span><span class="sxs-lookup"><span data-stu-id="43367-139">Choose a name and location for your application</span></span>
  - <span data-ttu-id="43367-140">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="43367-140">Select **Create**</span></span>

- <span data-ttu-id="43367-141">プロジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="43367-141">Inspect the project</span></span>
  - <span data-ttu-id="43367-142">という名前`Program.qs`のファイルが作成されていることがわかります。これは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。</span><span class="sxs-lookup"><span data-stu-id="43367-142">You should see that a file called `Program.qs` has been created, which is a Q# program that defines a simple operation to print a message to the console.</span></span>

- <span data-ttu-id="43367-143">アプリケーションの実行</span><span class="sxs-lookup"><span data-stu-id="43367-143">Run the application</span></span>
  - <span data-ttu-id="43367-144">デバッグ**Debug** -> を**行わないデバッグ開始**の選択</span><span class="sxs-lookup"><span data-stu-id="43367-144">Select **Debug** -> **Start Without Debugging**</span></span>
  - <span data-ttu-id="43367-145">テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。</span><span class="sxs-lookup"><span data-stu-id="43367-145">You should see the text `Hello quantum world!` printed to a console window.</span></span>

> [!NOTE]
> * <span data-ttu-id="43367-146">1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43367-146">If you have multiple projects within one Visual Studio solution, all projects contained in the solution need to be in the same folder as the solution, or in one of its subfolders.</span></span>  


## <a name="whats-next"></a><span data-ttu-id="43367-147">次の内容</span><span class="sxs-lookup"><span data-stu-id="43367-147">What's next?</span></span>

<span data-ttu-id="43367-148">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="43367-148">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
