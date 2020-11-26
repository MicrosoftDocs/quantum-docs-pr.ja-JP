---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 56b7f93f33ae18146c1fb13d404fc1d119eee72e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202194"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="a376d-102">AssertQubitWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="a376d-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="a376d-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a376d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a376d-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="a376d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a376d-105">`q`指定された許容範囲を上限として、Pauli Z 演算子の予期される eigenstate に qubit があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="a376d-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="a376d-106">入力</span><span class="sxs-lookup"><span data-stu-id="a376d-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="a376d-107">想定:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a376d-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="a376d-108">Qubit があることが予期されている状態: `Zero` または `One` 。</span><span class="sxs-lookup"><span data-stu-id="a376d-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="a376d-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a376d-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a376d-110">状態がアサートされる qubit。</span><span class="sxs-lookup"><span data-stu-id="a376d-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a376d-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a376d-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a376d-112">Qubit の測定値が予想される結果を返す確率の許容範囲です。</span><span class="sxs-lookup"><span data-stu-id="a376d-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a376d-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a376d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a376d-114">解説</span><span class="sxs-lookup"><span data-stu-id="a376d-114">Remarks</span></span>

<span data-ttu-id="a376d-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a376d-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="a376d-116">参照</span><span class="sxs-lookup"><span data-stu-id="a376d-116">See Also</span></span>

- [<span data-ttu-id="a376d-117">AssertQubitIsInStateWithinTolerance です。</span><span class="sxs-lookup"><span data-stu-id="a376d-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)