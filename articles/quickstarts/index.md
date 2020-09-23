---
title: Microsoft Quantum 開発キット (QDK) の設定
description: さまざまな環境に合わせて Microsoft Quantum 開発キットを設定する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 74b9b3d8f694072f5b5f4d0eb520263387de8919
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834484"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="e17ef-103">Microsoft Quantum 開発キット (QDK) の設定</span><span class="sxs-lookup"><span data-stu-id="e17ef-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="e17ef-104">量子プログラミングを開始できるように、お使いの環境に合わせて Microsoft Quantum 開発キット (QDK) を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e17ef-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="e17ef-105">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-105">The QDK consists of:</span></span>

- <span data-ttu-id="e17ef-106">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="e17ef-106">The Q# programming language</span></span>
- <span data-ttu-id="e17ef-107">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="e17ef-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="e17ef-108">Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)</span><span class="sxs-lookup"><span data-stu-id="e17ef-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="e17ef-109">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="e17ef-109">Tools to facilitate your development</span></span>

<span data-ttu-id="e17ef-110">Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、あるいは Python または .NET 言語 (C#、F#) で作成されたホスト プログラムと組み合わせて、スタンドアロン アプリケーションとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="e17ef-111">また、[Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/)、または [Docker](#use-the-qdk-with-docker) を使用して、Q# プログラムをオンラインで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="e17ef-112">QDK を設定するためのオプション</span><span class="sxs-lookup"><span data-stu-id="e17ef-112">Options for setting up the QDK</span></span>

<span data-ttu-id="e17ef-113">QDK は、次の 3 つの方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="e17ef-114">QDK をローカルにインストールする</span><span class="sxs-lookup"><span data-stu-id="e17ef-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="e17ef-115">QDK をオンラインで使用する</span><span class="sxs-lookup"><span data-stu-id="e17ef-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="e17ef-116">QDK Docker イメージを使用する</span><span class="sxs-lookup"><span data-stu-id="e17ef-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="e17ef-117">QDK をローカルにインストールする</span><span class="sxs-lookup"><span data-stu-id="e17ef-117">Install the QDK locally</span></span>

<span data-ttu-id="e17ef-118">ほとんどの使い慣れた IDE で Q# コードを開発できるだけでなく、Python や .NET (C#、F#) などの他の言語と Q# を統合することもできます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

|&nbsp; | <span data-ttu-id="e17ef-119">**VS Code<br> (2019 以降)**</span><span class="sxs-lookup"><span data-stu-id="e17ef-119">**VS Code<br>(2019 or later)**</span></span>| <span data-ttu-id="e17ef-120">**Visual Studio<br> (2019 以降)**</span><span class="sxs-lookup"><span data-stu-id="e17ef-120">**Visual Studio<br>(2019 or later)**</span></span> | <span data-ttu-id="e17ef-121">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="e17ef-121">**Jupyter Notebooks**</span></span> | <span data-ttu-id="e17ef-122">**コマンド ライン**</span><span class="sxs-lookup"><span data-stu-id="e17ef-122">**Command line**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="e17ef-123">**OS**</span><span class="sxs-lookup"><span data-stu-id="e17ef-123">**OS**</span></span> |<span data-ttu-id="e17ef-124">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="e17ef-124">Windows, macOS, Linux</span></span> |<span data-ttu-id="e17ef-125">Windows のみ</span><span class="sxs-lookup"><span data-stu-id="e17ef-125">Windows only</span></span> |<span data-ttu-id="e17ef-126">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="e17ef-126">Windows, macOS, Linux</span></span> |<span data-ttu-id="e17ef-127">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="e17ef-127">Windows, macOS, Linux</span></span> |
|<br><span data-ttu-id="e17ef-128">**Q# スタンドアロン**</span><span class="sxs-lookup"><span data-stu-id="e17ef-128">**Q# standalone**</span></span> |<br>[<span data-ttu-id="e17ef-129">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-129">Install</span></span>](xref:microsoft.quantum.install.standalone) |<br> [<span data-ttu-id="e17ef-130">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-130">Install</span></span>](xref:microsoft.quantum.install.standalone)  |<br> [<span data-ttu-id="e17ef-131">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-131">Install</span></span>](xref:microsoft.quantum.install.jupyter) |<br>[<span data-ttu-id="e17ef-132">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-132">Install</span></span>](xref:microsoft.quantum.install.standalone)|
|<span data-ttu-id="e17ef-133">**Q#  および Python**</span><span class="sxs-lookup"><span data-stu-id="e17ef-133">**Q#  and Python**</span></span> |[<span data-ttu-id="e17ef-134">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-134">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="e17ef-135">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-135">Install</span></span>](xref:microsoft.quantum.install.python) |[<span data-ttu-id="e17ef-136">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-136">Install</span></span>](xref:microsoft.quantum.install.jupyter) |[<span data-ttu-id="e17ef-137">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-137">Install</span></span>](xref:microsoft.quantum.install.python) |
|<span data-ttu-id="e17ef-138">**Q# および .NET (C#、F#)**</span><span class="sxs-lookup"><span data-stu-id="e17ef-138">**Q# and .NET (C#, F#)**</span></span>|[<span data-ttu-id="e17ef-139">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-139">Install</span></span>](xref:microsoft.quantum.install.cs) |[<span data-ttu-id="e17ef-140">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-140">Install</span></span>](xref:microsoft.quantum.install.cs)|<span data-ttu-id="e17ef-141">&#10006;</span><span class="sxs-lookup"><span data-stu-id="e17ef-141">&#10006;</span></span> |[<span data-ttu-id="e17ef-142">インストール</span><span class="sxs-lookup"><span data-stu-id="e17ef-142">Install</span></span>](xref:microsoft.quantum.install.cs) |

## <a name="use-the-qdk-online"></a><span data-ttu-id="e17ef-143">QDK をオンラインで使用する</span><span class="sxs-lookup"><span data-stu-id="e17ef-143">Use the QDK Online</span></span>

<span data-ttu-id="e17ef-144">また、これらのオプションを使用して、ローカルに何もインストールせずに Q# コードを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-144">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="e17ef-145">リソース</span><span class="sxs-lookup"><span data-stu-id="e17ef-145">Resource</span></span>|<span data-ttu-id="e17ef-146">長所</span><span class="sxs-lookup"><span data-stu-id="e17ef-146">Advantages</span></span>|<span data-ttu-id="e17ef-147">制限事項</span><span class="sxs-lookup"><span data-stu-id="e17ef-147">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="e17ef-148">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="e17ef-148">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="e17ef-149">充実したオンライン開発環境</span><span class="sxs-lookup"><span data-stu-id="e17ef-149">A rich online development environment</span></span>  |<span data-ttu-id="e17ef-150">Azure サブスクリプションとプランが必要</span><span class="sxs-lookup"><span data-stu-id="e17ef-150">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="e17ef-151">**Binder**</span><span class="sxs-lookup"><span data-stu-id="e17ef-151">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="e17ef-152">無料のオンライン ノートブック エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="e17ef-152">Free online notebook experience</span></span> |<span data-ttu-id="e17ef-153">永続化なし</span><span class="sxs-lookup"><span data-stu-id="e17ef-153">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="e17ef-154">Docker で QDK を使用する</span><span class="sxs-lookup"><span data-stu-id="e17ef-154">Use the QDK with Docker</span></span>

<span data-ttu-id="e17ef-155">QDK の Docker イメージは、ローカルの Docker イ ンストールで使用することも、ACI など Docker イメージをサポートする任意のサービスを介してクラウドで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-155">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="e17ef-156">https://github.com/microsoft/iqsharp/#using-iq-as-a-container から IQ# Docker イメージをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-156">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="e17ef-157">Docker を Visual Studio Code リモート開発コンテナーと共に使用して、開発環境を迅速に定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="e17ef-157">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="e17ef-158">VS Code 開発コンテナーの詳細については、「 https://github.com/microsoft/Quantum/tree/master/.devcontainer 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e17ef-158">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e17ef-159">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e17ef-159">Next steps</span></span>

<span data-ttu-id="e17ef-160">これらの各セットアップのワークフローの説明および比較については、「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e17ef-160">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
