---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713433"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="ca310-102">MaybeBigIntAsInt 関数</span><span class="sxs-lookup"><span data-stu-id="ca310-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="ca310-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ca310-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ca310-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca310-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca310-105">可能な場合は、指定した大きい整数を等価の整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="ca310-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="ca310-106">関数は、変換が可能であった場合にのみ、結果として得られる整数とブール値のフラグのペアを返します。</span><span class="sxs-lookup"><span data-stu-id="ca310-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="ca310-107">入力</span><span class="sxs-lookup"><span data-stu-id="ca310-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="ca310-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ca310-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="ca310-109">出力: ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="ca310-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="ca310-110">解説</span><span class="sxs-lookup"><span data-stu-id="ca310-110">Remarks</span></span>

<span data-ttu-id="ca310-111">詳細については、「 [C# BigInteger コンストラクター](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca310-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>