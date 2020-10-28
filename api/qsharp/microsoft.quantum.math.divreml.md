---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: d2ca91e0c3e8d69902234689359da7b73a8f7d1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723741"
---
# <a name="divreml-function"></a><span data-ttu-id="5017e-102">DivRemL 関数</span><span class="sxs-lookup"><span data-stu-id="5017e-102">DivRemL function</span></span>

<span data-ttu-id="5017e-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="5017e-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="5017e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5017e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5017e-105">1つの BigInteger 値を別の値で除算し、その結果と剰余をタプルとして返します。</span><span class="sxs-lookup"><span data-stu-id="5017e-105">Divides one BigInteger value by another, returns the result and the remainder as a tuple.</span></span>

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="5017e-106">入力</span><span class="sxs-lookup"><span data-stu-id="5017e-106">Input</span></span>

### <a name="dividend--bigint"></a><span data-ttu-id="5017e-107">被除数: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5017e-107">dividend : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="divisor--bigint"></a><span data-ttu-id="5017e-108">除数: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5017e-108">divisor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigintbigint"></a><span data-ttu-id="5017e-109">出力: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="5017e-109">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>



## <a name="remarks"></a><span data-ttu-id="5017e-110">解説</span><span class="sxs-lookup"><span data-stu-id="5017e-110">Remarks</span></span>

<span data-ttu-id="5017e-111">詳細については、 [BigInteger. DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5017e-111">See [System.Numerics.BigInteger.DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) for more details.</span></span>