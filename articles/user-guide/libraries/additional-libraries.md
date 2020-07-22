---
title: その他の Q# ライブラリを使用する
description: '他の Q # ライブラリを quantum アプリケーションに追加する方法について説明します。'
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
ms.openlocfilehash: b82113b925870d07c8a28aecd50176e009826062
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872636"
---
# <a name="using-additional-q-libraries"></a><span data-ttu-id="ff268-103">追加の Q # ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="ff268-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="ff268-104">Quantum Development Kit は、Q # プロジェクトに追加できる_NuGet パッケージ_を使用して、ドメイン固有の追加機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ff268-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="ff268-105">Q # ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ff268-105">Q# Library</span></span>  | <span data-ttu-id="ff268-106">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="ff268-106">NuGet package</span></span> | <span data-ttu-id="ff268-107">Notes</span><span class="sxs-lookup"><span data-stu-id="ff268-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="ff268-108">Q # 標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ff268-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="ff268-109">**Microsoft. Quantum. Standard**</span><span class="sxs-lookup"><span data-stu-id="ff268-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="ff268-110">既定で含まれる</span><span class="sxs-lookup"><span data-stu-id="ff268-110">Included by default</span></span> |
| [<span data-ttu-id="ff268-111">量子化学ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ff268-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="ff268-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="ff268-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="ff268-113">量子数値ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ff268-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="ff268-114">**Microsoft. Quantum. 数値**</span><span class="sxs-lookup"><span data-stu-id="ff268-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="ff268-115">Quantum Machine Learning Library</span><span class="sxs-lookup"><span data-stu-id="ff268-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="ff268-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="ff268-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="ff268-117">任意の環境およびホスト言語で使用するために Quantum 開発キットをインストールすると、追加のインストールを行わなくても、個別の Q # プロジェクトに簡単にライブラリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ff268-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="ff268-118">一部の Q # ライブラリは、Q # プログラムと並行して動作する追加のツールや、ホストアプリケーションと統合されているツールで適切に動作する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ff268-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="ff268-119">たとえば、[化学ライブラリのインストール手順](xref:microsoft.quantum.chemistry.concepts.installation)では、NWChem 計算化学プラットフォームと共に[ **Microsoft の quantum**パッケージ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)を使用する方法と、 `qdk-chem` quantum の化学データを操作するためのコマンドラインツールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff268-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="q-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="ff268-120">Q # コマンドラインアプリケーションまたは .NET interopability</span><span class="sxs-lookup"><span data-stu-id="ff268-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="ff268-121">**コマンドラインまたは Visual Studio Code:** コマンドラインを単独で使用するか Visual Studio Code 内から使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="ff268-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="ff268-122">たとえば、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)パッケージを追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff268-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="ff268-123">**Visual Studio:** Visual Studio 2019 以降を使用している場合は、NuGet パッケージマネージャーを使用して追加の Q # パッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ff268-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="ff268-124">パッケージを読み込むには:</span><span class="sxs-lookup"><span data-stu-id="ff268-124">To load a package:</span></span> 
1. <span data-ttu-id="ff268-125">Visual Studio でプロジェクトを開いた状態で、[**プロジェクト**] メニューの [ **NuGet パッケージの管理...** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff268-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="ff268-126">[**参照**] をクリックし、[**プレリリースを含める**] を選択して、パッケージ名として「Microsoft. Quantum. 数値」を検索します。</span><span class="sxs-lookup"><span data-stu-id="ff268-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="ff268-127">これにより、ダウンロード可能なパッケージが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ff268-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="ff268-128">[ **..** .] をポイントし、バージョン番号の右側にある下向きの矢印をクリックして、数値パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff268-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="ff268-129">詳細については、「[パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff268-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="ff268-130">または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ff268-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![コマンドラインからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="ff268-132">パッケージマネージャーコンソールで、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="ff268-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="ff268-133">詳細については、「[パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff268-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="iq-notebooks"></a>[<span data-ttu-id="ff268-134">IQ # Notebook</span><span class="sxs-lookup"><span data-stu-id="ff268-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="ff268-135">[ `%package` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.package)を使用して、他のパッケージを IQ # Notebook で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ff268-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="ff268-136">たとえば、IQ # Notebook で使用するために、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)パッケージを追加するには、notebook セルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff268-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="ff268-137">このコマンドに従うと、notebook 内の任意のセルでパッケージを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ff268-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="ff268-138">現在のワークスペースの Q # コードからパッケージを使用できるようにするには、パッケージを追加した後でワークスペースを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="ff268-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="ff268-139">Python の相互運用性</span><span class="sxs-lookup"><span data-stu-id="ff268-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="ff268-140">メソッドを使用して、Python ホストプログラムで追加のパッケージを使用できるようにすることができ [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) ます。</span><span class="sxs-lookup"><span data-stu-id="ff268-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="ff268-141">たとえば、IQ # Notebook で使用するために、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)パッケージを追加するには、次の Python コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff268-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="ff268-142">このコマンドに従うと、を使用してコンパイルされたすべての Q # コードでパッケージが使用できるようになり `qsharp.compile` ます。</span><span class="sxs-lookup"><span data-stu-id="ff268-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="ff268-143">現在のワークスペースの Q # コードからパッケージを使用できるようにするには、パッケージを追加した後でワークスペースを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="ff268-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
