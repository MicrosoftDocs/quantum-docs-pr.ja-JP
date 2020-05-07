---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
description: C#、Python、および Jupyter Notebook 環境用の Microsoft Quantum 開発キットのインストール方法。
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680188"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="ab0cf-103">Microsoft Quantum Development Kit (QDK) のインストール</span><span class="sxs-lookup"><span data-stu-id="ab0cf-103">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="ab0cf-104">Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-104">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="ab0cf-105">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-105">The QDK consists of:</span></span>

- <span data-ttu-id="ab0cf-106">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="ab0cf-106">the Q# programming language</span></span>
- <span data-ttu-id="ab0cf-107">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="ab0cf-107">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="ab0cf-108">Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)</span><span class="sxs-lookup"><span data-stu-id="ab0cf-108">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="ab0cf-109">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="ab0cf-109">tools to facilitate your development</span></span>

<span data-ttu-id="ab0cf-110">Q# プログラムは、多くの場合、.NET 言語 (通常 C#) または Python で記述されたホスト プログラムとペアになります。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-110">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="ab0cf-111">これにより、従来のプログラム内から量子演算を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-111">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="ab0cf-112">さらに、QDK では、Jupyter Notebook と IQ# Jupyter カーネル用に Q# サポートも提供されます。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-112">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="ab0cf-113">QDK は、複数の開発環境用に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-113">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="ab0cf-114">以下のセクションからお好みの設定を選択してください。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-114">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="ab0cf-115">[Q# コマンド ライン アプリケーション:](xref:microsoft.quantum.install.standalone) コマンド ラインから Q# を操作する場合は、この方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-115">[Q# command line application:](xref:microsoft.quantum.install.standalone) choose this approach if you want to work with Q# from the command line.</span></span> <span data-ttu-id="ab0cf-116">これには、次のオプションのようなドライバーやホスト プログラムは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-116">This does not require a driver or a host program like the below options.</span></span>
- <span data-ttu-id="ab0cf-117">[[Install Q# for Jupyter Notebooks]\(Jupyter Notebook 用 Q# のインストール\):](xref:microsoft.quantum.install.jupyter) テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-117">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> 
- <span data-ttu-id="ab0cf-118">[Q# と Python を使用した開発:](xref:microsoft.quantum.install.python) Python と Q# を組み合わせて、Q# 操作を呼び出す Python ホスト プログラムを作成する場合。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-118">[Develop with Q# and Python:](xref:microsoft.quantum.install.python) if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="ab0cf-119">[Q# と C# または F# を使用した開発:](xref:microsoft.quantum.install.cs) C# または F# と Q# を組み合わせて Q# 操作を呼び出す .NET ホスト プログラムを作成する場合。</span><span class="sxs-lookup"><span data-stu-id="ab0cf-119">[Develop with Q# and C# or F#:](xref:microsoft.quantum.install.cs) if you want to combine C# or F# and Q# to create a .NET host program that calls Q# operations.</span></span>
