---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 1ce83389f2ac3ce9ab2898f9d167941ca2973508
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834597"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="abd69-102">BigIntAsBoolArray 関数</span><span class="sxs-lookup"><span data-stu-id="abd69-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="abd69-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="abd69-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="abd69-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="abd69-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="abd69-105">指定した大きい整数をブール値の配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="abd69-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="abd69-106">配列の0要素は、大きい整数の最下位ビットです。</span><span class="sxs-lookup"><span data-stu-id="abd69-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="abd69-107">入力</span><span class="sxs-lookup"><span data-stu-id="abd69-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="abd69-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="abd69-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="abd69-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="abd69-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="abd69-110">解説</span><span class="sxs-lookup"><span data-stu-id="abd69-110">Remarks</span></span>

<span data-ttu-id="abd69-111">詳細については、「 [C# BigInteger コンストラクター](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abd69-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>