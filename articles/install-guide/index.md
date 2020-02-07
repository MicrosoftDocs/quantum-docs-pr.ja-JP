---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 0e9dd1c74316eeb1fa7bbbf657d2e78231ee4294
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036510"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a><span data-ttu-id="0d672-102">Microsoft Quantum Development Kit (QDK) のインストール</span><span class="sxs-lookup"><span data-stu-id="0d672-102">Install the Microsoft Quantum Development Kit (QDK)</span></span>

<span data-ttu-id="0d672-103">Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。</span><span class="sxs-lookup"><span data-stu-id="0d672-103">Learn how to install the Microsoft Quantum Development Kit (QDK), so that you can get started with quantum programming.</span></span> <span data-ttu-id="0d672-104">QDK は次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="0d672-104">The QDK consists of:</span></span>

- <span data-ttu-id="0d672-105">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="0d672-105">the Q# programming language</span></span>
- <span data-ttu-id="0d672-106">Q# の複雑な機能を抽象化するライブラリのセット</span><span class="sxs-lookup"><span data-stu-id="0d672-106">a set of libraries that abstract complex functionality in Q#</span></span>
- <span data-ttu-id="0d672-107">Python および .NET 言語用 API (C#、F#、VB.NET) (Q# で記述された量子プログラムの実行用)</span><span class="sxs-lookup"><span data-stu-id="0d672-107">APIs for Python and .NET languages (C#, F#, and VB.NET) for running quantum programs written in Q#</span></span>
- <span data-ttu-id="0d672-108">開発を容易にするツール</span><span class="sxs-lookup"><span data-stu-id="0d672-108">tools to facilitate your development</span></span>

<span data-ttu-id="0d672-109">Q# プログラムは、多くの場合、.NET 言語 (通常 C#) または Python で記述されたホスト プログラムとペアになります。</span><span class="sxs-lookup"><span data-stu-id="0d672-109">Q# programs are often paired with a host program written in a .NET language (typically C#) or Python.</span></span> <span data-ttu-id="0d672-110">これにより、従来のプログラム内から量子演算を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0d672-110">This allows us to call quantum operations from inside a classical program.</span></span>
<span data-ttu-id="0d672-111">さらに、QDK では、Jupyter Notebook と IQ# Jupyter カーネル用に Q# サポートも提供されます。</span><span class="sxs-lookup"><span data-stu-id="0d672-111">In addition, the QDK provides Q# support for Jupyter Notebooks with the IQ# Jupyter kernel.</span></span>

<span data-ttu-id="0d672-112">QDK は、複数の開発環境用に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0d672-112">The QDK is available for multiple development environments.</span></span> <span data-ttu-id="0d672-113">以下のセクションからお好みの設定を選択してください。</span><span class="sxs-lookup"><span data-stu-id="0d672-113">Select your preferred setup from the sections below:</span></span>

- <span data-ttu-id="0d672-114">[[Install Q# for C#]\(C# 用 Q# のインストール\):](xref:microsoft.quantum.install.cs) C# と Q# を組み合わせて、Q# 操作を呼び出す C# ホスト プログラムを作成する場合は、この環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d672-114">[Install Q# for C#:](xref:microsoft.quantum.install.cs) choose this environment if you want to combine C# and Q# to create a C# host program that calls Q# operations.</span></span>
- <span data-ttu-id="0d672-115">[[Install Q# for Python]\(Python 用 Q# のインストール\):](xref:microsoft.quantum.install.python) Python と Q# を組み合わせて、Q# 操作を呼び出す C# ホスト プログラムを作成する場合は、この環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d672-115">[Install Q# for Python:](xref:microsoft.quantum.install.python) choose this environment if you want to combine Python and Q# to create a Python host program that calls Q# operations.</span></span>
- <span data-ttu-id="0d672-116">[[Install Q# for Jupyter Notebooks]\(Jupyter Notebook 用 Q# のインストール\):](xref:microsoft.quantum.install.jupyter) テキストが埋め込まれたセル内で Q# コードを実行するか、量子コンピューティングの対話型チュートリアルを作成する場合は、この環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="0d672-116">[Install Q# for Jupyter Notebooks:](xref:microsoft.quantum.install.jupyter) choose this environment to execute Q# code in cells with embedded text or create quantum computing interactive tutorials.</span></span> <span data-ttu-id="0d672-117">Q # と外部の従来のホスト プログラムを組み合わせる場合は、この環境を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="0d672-117">Do not choose this environment if you want to combine Q# with an external classical host program.</span></span>
