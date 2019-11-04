---
title: 数値ライブラリを使用する |Microsoft Docs
description: 数値ライブラリの使用
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 332781a4356015461426ee7640fd931a41450367
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184612"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="eafab-103">数値ライブラリの使用</span><span class="sxs-lookup"><span data-stu-id="eafab-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="eafab-104">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="eafab-104">Overview</span></span>

<span data-ttu-id="eafab-105">数値ライブラリは3つのコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="eafab-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="eafab-106">整数の加算と比較子を使用した**基本的な整数算術演算**</span><span class="sxs-lookup"><span data-stu-id="eafab-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="eafab-107">基本機能の上に構築された**高レベルの整数機能**。これには、乗算、除算、逆転などが含まれます。 符号付き整数と符号なし整数の場合。</span><span class="sxs-lookup"><span data-stu-id="eafab-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="eafab-108">固定小数点の初期化、加算、乗算、逆数、多項式評価、および測定を使用した**固定小数点演算機能**。</span><span class="sxs-lookup"><span data-stu-id="eafab-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="eafab-109">これらのコンポーネントはすべて、1つの `open` ステートメントを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="eafab-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="eafab-110">型</span><span class="sxs-lookup"><span data-stu-id="eafab-110">Types</span></span>

<span data-ttu-id="eafab-111">数値ライブラリでは、次の型がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="eafab-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="eafab-112">**`LittleEndian`** : `qArr[0]` が最下位ビットを表している整数を表す qubit 配列 `qArr : Qubit[]`。</span><span class="sxs-lookup"><span data-stu-id="eafab-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="eafab-113">**`SignedLittleEndian`** : 2 の補数に格納されている符号付き整数を表す点を除いて、`LittleEndian` と同じです。</span><span class="sxs-lookup"><span data-stu-id="eafab-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="eafab-114">**`FixedPoint`** : qubit 配列 `qArr2 : Qubit[]` とバイナリポイント位置 `pos`で構成される実数を表します。これは、バイナリポイントの左側にあるバイナリの桁数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="eafab-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="eafab-115">`qArr2` は `SignedLittleEndian`と同じ方法で格納されます。</span><span class="sxs-lookup"><span data-stu-id="eafab-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="eafab-116">Operations</span><span class="sxs-lookup"><span data-stu-id="eafab-116">Operations</span></span>

<span data-ttu-id="eafab-117">上記の3種類のそれぞれに対して、さまざまな操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="eafab-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="eafab-118">加算</span><span class="sxs-lookup"><span data-stu-id="eafab-118">Addition</span></span>
    - <span data-ttu-id="eafab-119">比較</span><span class="sxs-lookup"><span data-stu-id="eafab-119">Comparison</span></span>
    - <span data-ttu-id="eafab-120">乗算</span><span class="sxs-lookup"><span data-stu-id="eafab-120">Multiplication</span></span>
    - <span data-ttu-id="eafab-121">2乗</span><span class="sxs-lookup"><span data-stu-id="eafab-121">Squaring</span></span>
    - <span data-ttu-id="eafab-122">除算 (剰余あり)</span><span class="sxs-lookup"><span data-stu-id="eafab-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="eafab-123">加算</span><span class="sxs-lookup"><span data-stu-id="eafab-123">Addition</span></span>
    - <span data-ttu-id="eafab-124">比較</span><span class="sxs-lookup"><span data-stu-id="eafab-124">Comparison</span></span>
    - <span data-ttu-id="eafab-125">剰余2の補数を反転する</span><span class="sxs-lookup"><span data-stu-id="eafab-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="eafab-126">乗算</span><span class="sxs-lookup"><span data-stu-id="eafab-126">Multiplication</span></span>
    - <span data-ttu-id="eafab-127">2乗</span><span class="sxs-lookup"><span data-stu-id="eafab-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="eafab-128">従来の値への準備/初期化</span><span class="sxs-lookup"><span data-stu-id="eafab-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="eafab-129">加算 (古典定数またはその他のクォンタム固定ポイント)</span><span class="sxs-lookup"><span data-stu-id="eafab-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="eafab-130">比較</span><span class="sxs-lookup"><span data-stu-id="eafab-130">Comparison</span></span>
    - <span data-ttu-id="eafab-131">乗算</span><span class="sxs-lookup"><span data-stu-id="eafab-131">Multiplication</span></span>
    - <span data-ttu-id="eafab-132">2乗</span><span class="sxs-lookup"><span data-stu-id="eafab-132">Squaring</span></span>
    - <span data-ttu-id="eafab-133">偶数関数と奇数関数の特殊化による多項式評価</span><span class="sxs-lookup"><span data-stu-id="eafab-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="eafab-134">逆数 (1/x)</span><span class="sxs-lookup"><span data-stu-id="eafab-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="eafab-135">測定 (古典 Double)</span><span class="sxs-lookup"><span data-stu-id="eafab-135">Measurement (classical Double)</span></span>

<span data-ttu-id="eafab-136">これらの各操作の詳細と詳細なドキュメントについては、 [docs.microsoft.com](https://docs.microsoft.com/en-us/quantum)の Q # ライブラリリファレンスドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eafab-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/en-us/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="eafab-137">サンプル: 整数加算</span><span class="sxs-lookup"><span data-stu-id="eafab-137">Sample: Integer addition</span></span>

<span data-ttu-id="eafab-138">基本的な例として、$ $ \ket x\ket y\ket x\ket {x + y} $ $ という演算を考えてみます。これは、n-qubit 整数 $x $、n または (n + 1)-qubit レジスタ $y $ を入力として使用し、後者は sum $ (x + y) $ にマップします。</span><span class="sxs-lookup"><span data-stu-id="eafab-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="eafab-139">$Y $ が $n $ bit レジスタに格納されている場合は、合計が $ 2 ^ n $ として計算されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eafab-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="eafab-140">この操作は、Quantum Development Kit を使用して次のように適用できます。</span><span class="sxs-lookup"><span data-stu-id="eafab-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation MyAdditionTest (xInt : Int, yInt : Int, n : Int) : Unit
{
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xInt, x); // initialize values
        ApplyXorInPlace(yInt, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="eafab-141">サンプル: smooth functions の評価</span><span class="sxs-lookup"><span data-stu-id="eafab-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="eafab-142">クォンタム $x コンピューターで $ \ sin (x) $ などの smooth functions を評価するには ($ がクォンタム `FixedPoint` 番号である場合、クォンタム開発キットの数値ライブラリは、操作 `EvaluatePolynomialFxP` と `Evaluate[Even/Odd]PolynomialFxP`を提供します。</span><span class="sxs-lookup"><span data-stu-id="eafab-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="eafab-143">1つ目の `EvaluatePolynomialFxP`では、を使用して、$ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \ cドット + a_dx ^ d, $ $ という形式の多項式を評価できます。ここで、$d $ はその*次数を表し*ます。</span><span class="sxs-lookup"><span data-stu-id="eafab-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="eafab-144">これを行うには、必要なのは多項式係数 `[a_0,..., a_d]` (`Double[]`型)、入力 `x : FixedPoint`、および出力 `y : FixedPoint` (最初はゼロ) だけです。</span><span class="sxs-lookup"><span data-stu-id="eafab-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="eafab-145">結果として $P (x) = 1 + 2x $ が `yFxP`に格納されます。</span><span class="sxs-lookup"><span data-stu-id="eafab-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="eafab-146">2番目、`EvaluateEvenPolynomialFxP`、3番目の `EvaluateOddPolynomialFxP`は、それぞれ偶数関数と奇数関数の場合に特に特殊化されています。</span><span class="sxs-lookup"><span data-stu-id="eafab-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="eafab-147">つまり、偶数/奇数関数 $f (x) $ および $ $ P_ {偶数} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \ cドット + a_d x ^ {2d}, $ $ $f (x) $ は、$P _ {偶数} (x) $ または $P _ {奇数} (x): = xP_ {偶数} (x) $ によって近似されます。4.3.</span><span class="sxs-lookup"><span data-stu-id="eafab-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="eafab-148">Q # では、次の2つのケースを処理できます。</span><span class="sxs-lookup"><span data-stu-id="eafab-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="eafab-149">これは $P _ {偶数} (x) = 1 + 2 ^ 2 $、およびを評価します。</span><span class="sxs-lookup"><span data-stu-id="eafab-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], xFxP, yFxP);
```
<span data-ttu-id="eafab-150">これは $P _ {奇数} (x) = x + 2x ^ 3 $ と評価されます。</span><span class="sxs-lookup"><span data-stu-id="eafab-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="eafab-151">その他のサンプル</span><span class="sxs-lookup"><span data-stu-id="eafab-151">More samples</span></span>

<span data-ttu-id="eafab-152">その他のサンプルについては、[メインサンプルリポジトリ](https://github.com/Microsoft/Quantum)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eafab-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="eafab-153">まず、リポジトリを複製し、`Numerics` サブフォルダーを開きます。</span><span class="sxs-lookup"><span data-stu-id="eafab-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

<span data-ttu-id="eafab-154">次に、いずれかのサンプルフォルダーに `cd` し、を使用してサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="eafab-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
