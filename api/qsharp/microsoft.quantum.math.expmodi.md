---
uid: Microsoft.Quantum.Math.ExpModI
title: Modi 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723363"
---
# <a name="expmodi-function"></a><span data-ttu-id="76d0f-102">Modi 関数</span><span class="sxs-lookup"><span data-stu-id="76d0f-102">ExpModI function</span></span>

<span data-ttu-id="76d0f-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="76d0f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="76d0f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76d0f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76d0f-105">指定された剰余に関して、指定された指数で累乗された整数を返します。</span><span class="sxs-lookup"><span data-stu-id="76d0f-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a><span data-ttu-id="76d0f-106">説明</span><span class="sxs-lookup"><span data-stu-id="76d0f-106">Description</span></span>

<span data-ttu-id="76d0f-107">$ $X ドルで底を示し、$ と $p を $N $ で累乗してみましょう。</span><span class="sxs-lookup"><span data-stu-id="76d0f-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="76d0f-108">関数は $x ^ p/演算子名 {mod} N $ を返します。</span><span class="sxs-lookup"><span data-stu-id="76d0f-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="76d0f-109">$N $, $x $ は正の値で、累乗は負ではないと想定しています。</span><span class="sxs-lookup"><span data-stu-id="76d0f-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="76d0f-110">入力</span><span class="sxs-lookup"><span data-stu-id="76d0f-110">Input</span></span>

### <a name="expbase--int"></a><span data-ttu-id="76d0f-111">底: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76d0f-111">expBase : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="power--int"></a><span data-ttu-id="76d0f-112">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76d0f-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="modulus--int"></a><span data-ttu-id="76d0f-113">剰余: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76d0f-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--int"></a><span data-ttu-id="76d0f-114">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="76d0f-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>



## <a name="remarks"></a><span data-ttu-id="76d0f-115">解説</span><span class="sxs-lookup"><span data-stu-id="76d0f-115">Remarks</span></span>

<span data-ttu-id="76d0f-116">は、ではなく、のビット数に比例 `power` `power` します。</span><span class="sxs-lookup"><span data-stu-id="76d0f-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>