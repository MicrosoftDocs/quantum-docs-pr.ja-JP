---
title: Q# と C# を使用した開発
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680164"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="f1233-102">Q # を C\#および F と共に使用する\#</span><span class="sxs-lookup"><span data-stu-id="f1233-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="f1233-103">Q # は、C# や F # などの .NET 言語で適切に動作するように構築されています。</span><span class="sxs-lookup"><span data-stu-id="f1233-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="f1233-104">このガイドでは、.NET 言語で記述されたホストプログラムで Q # を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1233-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1233-105">[前提条件]</span><span class="sxs-lookup"><span data-stu-id="f1233-105">Prerequisites</span></span>

- <span data-ttu-id="f1233-106">[Q # コマンドラインプロジェクトで使用するための](xref:microsoft.quantum.install.standalone)Quantum 開発キットをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f1233-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="f1233-107">Q # ライブラリと .NET ホストの作成</span><span class="sxs-lookup"><span data-stu-id="f1233-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="f1233-108">最初の手順では、Q # ライブラリのプロジェクトを作成し、Q # ライブラリで定義されている操作と関数を呼び出す .NET ホストを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1233-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="f1233-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f1233-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="f1233-110">新しい Q # ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="f1233-110">Create a new Q# library</span></span>
  - <span data-ttu-id="f1233-111">**ファイル** -> の**新しい** -> **プロジェクト**にアクセス</span><span class="sxs-lookup"><span data-stu-id="f1233-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="f1233-112">検索ボックスに「Q #」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f1233-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="f1233-113">**Q # ライブラリ**を選択します</span><span class="sxs-lookup"><span data-stu-id="f1233-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="f1233-114">**次**を選択</span><span class="sxs-lookup"><span data-stu-id="f1233-114">Select **Next**</span></span>
  - <span data-ttu-id="f1233-115">ライブラリの名前と場所を選択します</span><span class="sxs-lookup"><span data-stu-id="f1233-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="f1233-116">[プロジェクトとソリューションを同じディレクトリに配置する] が**オフ**になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f1233-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="f1233-117">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="f1233-117">Select **Create**</span></span>
- <span data-ttu-id="f1233-118">新しい C# または F # ホストプログラムを作成する</span><span class="sxs-lookup"><span data-stu-id="f1233-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="f1233-119">**ファイル**にジャンプ→ [**新規**] → [**プロジェクト**]</span><span class="sxs-lookup"><span data-stu-id="f1233-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="f1233-120">C# または F に対して [Console App (.NET Core)] を選択します。#</span><span class="sxs-lookup"><span data-stu-id="f1233-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="f1233-121">**次**を選択</span><span class="sxs-lookup"><span data-stu-id="f1233-121">Select **Next**</span></span>
  - <span data-ttu-id="f1233-122">[*ソリューション*] で、[ソリューションに追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1233-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="f1233-123">ホストプログラムの名前を選択してください</span><span class="sxs-lookup"><span data-stu-id="f1233-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="f1233-124">**[作成]**</span><span class="sxs-lookup"><span data-stu-id="f1233-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="f1233-125">Visual Studio Code またはコマンドライン</span><span class="sxs-lookup"><span data-stu-id="f1233-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="f1233-126">新しい Q # ライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="f1233-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="f1233-127">新しい C# または F # コンソールプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="f1233-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="f1233-128">ホストプログラムからの参照として Q # ライブラリを追加する</span><span class="sxs-lookup"><span data-stu-id="f1233-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="f1233-129">Optional両方のプロジェクトのソリューションを作成する</span><span class="sxs-lookup"><span data-stu-id="f1233-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="f1233-130">.NET から Q # への呼び出し</span><span class="sxs-lookup"><span data-stu-id="f1233-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="f1233-131">上記の手順に従ってプロジェクトを設定したら、.NET コンソールアプリケーションから Q # を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1233-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="f1233-132">Q # コンパイラは、各 Q # 操作に対して .NET クラスを作成し、シミュレーターでクォンタムプログラムを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f1233-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="f1233-133">たとえば、 [.net 相互運用性のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)には、Q # 操作の次の例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f1233-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="f1233-134">クォンタムシミュレーターで .NET からこの操作を呼び出すには、Q # コンパイラ`Run`によって`RunAlgorithm`生成された .net クラスのメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1233-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="f1233-135">C#</span><span class="sxs-lookup"><span data-stu-id="f1233-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="f1233-136">F#</span><span class="sxs-lookup"><span data-stu-id="f1233-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="f1233-137">次の内容</span><span class="sxs-lookup"><span data-stu-id="f1233-137">What's next?</span></span>

<span data-ttu-id="f1233-138">これで、2つのコマンドラインプログラムに対してクォンタム開発キットがセットアップされました。また、.NET との相互運用性のために、[最初のクォンタムプログラム](xref:microsoft.quantum.write-program)を記述して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f1233-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
