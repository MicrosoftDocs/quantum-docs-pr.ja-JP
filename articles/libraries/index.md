---
title: Quantum 開発キット ライブラリ
description: Microsoft Quantum 開発キットに含まれる標準、化学、数値の各ライブラリの概要。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
ms.openlocfilehash: 89612aaa5c11e1a5e0d418256e96366953fdd3fe
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906408"
---
# <a name="overview-of-q-libraries"></a><span data-ttu-id="ee54c-103">Q# ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="ee54c-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="ee54c-104">Quantum 開発キットには、Q# で量子アプリケーションを簡単に開発するためのいくつかのライブラリが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ee54c-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="ee54c-105">ドキュメントのこのセクションでは、そのライブラリと、それらをプログラムで使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54c-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="ee54c-106">[**標準ライブラリ**](xref:microsoft.quantum.libraries.standard.intro): このセクションでは、Q# のプログラムとターゲット コンピューターの間のインターフェイスを定義する導入部、規範、Q# のプログラムの記述で使用する汎用的な操作と関数を提供する Q# ライブラリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54c-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="ee54c-107">[**量子化学ライブラリ**](xref:microsoft.quantum.chemistry.concepts.intro): このセクションでは、量子化学ライブラリについて説明します。このライブラリは、フェルミオンのハミルトニアンの表記を読み込むデータ モデルと、その表記に作用する量子シミュレーションの操作と関数を提供します。</span><span class="sxs-lookup"><span data-stu-id="ee54c-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="ee54c-108">[**量子数値ライブラリ**](xref:microsoft.quantum.numerics.intro): このセクションでは、数学関数のホストに対する実装を提供する、量子数値ライブラリについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ee54c-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="ee54c-109">整数 (符号付きと符号なし) と固定小数点表記がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ee54c-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>

<span data-ttu-id="ee54c-110">ライブラリのソースとコード サンプルは、GitHub から入手できます。</span><span class="sxs-lookup"><span data-stu-id="ee54c-110">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span> <span data-ttu-id="ee54c-111">詳細については、「[licensing](xref:microsoft.quantum.libraries.licensing)」(ライセンス) のセクションも参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee54c-111">See also the [licensing](xref:microsoft.quantum.libraries.licensing) section for further information.</span></span> <span data-ttu-id="ee54c-112">プロジェクトにライブラリを追加する別の方法を提供するライブラリについては、パッケージ参照 ("バイナリ") も使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee54c-112">It should be noted that package references ("binaries") are available also for the libraries which offers another way of including the libraries in projects.</span></span> <span data-ttu-id="ee54c-113">これを取得するには [NuGet](https://nuget.org) を使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="ee54c-113">A convenient way of obtaining them is via [nuget](https://nuget.org).</span></span>
