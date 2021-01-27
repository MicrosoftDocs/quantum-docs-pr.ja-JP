---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: 329f4d0bc21e74ab6c138af39c88cdcd964e63cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857086"
---
# <a name="divreml-function"></a><span data-ttu-id="96c87-102">DivRemL 関数</span><span class="sxs-lookup"><span data-stu-id="96c87-102">DivRemL function</span></span>

<span data-ttu-id="96c87-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="96c87-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="96c87-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="96c87-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="96c87-105">1つの BigInteger 値を別の値で除算し、その結果と剰余をタプルとして返します。</span><span class="sxs-lookup"><span data-stu-id="96c87-105">Divides one BigInteger value by another, returns the result and the remainder as a tuple.</span></span>

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="96c87-106">入力</span><span class="sxs-lookup"><span data-stu-id="96c87-106">Input</span></span>

### <a name="dividend--bigint"></a><span data-ttu-id="96c87-107">被除数: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="96c87-107">dividend : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="divisor--bigint"></a><span data-ttu-id="96c87-108">除数: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="96c87-108">divisor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigintbigint"></a><span data-ttu-id="96c87-109">出力: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))</span><span class="sxs-lookup"><span data-stu-id="96c87-109">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>



## <a name="remarks"></a><span data-ttu-id="96c87-110">解説</span><span class="sxs-lookup"><span data-stu-id="96c87-110">Remarks</span></span>

<span data-ttu-id="96c87-111">詳細については、 [BigInteger. DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96c87-111">See [System.Numerics.BigInteger.DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) for more details.</span></span>