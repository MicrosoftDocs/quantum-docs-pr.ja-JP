---
title: Quantum 開発キット ライブラリ
description: Microsoft Quantum 開発キットに含まれる標準、化学、数値の各ライブラリの概要。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 09fc723d27f2e026430b358c62b817c106c135c2
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871503"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="9a00a-103">Q# ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="9a00a-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="9a00a-104">Quantum 開発キットには、Q# で量子アプリケーションを簡単に開発するためのいくつかのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9a00a-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="9a00a-105">ドキュメントのこのセクションでは、そのライブラリと、それらをプログラムで使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9a00a-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="9a00a-106">[**標準ライブラリ**](xref:microsoft.quantum.libraries.standard.intro): このセクションでは、Q# のプログラムとターゲット コンピューターの間のインターフェイスを定義する導入部、規範、Q# のプログラムの記述で使用する汎用的な操作と関数を提供する Q# ライブラリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9a00a-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="9a00a-107">[**量子化学ライブラリ**](xref:microsoft.quantum.chemistry.concepts.intro): このセクションでは、量子化学ライブラリについて説明します。このライブラリは、フェルミオンのハミルトニアンの表記を読み込むデータ モデルと、その表記に作用する量子シミュレーションの操作と関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="9a00a-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="9a00a-108">[**量子数値ライブラリ**](xref:microsoft.quantum.numerics.intro): このセクションでは、数学関数のホストに対する実装を提供する、量子数値ライブラリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9a00a-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="9a00a-109">整数 (符号付きと符号なし) と固定小数点表記がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9a00a-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="9a00a-110">[**量子機械学習ライブラリ**](xref:microsoft.quantum.machine-learning.concepts.intro):このセクションでは、量子機械学習ライブラリについて説明します。これは、量子コンピューティングを利用してデータを理解するためのシーケンシャル分類器の実装を提供します。</span><span class="sxs-lookup"><span data-stu-id="9a00a-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="9a00a-111">ライブラリのソースとコード サンプルは、GitHub から入手できます。</span><span class="sxs-lookup"><span data-stu-id="9a00a-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="9a00a-112">詳細については、[ライセンス](xref:microsoft.quantum.libraries.licensing)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a00a-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="9a00a-113">ライブラリについては、パッケージ参照 ("バイナリ") も使用でき、プロジェクトにライブラリを含めるための別の手段が用意されています。</span><span class="sxs-lookup"><span data-stu-id="9a00a-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="9a00a-114">これを取得するには [NuGet](https://nuget.org) を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="9a00a-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
