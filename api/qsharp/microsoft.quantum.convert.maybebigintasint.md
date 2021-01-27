---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: 1f10ac027f8f289e5ea554a7804abeb33def4df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832759"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="1dd1c-102">MaybeBigIntAsInt 関数</span><span class="sxs-lookup"><span data-stu-id="1dd1c-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="1dd1c-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="1dd1c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="1dd1c-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="1dd1c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1dd1c-105">可能な場合は、指定した大きい整数を等価の整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="1dd1c-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="1dd1c-106">関数は、変換が可能であった場合にのみ、結果として得られる整数とブール値のフラグのペアを返します。</span><span class="sxs-lookup"><span data-stu-id="1dd1c-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="1dd1c-107">入力</span><span class="sxs-lookup"><span data-stu-id="1dd1c-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1dd1c-108">a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1dd1c-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="1dd1c-109">出力: ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span><span class="sxs-lookup"><span data-stu-id="1dd1c-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="1dd1c-110">解説</span><span class="sxs-lookup"><span data-stu-id="1dd1c-110">Remarks</span></span>

<span data-ttu-id="1dd1c-111">詳細については、「 [C# BigInteger コンストラクター](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dd1c-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>