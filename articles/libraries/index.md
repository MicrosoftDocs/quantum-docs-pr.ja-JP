---
title: Quantum 開発キット ライブラリ | Microsoft Docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 7b51945a8aaf937856441cdb10e8a024bf816f88
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442433"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="8a6d7-102">Q# ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="8a6d7-102">Overview of Q# Libraries</span></span>
<span data-ttu-id="8a6d7-103">Quantum 開発キットには、Q# で量子アプリケーションを簡単に開発するためのいくつかのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-103">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="8a6d7-104">ドキュメントのこのセクションでは、そのライブラリと、それらをプログラムで使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-104">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="8a6d7-105">[**標準ライブラリ**](xref:microsoft.quantum.libraries.standard.intro): このセクションでは、Q# のプログラムとターゲット コンピューターの間のインターフェイスを定義する導入部、規範、Q# のプログラムの記述で使用する汎用的な操作と関数を提供する Q# ライブラリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-105">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="8a6d7-106">[**量子化学ライブラリ**](xref:microsoft.quantum.chemistry.concepts.intro): このセクションでは、量子化学ライブラリについて説明します。このライブラリは、フェルミオンのハミルトニアンの表記を読み込むデータ モデルと、その表記に作用する量子シミュレーションの操作と関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-106">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="8a6d7-107">[**量子数値ライブラリ**](xref:microsoft.quantum.numerics.intro): このセクションでは、数学関数のホストに対する実装を提供する、量子数値ライブラリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-107">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="8a6d7-108">整数 (符号付きと符号なし) と固定小数点表記がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-108">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="8a6d7-109">ライブラリのソースとコード サンプルは、GitHub から入手できます。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-109">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="8a6d7-110">詳細については、「[licensing](xref:microsoft.quantum.libraries.licensing)」(ライセンス) のセクションも参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-110">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="8a6d7-111">プロジェクトにライブラリを追加する別の方法を提供するライブラリについては、パッケージ参照 ("バイナリ") も使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-111">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="8a6d7-112">これを取得するには [NuGet](https://nuget.org) を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="8a6d7-112">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>  