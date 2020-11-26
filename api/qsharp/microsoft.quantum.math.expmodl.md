---
uid: Microsoft.Quantum.Math.ExpModL
title: 関数の集計関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210750"
---
# <a name="expmodl-function"></a><span data-ttu-id="a3ab0-102">関数の集計関数</span><span class="sxs-lookup"><span data-stu-id="a3ab0-102">ExpModL function</span></span>

<span data-ttu-id="a3ab0-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="a3ab0-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="a3ab0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a3ab0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a3ab0-105">指定された剰余に関して、指定された指数で累乗された整数を返します。</span><span class="sxs-lookup"><span data-stu-id="a3ab0-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="a3ab0-106">説明</span><span class="sxs-lookup"><span data-stu-id="a3ab0-106">Description</span></span>

<span data-ttu-id="a3ab0-107">$ $X ドルで底を示し、$ と $p を $N $ で累乗してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a3ab0-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="a3ab0-108">関数は $x ^ p/演算子名 {mod} N $ を返します。</span><span class="sxs-lookup"><span data-stu-id="a3ab0-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="a3ab0-109">$N $, $x $ は正の値で、累乗は負ではないと想定しています。</span><span class="sxs-lookup"><span data-stu-id="a3ab0-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="a3ab0-110">入力</span><span class="sxs-lookup"><span data-stu-id="a3ab0-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="a3ab0-111">基本: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3ab0-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="a3ab0-112">power: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3ab0-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="a3ab0-113">剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3ab0-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="a3ab0-114">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="a3ab0-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="a3ab0-115">解説</span><span class="sxs-lookup"><span data-stu-id="a3ab0-115">Remarks</span></span>

<span data-ttu-id="a3ab0-116">は、ではなく、のビット数に比例 `power` `power` します。</span><span class="sxs-lookup"><span data-stu-id="a3ab0-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>