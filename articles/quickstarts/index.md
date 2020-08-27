---
title: Microsoft Quantum Development Kit (QDK) のインストール
description: さまざまな環境の Microsoft Quantum Development Kit をインストールする方法。
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863707"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="4e5ec-103">Microsoft Quantum Development Kit (QDK) のインストール</span><span class="sxs-lookup"><span data-stu-id="4e5ec-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="4e5ec-104">Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="4e5ec-105">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-105">The QDK consists of:</span></span>

- <span data-ttu-id="4e5ec-106">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="4e5ec-106">The Q# programming language</span></span>
- <span data-ttu-id="4e5ec-107">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="4e5ec-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="4e5ec-108">Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)</span><span class="sxs-lookup"><span data-stu-id="4e5ec-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="4e5ec-109">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="4e5ec-109">Tools to facilitate your development</span></span>

<span data-ttu-id="4e5ec-110">Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、スタンドアロン アプリケーションとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>
<span data-ttu-id="4e5ec-111">また、.NET 言語 (通常は C#) または Python で記述されたホスト プログラムと組み合わせて使用することもできます。これにより、従来のプログラム内からクォンタム操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="4e5ec-112">これらの各セットアップのワークフローの説明および比較については、「[Q# プログラムの実行方法](xref:microsoft.quantum.guide.host-programs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-112">The workflows for each of these setups are described and compared at [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

<span data-ttu-id="4e5ec-113">QDK のインストールを続行し、Q# プロジェクトを作成するために、適切なセットアップを選択してください。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-113">To proceed with installing the QDK and creating Q# projects, select your preferred setup:</span></span>

<span data-ttu-id="4e5ec-114">[Q# アプリケーションを使用した開発](xref:microsoft.quantum.install.standalone) - コマンド プロンプトから Q# を操作する場合は、この方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-114">[Develop with Q# applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command prompt.</span></span> <span data-ttu-id="4e5ec-115">これには、次のオプションのようなドライバーやホスト プログラムは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="4e5ec-116">[Q# Jupyter Notebook を使用した開発](xref:microsoft.quantum.install.jupyter) - テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="4e5ec-117">[Q# と Python を使用した開発](xref:microsoft.quantum.install.python) - Python と Q# を組み合わせて、Q# 操作を呼び出す Python ホスト プログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="4e5ec-118">[Q# と .NET を使用した開発](xref:microsoft.quantum.install.cs) - C#、F#、または VB.NET と Q# を組み合わせて、Q# 操作を呼び出す .NET ホスト プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e5ec-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
