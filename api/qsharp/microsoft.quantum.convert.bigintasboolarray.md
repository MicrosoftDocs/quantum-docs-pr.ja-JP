---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 13ba5b6dbf477dd1a02f24da5b7aca9bdb30ad2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713624"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="70789-102">BigIntAsBoolArray 関数</span><span class="sxs-lookup"><span data-stu-id="70789-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="70789-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="70789-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="70789-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70789-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70789-105">指定した大きい整数をブール値の配列に変換します。</span><span class="sxs-lookup"><span data-stu-id="70789-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="70789-106">配列の0要素は、大きい整数の最下位ビットです。</span><span class="sxs-lookup"><span data-stu-id="70789-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="70789-107">入力</span><span class="sxs-lookup"><span data-stu-id="70789-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="70789-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="70789-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="70789-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="70789-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="70789-110">解説</span><span class="sxs-lookup"><span data-stu-id="70789-110">Remarks</span></span>

<span data-ttu-id="70789-111">詳細については、「 [C# BigInteger コンストラクター](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70789-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>