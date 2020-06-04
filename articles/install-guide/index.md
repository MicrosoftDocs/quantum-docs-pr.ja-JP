---
title: Microsoft Quantum Development Kit (QDK) のインストール
description: さまざまな環境の Microsoft Quantum Development Kit をインストールする方法。
author: natke
ms.author: nakersha
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: a5230f506bce02c331d22d6a428b3bd92052bbd4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327571"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="567dd-103">Microsoft Quantum Development Kit (QDK) のインストール</span><span class="sxs-lookup"><span data-stu-id="567dd-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="567dd-104">Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="567dd-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="567dd-105">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="567dd-105">The QDK consists of:</span></span>

- <span data-ttu-id="567dd-106">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="567dd-106">The Q# programming language</span></span>
- <span data-ttu-id="567dd-107">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="567dd-107">A set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="567dd-108">Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)</span><span class="sxs-lookup"><span data-stu-id="567dd-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="567dd-109">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="567dd-109">Tools to facilitate your development</span></span>

<span data-ttu-id="567dd-110">Q# プログラムは、Visual Studio Code または Visual Studio を使用するか、IQ# Jupyter カーネルを持つ Jupyter Notebook を使用して、スタンドアロン アプリケーションとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="567dd-110">Q# programs can run as standalone applications using Visual Studio Code or Visual Studio, or through Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="567dd-111">また、.NET 言語 (通常は C#) または Python で記述されたホスト プログラムと組み合わせて使用することもできます。これにより、従来のプログラム内からクォンタム操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="567dd-111">They can also be paired with a host program written in a .NET language (typically C#) or Python, enabling you to call quantum operations from inside a classical program.</span></span>

<span data-ttu-id="567dd-112">QDK は、複数の開発環境用に使用できます。</span><span class="sxs-lookup"><span data-stu-id="567dd-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="567dd-113">希望するセットアップを選択してください:</span><span class="sxs-lookup"><span data-stu-id="567dd-113">Select your preferred setup from:</span></span>

<span data-ttu-id="567dd-114">[Q# コマンド ライン アプリケーションを使用した開発](xref:microsoft.quantum.install.standalone) - コマンド ラインから Q# を操作する場合は、この方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="567dd-114">[Develop with Q# command line applications](xref:microsoft.quantum.install.standalone) - Choose this approach to work with Q# from the command line.</span></span> <span data-ttu-id="567dd-115">これには、次のオプションのようなドライバーやホスト プログラムは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567dd-115">This does not require a driver or a host program like the below options.</span></span>

<span data-ttu-id="567dd-116">[Q# Jupyter Notebook を使用した開発](xref:microsoft.quantum.install.jupyter) - テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="567dd-116">[Develop with Q# Jupyter Notebooks](xref:microsoft.quantum.install.jupyter) - Select this environment to run Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 

<span data-ttu-id="567dd-117">[Q# と Python を使用した開発](xref:microsoft.quantum.install.python) - Python と Q# を組み合わせて、Q# 操作を呼び出す Python ホスト プログラムを作成できます。</span><span class="sxs-lookup"><span data-stu-id="567dd-117">[Develop with Q# and Python](xref:microsoft.quantum.install.python) - Enables you to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>

<span data-ttu-id="567dd-118">[Q# と .NET を使用した開発](xref:microsoft.quantum.install.cs) - C#、F#、または VB.NET と Q# を組み合わせて、Q# 操作を呼び出す .NET ホスト プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="567dd-118">[Develop with Q# and .NET](xref:microsoft.quantum.install.cs) - Combine C#, F#, or VB.NET with Q# to create a .NET host program that calls Q# operations.</span></span>
