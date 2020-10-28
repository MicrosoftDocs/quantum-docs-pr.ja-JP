---
uid: Microsoft.Quantum.Math.PowL
title: PowL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PowL
qsharp.summary: Returns a number raised to a given power.
ms.openlocfilehash: 22c05cf85acf691490049ce9ac27a7c6b2a4899e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724749"
---
# <a name="powl-function"></a><span data-ttu-id="f5ea3-102">PowL 関数</span><span class="sxs-lookup"><span data-stu-id="f5ea3-102">PowL function</span></span>

<span data-ttu-id="f5ea3-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f5ea3-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f5ea3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f5ea3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f5ea3-105">指定された指数で累乗された数値を返します。</span><span class="sxs-lookup"><span data-stu-id="f5ea3-105">Returns a number raised to a given power.</span></span>

```qsharp
function PowL (a : BigInt, power : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="f5ea3-106">入力</span><span class="sxs-lookup"><span data-stu-id="f5ea3-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="f5ea3-107">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f5ea3-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f5ea3-108">発生させる $ $a 番号。</span><span class="sxs-lookup"><span data-stu-id="f5ea3-108">The number $a$ that is to be raised.</span></span>


### <a name="power--int"></a><span data-ttu-id="f5ea3-109">power: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f5ea3-109">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f5ea3-110">$A $ が発生する必要のある power $b $。</span><span class="sxs-lookup"><span data-stu-id="f5ea3-110">The power $b$ to which $a$ should be raised.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="f5ea3-111">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="f5ea3-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="f5ea3-112">Power $a ^ b $</span><span class="sxs-lookup"><span data-stu-id="f5ea3-112">The power $a^b$</span></span>