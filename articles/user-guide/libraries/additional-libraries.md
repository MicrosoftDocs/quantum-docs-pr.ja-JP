---
title: 追加の Q# ライブラリの使用
description: Quantum アプリケーションにライブラリを追加する方法について説明 Q# します。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: c558e25bf0d906ba6480cd7c41d3ece4ea97c2d1
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863082"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="33285-103">追加の Q# ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="33285-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="33285-104">Quantum Development Kit は、プロジェクトに追加できる _NuGet パッケージ_ によって、ドメイン固有の追加機能を提供し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="33285-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="33285-105">Q# ライブラリ</span><span class="sxs-lookup"><span data-stu-id="33285-105">Q# Library</span></span>  | <span data-ttu-id="33285-106">NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="33285-106">NuGet package</span></span> | <span data-ttu-id="33285-107">Notes</span><span class="sxs-lookup"><span data-stu-id="33285-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="33285-108">Q# 標準ライブラリ</span><span class="sxs-lookup"><span data-stu-id="33285-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="33285-109">**Microsoft. Quantum. Standard**</span><span class="sxs-lookup"><span data-stu-id="33285-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="33285-110">既定で含まれる</span><span class="sxs-lookup"><span data-stu-id="33285-110">Included by default</span></span> |
| [<span data-ttu-id="33285-111">量子化学ライブラリ</span><span class="sxs-lookup"><span data-stu-id="33285-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="33285-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="33285-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="33285-113">量子数値ライブラリ</span><span class="sxs-lookup"><span data-stu-id="33285-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="33285-114">**Microsoft. Quantum. 数値**</span><span class="sxs-lookup"><span data-stu-id="33285-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="33285-115">Quantum Machine Learning Library</span><span class="sxs-lookup"><span data-stu-id="33285-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="33285-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="33285-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="33285-117">任意の環境およびホスト言語で使用するために Quantum 開発キットをインストールすると、追加のインストールなしで個別のプロジェクトに簡単にライブラリを追加でき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="33285-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="33285-118">ライブラリによって Q# は、プログラムと共に動作する追加のツール Q# や、ホストアプリケーションと統合されるツールを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="33285-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="33285-119">たとえば、[化学ライブラリのインストール手順](xref:microsoft.quantum.chemistry.concepts.installation)では、NWChem 計算化学プラットフォームと共に[ **Microsoft の quantum**パッケージ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)を使用する方法と、 `qdk-chem` quantum の化学データを操作するためのコマンドラインツールをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="33285-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-applications-or-net-interopability"></a>[<span data-ttu-id="33285-120">Q# アプリケーションまたは .NET interopability</span><span class="sxs-lookup"><span data-stu-id="33285-120">Q# applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="33285-121">**コマンドプロンプトまたは Visual Studio Code:** コマンドプロンプトを単独で、または Visual Studio Code 内で使用すると、コマンドを使用して `dotnet` NuGet パッケージ参照をプロジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="33285-121">**Command prompt or Visual Studio Code:** Using the command prompt on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="33285-122">たとえば、 [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) パッケージを追加するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33285-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="33285-123">**Visual Studio:** Visual Studio 2019 以降を使用している場合は、 Q# NuGet パッケージマネージャーを使用してパッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="33285-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="33285-124">パッケージを読み込むには:</span><span class="sxs-lookup"><span data-stu-id="33285-124">To load a package:</span></span> 
1. <span data-ttu-id="33285-125">Visual Studio でプロジェクトを開いた状態で、[**プロジェクト**] メニューの [ **NuGet パッケージの管理...** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33285-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="33285-126">[ **参照**] をクリックし、[ **プレリリースを含める** ] を選択して、パッケージ名として「Microsoft. Quantum. 数値」を検索します。</span><span class="sxs-lookup"><span data-stu-id="33285-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="33285-127">これにより、ダウンロード可能なパッケージが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="33285-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="33285-128">[ **..** .] をポイントし、バージョン番号の右側にある下向きの矢印をクリックして、数値パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="33285-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="33285-129">詳細については、「 [パッケージマネージャー UI ガイド](https://docs.microsoft.com/nuget/tools/package-manager-ui)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33285-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="33285-130">または、パッケージマネージャーコンソールを使用して、コマンドラインインターフェイスを使用して数値ライブラリをプロジェクトに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="33285-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![コマンドプロンプトからのパッケージマネージャーコンソールの使用](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="33285-132">パッケージマネージャーコンソールで、次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="33285-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="33285-133">詳細については、「 [パッケージマネージャーコンソールガイド](https://docs.microsoft.com/nuget/tools/package-manager-console)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33285-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="33285-134">I Q# notebook</span><span class="sxs-lookup"><span data-stu-id="33285-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="33285-135">Q# [ `%package` マジックコマンド](xref:microsoft.quantum.iqsharp.magic-ref.package)を使用して、追加のパッケージを I Notebook で使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="33285-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="33285-136">たとえば、I notebook で使用するために [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) パッケージを追加するには、 Q# notebook セルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="33285-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="33285-137">このコマンドに従うと、notebook 内の任意のセルでパッケージを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="33285-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="33285-138">現在のワークスペースのコードからパッケージを使用できるようにするには Q# 、パッケージを追加した後でワークスペースを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="33285-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="33285-139">Python の相互運用性</span><span class="sxs-lookup"><span data-stu-id="33285-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="33285-140">メソッドを使用して、Python ホストプログラムで追加のパッケージを使用できるようにすることができ [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) ます。</span><span class="sxs-lookup"><span data-stu-id="33285-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="33285-141">たとえば、I Notebook で使用するために [**Microsoft の Quantum**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) パッケージを追加するには、 Q# 次の Python コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="33285-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="33285-142">このコマンドに従うと、 Q# を使用してコンパイルされたすべてのコードでパッケージが使用できるようになり `qsharp.compile` ます。</span><span class="sxs-lookup"><span data-stu-id="33285-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="33285-143">現在のワークスペースのコードからパッケージを使用できるようにするには Q# 、パッケージを追加した後でワークスペースを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="33285-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
