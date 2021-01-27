---
title: Microsoft Q# 数値ライブラリの使用
description: Microsoft Quantum の数値ライブラリで使用できる型と操作について説明します。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: 92efd3b8677d2f27bc59f986ce6c9e915cd23652
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856445"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="4a00d-103">数値ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="4a00d-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="4a00d-104">概要</span><span class="sxs-lookup"><span data-stu-id="4a00d-104">Overview</span></span>

<span data-ttu-id="4a00d-105">数値ライブラリは3つのコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="4a00d-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="4a00d-106">整数の加算と比較子を使用した **基本的な整数算術演算**</span><span class="sxs-lookup"><span data-stu-id="4a00d-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="4a00d-107">基本機能の上に構築された **高レベルの整数機能**。これには、乗算、除算、逆転などが含まれます。 符号付き整数と符号なし整数の場合。</span><span class="sxs-lookup"><span data-stu-id="4a00d-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="4a00d-108">固定小数点の初期化、加算、乗算、逆数、多項式評価、および測定を使用した **固定小数点演算機能**。</span><span class="sxs-lookup"><span data-stu-id="4a00d-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="4a00d-109">これらのコンポーネントはすべて、1つのステートメントを使用してアクセスでき `open` ます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="4a00d-110">種類</span><span class="sxs-lookup"><span data-stu-id="4a00d-110">Types</span></span>

<span data-ttu-id="4a00d-111">数値ライブラリでは、次の型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4a00d-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="4a00d-112">**`LittleEndian`**: が最 `qArr : Qubit[]` `qArr[0]` 下位ビットを表している整数を表す qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="4a00d-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="4a00d-113">**`SignedLittleEndian`**: と同じです `LittleEndian` が、2の補数に格納されている符号付き整数を表している点が異なります。</span><span class="sxs-lookup"><span data-stu-id="4a00d-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="4a00d-114">**`FixedPoint`**: Qubit 配列とバイナリポイント位置で構成される実数を表します。この値は、バイナリ `qArr2 : Qubit[]` `pos` ポイントの左側にあるバイナリの桁数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="4a00d-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="4a00d-115">`qArr2` はと同じ方法で格納され `SignedLittleEndian` ます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="4a00d-116">Operations</span><span class="sxs-lookup"><span data-stu-id="4a00d-116">Operations</span></span>

<span data-ttu-id="4a00d-117">上記の3種類のそれぞれに対して、さまざまな操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="4a00d-118">加算</span><span class="sxs-lookup"><span data-stu-id="4a00d-118">Addition</span></span>
    - <span data-ttu-id="4a00d-119">比較</span><span class="sxs-lookup"><span data-stu-id="4a00d-119">Comparison</span></span>
    - <span data-ttu-id="4a00d-120">乗算</span><span class="sxs-lookup"><span data-stu-id="4a00d-120">Multiplication</span></span>
    - <span data-ttu-id="4a00d-121">2乗</span><span class="sxs-lookup"><span data-stu-id="4a00d-121">Squaring</span></span>
    - <span data-ttu-id="4a00d-122">除算 (剰余あり)</span><span class="sxs-lookup"><span data-stu-id="4a00d-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="4a00d-123">加算</span><span class="sxs-lookup"><span data-stu-id="4a00d-123">Addition</span></span>
    - <span data-ttu-id="4a00d-124">比較</span><span class="sxs-lookup"><span data-stu-id="4a00d-124">Comparison</span></span>
    - <span data-ttu-id="4a00d-125">剰余2の補数を反転する</span><span class="sxs-lookup"><span data-stu-id="4a00d-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="4a00d-126">乗算</span><span class="sxs-lookup"><span data-stu-id="4a00d-126">Multiplication</span></span>
    - <span data-ttu-id="4a00d-127">2乗</span><span class="sxs-lookup"><span data-stu-id="4a00d-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="4a00d-128">従来の値への準備/初期化</span><span class="sxs-lookup"><span data-stu-id="4a00d-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="4a00d-129">加算 (古典定数またはその他のクォンタム固定ポイント)</span><span class="sxs-lookup"><span data-stu-id="4a00d-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="4a00d-130">比較</span><span class="sxs-lookup"><span data-stu-id="4a00d-130">Comparison</span></span>
    - <span data-ttu-id="4a00d-131">乗算</span><span class="sxs-lookup"><span data-stu-id="4a00d-131">Multiplication</span></span>
    - <span data-ttu-id="4a00d-132">2乗</span><span class="sxs-lookup"><span data-stu-id="4a00d-132">Squaring</span></span>
    - <span data-ttu-id="4a00d-133">偶数関数と奇数関数の特殊化による多項式評価</span><span class="sxs-lookup"><span data-stu-id="4a00d-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="4a00d-134">逆数 (1/x)</span><span class="sxs-lookup"><span data-stu-id="4a00d-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="4a00d-135">測定 (古典 Double)</span><span class="sxs-lookup"><span data-stu-id="4a00d-135">Measurement (classical Double)</span></span>

<span data-ttu-id="4a00d-136">これらの各操作の詳細と詳細なドキュメントについては、 Q# [docs.microsoft.com](https://docs.microsoft.com/quantum)のライブラリリファレンスドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a00d-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="4a00d-137">サンプル: 整数加算</span><span class="sxs-lookup"><span data-stu-id="4a00d-137">Sample: Integer addition</span></span>

<span data-ttu-id="4a00d-138">基本的な例として、$ $ \ket x\ket y\ket x\ket {x + y} $ $ という演算を考えてみます。これは、n-qubit 整数 $x $、n または (n + 1)-qubit レジスタ $y $ を入力として使用し、後者は sum $ (x + y) $ にマップします。</span><span class="sxs-lookup"><span data-stu-id="4a00d-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="4a00d-139">$Y $ が $n $ bit レジスタに格納されている場合は、合計が $ 2 ^ n $ として計算されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4a00d-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="4a00d-140">この操作は、Quantum Development Kit を使用して次のように適用できます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="4a00d-141">サンプル: smooth functions の評価</span><span class="sxs-lookup"><span data-stu-id="4a00d-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="4a00d-142">クォンタム $x コンピューターで $ \ sin (x) $ などの smooth functions を評価するには ($ がクォンタム番号である)、 `FixedPoint` クォンタム開発キットの数値ライブラリでは、操作 `EvaluatePolynomialFxP` とを提供し `Evaluate[Even/Odd]PolynomialFxP` ます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="4a00d-143">1つ目のは、 `EvaluatePolynomialFxP` $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \ cドット + a_dx ^ d, $ $ という形式の多項式を評価できるようにします。ここで、$d $ は *度* を表します。</span><span class="sxs-lookup"><span data-stu-id="4a00d-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="4a00d-144">これを行うには、必要なのは多項式係数 `[a_0,..., a_d]` (型 `Double[]` )、入力、 `x : FixedPoint` および出力 `y : FixedPoint` (最初はゼロ) だけです。</span><span class="sxs-lookup"><span data-stu-id="4a00d-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="4a00d-145">結果として $P (x) = 1 + 2x $ がに格納され `yFxP` ます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="4a00d-146">2番目の、 `EvaluateEvenPolynomialFxP` 、および3番目のは、 `EvaluateOddPolynomialFxP` それぞれ偶数と奇数の関数の場合に特殊化されています。</span><span class="sxs-lookup"><span data-stu-id="4a00d-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="4a00d-147">つまり、偶数/奇数関数 $f (x) $ および $ $ P_ {偶数} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \ cドット + a_d x ^ {2d}, $ $ $f (x) $ は、_ {偶数} (x) $ または $P _ {奇数} (x): = xcdot P_ {偶数} (x) $ の $P によって、近似されます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="4a00d-148">では、次の Q# 2 つのケースを処理できます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="4a00d-149">これは $P _ {偶数} (x) = 1 + 2 ^ 2 $、およびを評価します。</span><span class="sxs-lookup"><span data-stu-id="4a00d-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="4a00d-150">これは $P _ {奇数} (x) = x + 2x ^ 3 $ と評価されます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="4a00d-151">その他のサンプル</span><span class="sxs-lookup"><span data-stu-id="4a00d-151">More samples</span></span>

<span data-ttu-id="4a00d-152">その他のサンプルについては、 [メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a00d-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="4a00d-153">まず、リポジトリを複製し、 `Numerics` サブフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="4a00d-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

<span data-ttu-id="4a00d-154">次に、の `cd` いずれかのサンプルフォルダーに入力し、を使用してサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a00d-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
