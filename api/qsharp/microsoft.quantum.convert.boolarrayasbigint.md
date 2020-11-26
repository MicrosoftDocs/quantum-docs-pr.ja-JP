---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: ブール Arrayasbigint 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 5a85fd9f81cec0f2de7e7807622aab9604a4db7c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214315"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="d8bb1-102">ブール Arrayasbigint 関数</span><span class="sxs-lookup"><span data-stu-id="d8bb1-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="d8bb1-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="d8bb1-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="d8bb1-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="d8bb1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d8bb1-105">指定したブール値の配列を等価の大きい整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="d8bb1-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="d8bb1-106">配列の0要素は、大きい整数の最下位ビットです。</span><span class="sxs-lookup"><span data-stu-id="d8bb1-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="d8bb1-107">入力</span><span class="sxs-lookup"><span data-stu-id="d8bb1-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d8bb1-108">a: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="d8bb1-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="d8bb1-109">出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d8bb1-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="d8bb1-110">解説</span><span class="sxs-lookup"><span data-stu-id="d8bb1-110">Remarks</span></span>

<span data-ttu-id="d8bb1-111">詳細については、「 [C# BigInteger コンストラクター](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8bb1-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>