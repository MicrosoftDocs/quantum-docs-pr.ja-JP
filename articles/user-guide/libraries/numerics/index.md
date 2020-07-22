---
title: 量子数値ライブラリの概要 | Microsoft Docs
description: 量子数値ライブラリの概要
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
ms.openlocfilehash: 9552f3683e1df8cb10d19d0b3f85223df056f83d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871350"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="a5115-103">量子数値ライブラリの概要</span><span class="sxs-lookup"><span data-stu-id="a5115-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="a5115-104">多くの量子アルゴリズムは、入力の重ね合わせに対して数学関数を評価する[オラクル](xref:microsoft.quantum.concepts.oracles)に依存しています。</span><span class="sxs-lookup"><span data-stu-id="a5115-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="a5115-105">たとえば、Shor のアルゴリズムの主要なコンポーネントは、固定 $a$ に対して $f(x) = a^x\operatorname{mod} N$ を、数値を因数 $N$ に対して、$x$ a $2n$-qubit 整数を均一の重ね合わせですべての $2n$-bit 文字列に対して、評価します。</span><span class="sxs-lookup"><span data-stu-id="a5115-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="a5115-106">実際の量子コンピューターで Shor のアルゴリズムを実行するには、ターゲット マシンのネイティブ操作に関してこの関数を記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5115-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="a5115-107">最下位ビットから数えて $i$ 番目のビットを示す $x_i$ とともに $x$ のバイナリ表現を使用すると、$f(x)$ は $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$ として記述できます。</span><span class="sxs-lookup"><span data-stu-id="a5115-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="a5115-108">次に、これは項 $a^{2^i x_i}=(a^{2^i})^{x_i}$ の積 (mod N) として記述できます。</span><span class="sxs-lookup"><span data-stu-id="a5115-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="a5115-109">したがって、関数 $f(x)$ は、$x_i$ がゼロ以外であることを条件として 2n$ (モジュラー) の $a^{2^i}$ による乗算の連続を使用して実装できます。</span><span class="sxs-lookup"><span data-stu-id="a5115-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="a5115-110">定数 $a^{2^i}$ はアルゴリズムの実行前に事前計算し剰余 N を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a5115-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="a5115-111">この一連の制御されたモジュラー乗算は、さらに簡略化できます。各乗算は $n$ 制御されたモジュラー加算のシーケンスを使用して実行できます。また、各モジュラー加算は、通常の加算と比較基準から構築できます。</span><span class="sxs-lookup"><span data-stu-id="a5115-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="a5115-112">実際の実装に到達するために多くの手順が必要なので、最初からこのような機能を使用できるようにすると非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="a5115-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="a5115-113">このため、Quantum Development Kit では、さまざまな数値の機能がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a5115-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="a5115-114">機能</span><span class="sxs-lookup"><span data-stu-id="a5115-114">Functionality</span></span>

<span data-ttu-id="a5115-115">これまでに説明した整数演算以外にも、数値ライブラリでは次の機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="a5115-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

- <span data-ttu-id="a5115-116">1 つまたは 2 つの量子整数値を入力として使用する、符号付き (符号なし) 整数の機能 (乗算、平方、剰余がある除算、反転、...)</span><span class="sxs-lookup"><span data-stu-id="a5115-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
- <span data-ttu-id="a5115-117">1 つまたは 2 つの量子固定小数点数を入力として持つ、固定小数点機能 (加算/減算、乗算、平方、1/x、多項式評価)</span><span class="sxs-lookup"><span data-stu-id="a5115-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="a5115-118">作業の開始</span><span class="sxs-lookup"><span data-stu-id="a5115-118">Getting started</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a5115-119">数値ライブラリの使用方法について確認する</span><span class="sxs-lookup"><span data-stu-id="a5115-119">Learn about using the numerics library</span></span>](xref:microsoft.quantum.numerics.usage)
