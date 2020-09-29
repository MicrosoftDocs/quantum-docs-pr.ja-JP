---
title: Q# と .NET を使用した開発
description: .NET 言語を使用して Q# アプリケーションを作成する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: e8733918daa02afaea0fc1994d5f0851d4be9b93
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834331"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="2f5ca-103">Q# と .NET を使用した開発</span><span class="sxs-lookup"><span data-stu-id="2f5ca-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="2f5ca-104">Q# は、C# や F# などの .NET 言語とうまく動作するように構築されています。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="2f5ca-105">このガイドでは、Q# を .NET 言語で作成されたホスト プログラムとともに使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="2f5ca-106">まず、Q# アプリケーションと .NET ホストを作成し、次にホストから Q# を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2f5ca-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="2f5ca-107">Prerequisites</span></span>

- <span data-ttu-id="2f5ca-108">[Q# プロジェクトで使用するための](xref:microsoft.quantum.install.standalone) Quantum 開発キットをインストールしていること。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="2f5ca-109">Q# ライブラリと .NET ホストを作成する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="2f5ca-110">最初の手順として、Q# ライブラリのプロジェクトと、Q# ライブラリで定義された演算と関数を呼び出す .NET ホストのプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="2f5ca-111">お使いの開発環境に対応するタブの指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="2f5ca-112">Visual Studio または VS Code 以外のエディターを使用している場合は、コマンド プロンプトの手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="2f5ca-113">Visual Studio Code またはコマンド プロンプト</span><span class="sxs-lookup"><span data-stu-id="2f5ca-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="2f5ca-114">新しい Q# ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="2f5ca-115">新しい C# または F# のコンソール プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="2f5ca-116">Q# ライブラリを、ホスト プログラムからの参照として追加する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="2f5ca-117">[オプション] 両方のプロジェクトに対してソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="2f5ca-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="2f5ca-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="2f5ca-119">新しい Q# ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-119">Create a new Q# library</span></span>
  - <span data-ttu-id="2f5ca-120">**[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="2f5ca-121">検索ボックスに、「Q#」と入力します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="2f5ca-122">**[Q#ライブラリ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="2f5ca-123">**[次へ]** を選択します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-123">Select **Next**</span></span>
  - <span data-ttu-id="2f5ca-124">ライブラリの名前と場所を選択します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="2f5ca-125">[ソリューションとプロジェクトを同じディレクトリに配置する] に**チェックを入れない**ようにします</span><span class="sxs-lookup"><span data-stu-id="2f5ca-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="2f5ca-126">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="2f5ca-126">Select **Create**</span></span>
- <span data-ttu-id="2f5ca-127">新しい C# または F# のホスト プログラムを作成する</span><span class="sxs-lookup"><span data-stu-id="2f5ca-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="2f5ca-128">**[ファイル]** → **[新規作成]** → **[プロジェクト]** に移動します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="2f5ca-129">C# または F# の [コンソール アプリ (.NET Core)] を選択します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="2f5ca-130">**[次へ]** を選択します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-130">Select **Next**</span></span>
  - <span data-ttu-id="2f5ca-131">*[ソリューション]* で、[ソリューションに追加] を選択します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="2f5ca-132">ホスト プログラムの名前を選択します</span><span class="sxs-lookup"><span data-stu-id="2f5ca-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="2f5ca-133">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="2f5ca-133">Select **Create**</span></span>

***

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="2f5ca-134">.NET から Q# を呼び出す</span><span class="sxs-lookup"><span data-stu-id="2f5ca-134">Calling into Q# from .NET</span></span>

<span data-ttu-id="2f5ca-135">上の手順に従ってプロジェクトを設定したら、.NET コンソール アプリケーションから Q# を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-135">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="2f5ca-136">Q# コンパイラは、それぞれの Q# の演算と関数に対して .NET クラスを作成します。これにより、量子プログラムをシミュレーターで実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-136">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="2f5ca-137">たとえば、[.NET の相互運用性サンプル](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)には、次の Q# の演算の例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-137">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="2f5ca-138">量子シミュレーターで .NET からこの演算を呼び出すには、Q# コンパイラが生成した `RunAlgorithm` .NET クラスの `Run` メソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-138">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="2f5ca-139">C#</span><span class="sxs-lookup"><span data-stu-id="2f5ca-139">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="2f5ca-140">F#</span><span class="sxs-lookup"><span data-stu-id="2f5ca-140">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="2f5ca-141">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2f5ca-141">Next steps</span></span>

<span data-ttu-id="2f5ca-142">これで、Q# アプリケーションと .NET との相互運用性の両方に対して Quantum 開発キットを設定することができたので、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="2f5ca-142">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
