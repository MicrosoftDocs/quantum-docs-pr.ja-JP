---
title: Microsoft Quantum 開発キット (QDK) の設定
description: さまざまな環境に合わせて Microsoft Quantum 開発キットを設定する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 5/8/2020
ms.topic: quickstart
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 15067f1762f4468345beee38c98e1b943081fc1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859025"
---
# <a name="setting-up-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="65433-103">Microsoft Quantum 開発キット (QDK) の設定</span><span class="sxs-lookup"><span data-stu-id="65433-103">Setting up the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="65433-104">量子プログラミングを開始できるように、お使いの環境に合わせて Microsoft Quantum 開発キット (QDK) を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65433-104">Learn how to set up the Microsoft Quantum Development Kit (QDK) for your environment, so that you can get started with quantum programming.</span></span> <span data-ttu-id="65433-105">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="65433-105">The QDK consists of:</span></span>

- <span data-ttu-id="65433-106">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="65433-106">The Q# programming language</span></span>
- <span data-ttu-id="65433-107">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="65433-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="65433-108">Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)</span><span class="sxs-lookup"><span data-stu-id="65433-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="65433-109">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="65433-109">Tools to facilitate your development</span></span>

<span data-ttu-id="65433-110">Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、あるいは Python または .NET 言語 (C#、F#) で作成されたホスト プログラムと組み合わせて、スタンドアロン アプリケーションとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="65433-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, through Jupyter Notebooks with the IQ# Jupyter kernel, or paired with a host program written in Python or a .NET language (C#, F#).</span></span> <span data-ttu-id="65433-111">また、[Codespaces](https://online.visualstudio.com/)、[MyBinder.org](https://mybinder.org/)、または [Docker](#use-the-qdk-with-docker) を使用して、Q# プログラムをオンラインで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="65433-111">You can also run Q# programs online using [Codespaces](https://online.visualstudio.com/), [MyBinder.org](https://mybinder.org/), or [Docker](#use-the-qdk-with-docker).</span></span> 

## <a name="options-for-setting-up-the-qdk"></a><span data-ttu-id="65433-112">QDK を設定するためのオプション</span><span class="sxs-lookup"><span data-stu-id="65433-112">Options for setting up the QDK</span></span>

<span data-ttu-id="65433-113">QDK は、次の 3 つの方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="65433-113">You can use the QDK in three ways:</span></span>

- [<span data-ttu-id="65433-114">QDK をローカルにインストールする</span><span class="sxs-lookup"><span data-stu-id="65433-114">Install the QDK locally</span></span>](#install-the-qdk-locally)
- [<span data-ttu-id="65433-115">QDK をオンラインで使用する</span><span class="sxs-lookup"><span data-stu-id="65433-115">Use the QDK online</span></span>](#use-the-qdk-online)
- [<span data-ttu-id="65433-116">QDK Docker イメージを使用する</span><span class="sxs-lookup"><span data-stu-id="65433-116">Use a QDK Docker image</span></span>](#use-the-qdk-with-docker)

## <a name="install-the-qdk-locally"></a><span data-ttu-id="65433-117">QDK をローカルにインストールする</span><span class="sxs-lookup"><span data-stu-id="65433-117">Install the QDK locally</span></span>

<span data-ttu-id="65433-118">ほとんどの使い慣れた IDE で Q# コードを開発できるだけでなく、Python や .NET (C#、F#) などの他の言語と Q# を統合することもできます。</span><span class="sxs-lookup"><span data-stu-id="65433-118">You can develop Q# code in most of your favorites IDEs, as well as integrate Q# with other languages such as Python and .NET (C#, F#).</span></span>

<table>
    <tr>
        <th width=10%>&nbsp;</th>
        <th>&nbsp;</th>
        <th align="center" width=18%><img src="~/media/vs_code.png" alt="VS Code" width="50"/><br><span data-ttu-id="65433-119"><b>VS Code</span><span class="sxs-lookup"><span data-stu-id="65433-119"><b>VS Code</span></span><br><span data-ttu-id="65433-120">(2019 以降)</b></span><span class="sxs-lookup"><span data-stu-id="65433-120">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/vs_studio.png" alt="Visual Studio" width="50"/><br><span data-ttu-id="65433-121"><b>Visual Studio</span><span class="sxs-lookup"><span data-stu-id="65433-121"><b>Visual Studio</span></span><br><span data-ttu-id="65433-122">(2019 以降)</b></span><span class="sxs-lookup"><span data-stu-id="65433-122">(2019 or later)</b></span></span></th>
        <th align="center" width=18%><img src="~/media/jupyter-wht.png" alt="jupyter install" width="65"/><br><span data-ttu-id="65433-123"><b>Jupyter Notebook</b></span><span class="sxs-lookup"><span data-stu-id="65433-123"><b>Jupyter Notebooks</b></span></span></th>
        <th align="center" width=18%><img src="~/media/blank.png" alt="blank spacer" width="65"/><br><span data-ttu-id="65433-124"><b>コマンド ライン</b></span><span class="sxs-lookup"><span data-stu-id="65433-124"><b>Command line</b></span></span></th>
    </tr>
    <tr>
        <th>&nbsp;</th>
        <td align="left"><span data-ttu-id="65433-125"><b>OS のサポート:</b></span><span class="sxs-lookup"><span data-stu-id="65433-125"><b>OS support:</b></span></span></td>
        <td align="center"><span data-ttu-id="65433-126">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="65433-126">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="65433-127">Windows のみ</span><span class="sxs-lookup"><span data-stu-id="65433-127">Windows only</span></span></td>
        <td align="center"><span data-ttu-id="65433-128">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="65433-128">Windows, macOS, Linux</span></span></td>
        <td align="center"><span data-ttu-id="65433-129">Windows、macOS、Linux</span><span class="sxs-lookup"><span data-stu-id="65433-129">Windows, macOS, Linux</span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/quantum-wht.png" alt="QDK" width="60"/></td>
        <td align="left"><span data-ttu-id="65433-130"><b>Q# スタンドアロン</b></span><span class="sxs-lookup"><span data-stu-id="65433-130"><b>Q# standalone</b></span></span></td>
        <td align="center"><span data-ttu-id="65433-131"><a href="xref:microsoft.quantum.install.standalone">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-131"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-132"><a href="xref:microsoft.quantum.install.standalone">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-132"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-133"><a href="xref:microsoft.quantum.install.jupyter">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-133"><a href="xref:microsoft.quantum.install.jupyter">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-134"><a href="xref:microsoft.quantum.install.standalone">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-134"><a href="xref:microsoft.quantum.install.standalone">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/python.png" alt="python install" width="50"/></td>
        <td align="left"><span data-ttu-id="65433-135"><b>Q# および Python</b></span><span class="sxs-lookup"><span data-stu-id="65433-135"><b>Q# and Python</b></span></span></td>
        <td align="center"><span data-ttu-id="65433-136"><a href="xref:microsoft.quantum.install.python">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-136"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-137"><a href="xref:microsoft.quantum.install.python">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-137"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-138"><a href="xref:microsoft.quantum.install.python">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-138"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-139"><a href="xref:microsoft.quantum.install.python">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-139"><a href="xref:microsoft.quantum.install.python">Install</a></span></span></td>
    </tr>
    <tr>
        <td align="right"><img src="~/media/dot_net.png" alt="dotnet install" width="50"/></td>
        <td align="left"><span data-ttu-id="65433-140"><b>Q# および .NET (C#、F#)</b></span><span class="sxs-lookup"><span data-stu-id="65433-140"><b>Q# and .NET (C#, F#)</b></span></span></td> 
        <td align="center"><span data-ttu-id="65433-141"><a href="xref:microsoft.quantum.install.cs">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-141"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-142"><a href="xref:microsoft.quantum.install.cs">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-142"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
        <td align="center"><span data-ttu-id="65433-143">&#10006;</span><span class="sxs-lookup"><span data-stu-id="65433-143">&#10006;</span></span></td>
        <td align="center"><span data-ttu-id="65433-144"><a href="xref:microsoft.quantum.install.cs">インストール</a></span><span class="sxs-lookup"><span data-stu-id="65433-144"><a href="xref:microsoft.quantum.install.cs">Install</a></span></span></td>
   </tr>
</table>

## <a name="use-the-qdk-online"></a><span data-ttu-id="65433-145">QDK をオンラインで使用する</span><span class="sxs-lookup"><span data-stu-id="65433-145">Use the QDK Online</span></span>

<span data-ttu-id="65433-146">また、これらのオプションを使用して、ローカルに何もインストールせずに Q# コードを開発することもできます。</span><span class="sxs-lookup"><span data-stu-id="65433-146">You can also develop Q# code without installing anything locally with these options:</span></span>

|<span data-ttu-id="65433-147">リソース</span><span class="sxs-lookup"><span data-stu-id="65433-147">Resource</span></span>|<span data-ttu-id="65433-148">長所</span><span class="sxs-lookup"><span data-stu-id="65433-148">Advantages</span></span>|<span data-ttu-id="65433-149">制限事項</span><span class="sxs-lookup"><span data-stu-id="65433-149">Limitations</span></span>|
|---|---|---|
|[<span data-ttu-id="65433-150">**Visual Studio Codespaces**</span><span class="sxs-lookup"><span data-stu-id="65433-150">**Visual Studio Codespaces**</span></span>](xref:microsoft.quantum.install.standalone)|<span data-ttu-id="65433-151">充実したオンライン開発環境</span><span class="sxs-lookup"><span data-stu-id="65433-151">A rich online development environment</span></span>  |<span data-ttu-id="65433-152">Azure サブスクリプションとプランが必要</span><span class="sxs-lookup"><span data-stu-id="65433-152">Requires an Azure subscription and plan</span></span> |
|[<span data-ttu-id="65433-153">**Binder**</span><span class="sxs-lookup"><span data-stu-id="65433-153">**Binder**</span></span>](xref:microsoft.quantum.install.binder) | <span data-ttu-id="65433-154">無料のオンライン ノートブック エクスペリエンス</span><span class="sxs-lookup"><span data-stu-id="65433-154">Free online notebook experience</span></span> |<span data-ttu-id="65433-155">永続化なし</span><span class="sxs-lookup"><span data-stu-id="65433-155">No persistence</span></span> |

## <a name="use-the-qdk-with-docker"></a><span data-ttu-id="65433-156">Docker で QDK を使用する</span><span class="sxs-lookup"><span data-stu-id="65433-156">Use the QDK with Docker</span></span>

<span data-ttu-id="65433-157">QDK の Docker イメージは、ローカルの Docker イ ンストールで使用することも、ACI など Docker イメージをサポートする任意のサービスを介してクラウドで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="65433-157">You can use our QDK Docker image in your local Docker installation or in the cloud via any service that supports Docker images, such as ACI.</span></span>

<span data-ttu-id="65433-158"> https://github.com/microsoft/iqsharp/#using-iq-as-a-container から IQ# Docker イメージをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="65433-158">You can download the IQ# Docker image from https://github.com/microsoft/iqsharp/#using-iq-as-a-container.</span></span> 

<span data-ttu-id="65433-159">Docker を Visual Studio Code リモート開発コンテナーと共に使用して、開発環境を迅速に定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="65433-159">You can also use Docker with a Visual Studio Code Remote Development Container to quickly define development environments.</span></span> <span data-ttu-id="65433-160">VS Code 開発コンテナーの詳細については、「 https://github.com/microsoft/Quantum/tree/master/.devcontainer 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65433-160">For more information about VS Code Development Containers, see https://github.com/microsoft/Quantum/tree/master/.devcontainer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="65433-161">次のステップ</span><span class="sxs-lookup"><span data-stu-id="65433-161">Next steps</span></span>

<span data-ttu-id="65433-162">これらの各セットアップのワークフローの説明および比較については、「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65433-162">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>
