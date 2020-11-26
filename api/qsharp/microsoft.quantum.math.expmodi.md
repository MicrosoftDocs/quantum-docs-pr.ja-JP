---
uid: Microsoft.Quantum.Math.ExpModI
title: Modi 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228492"
---
# <a name="expmodi-function"></a><span data-ttu-id="97906-102">Modi 関数</span><span class="sxs-lookup"><span data-stu-id="97906-102">ExpModI function</span></span>

<span data-ttu-id="97906-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="97906-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="97906-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97906-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97906-105">指定された剰余に関して、指定された指数で累乗された整数を返します。</span><span class="sxs-lookup"><span data-stu-id="97906-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="97906-106">説明</span><span class="sxs-lookup"><span data-stu-id="97906-106">Description</span></span>

<span data-ttu-id="97906-107">$ $X ドルで底を示し、$ と $p を $N $ で累乗してみましょう。</span><span class="sxs-lookup"><span data-stu-id="97906-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="97906-108">関数は $x ^ p/演算子名 {mod} N $ を返します。</span><span class="sxs-lookup"><span data-stu-id="97906-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="97906-109">$N $, $x $ は正の値で、累乗は負ではないと想定しています。</span><span class="sxs-lookup"><span data-stu-id="97906-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="97906-110">入力</span><span class="sxs-lookup"><span data-stu-id="97906-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="97906-111">底: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97906-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="97906-112">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97906-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="97906-113">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97906-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="97906-114">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97906-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="97906-115">解説</span><span class="sxs-lookup"><span data-stu-id="97906-115">Remarks</span></span>

<span data-ttu-id="97906-116">は、ではなく、のビット数に比例 `power` `power` します。</span><span class="sxs-lookup"><span data-stu-id="97906-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>