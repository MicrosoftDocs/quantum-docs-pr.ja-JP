---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: Extendedグリーン Atestcommon区分 Sorl 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: abbbd367859952180f181a245ca0754646529b18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210711"
---
# <a name="extendedgreatestcommondivisorl-function"></a><span data-ttu-id="aa6e2-102">Extendedグリーン Atestcommon区分 Sorl 関数</span><span class="sxs-lookup"><span data-stu-id="aa6e2-102">ExtendedGreatestCommonDivisorL function</span></span>

<span data-ttu-id="aa6e2-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="aa6e2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="aa6e2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa6e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa6e2-105">$U \ cdot a + v/cdot b = \ 演算子 name{gcd} (a, b) $ のようなタプル $ (u, v) $ を計算します。 $-演算子名 {gcd} $ は、$a $ および $b $ の最も一般的な除数 $a です。</span><span class="sxs-lookup"><span data-stu-id="aa6e2-105">Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$.</span></span> <span data-ttu-id="aa6e2-106">GCD は常に正の数値です。</span><span class="sxs-lookup"><span data-stu-id="aa6e2-106">The GCD is always positive.</span></span>

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="aa6e2-107">入力</span><span class="sxs-lookup"><span data-stu-id="aa6e2-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="aa6e2-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aa6e2-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aa6e2-109">拡張された最も一般的な除数の計算対象となる最初の数値</span><span class="sxs-lookup"><span data-stu-id="aa6e2-109">the first number of which extended greatest common divisor is being computed</span></span>


### <a name="b--bigint"></a><span data-ttu-id="aa6e2-110">b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="aa6e2-110">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="aa6e2-111">拡張された最も一般的な除数が計算されている2番目の数値</span><span class="sxs-lookup"><span data-stu-id="aa6e2-111">the second number of which extended greatest common divisor is being computed</span></span>



## <a name="output--bigintbigint"></a><span data-ttu-id="aa6e2-112">出力: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="aa6e2-112">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>

<span data-ttu-id="aa6e2-113">タプル $ (u, v) $ とプロパティ $u \ cdot a + v \ cdot b = \ 演算子 name{gcd} (a, b) $。</span><span class="sxs-lookup"><span data-stu-id="aa6e2-113">Tuple $(u,v)$ with the property $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$.</span></span>

## <a name="references"></a><span data-ttu-id="aa6e2-114">リファレンス</span><span class="sxs-lookup"><span data-stu-id="aa6e2-114">References</span></span>

- <span data-ttu-id="aa6e2-115">この実装は次のものに従っています。 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span><span class="sxs-lookup"><span data-stu-id="aa6e2-115">This implementation is according to https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm</span></span>