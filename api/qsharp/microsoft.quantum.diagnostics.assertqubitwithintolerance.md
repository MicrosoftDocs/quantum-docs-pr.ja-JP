---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712882"
---
# <a name="assertqubitwithintolerance-operation"></a><span data-ttu-id="1d7c2-102">AssertQubitWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="1d7c2-102">AssertQubitWithinTolerance operation</span></span>

<span data-ttu-id="1d7c2-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1d7c2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1d7c2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1d7c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1d7c2-105">`q`指定された許容範囲を上限として、Pauli Z 演算子の予期される eigenstate に qubit があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="1d7c2-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.</span></span>

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="1d7c2-106">入力</span><span class="sxs-lookup"><span data-stu-id="1d7c2-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="1d7c2-107">想定: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="1d7c2-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="1d7c2-108">Qubit があることが予期されている状態: `Zero` または `One` 。</span><span class="sxs-lookup"><span data-stu-id="1d7c2-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="1d7c2-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1d7c2-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1d7c2-110">状態がアサートされる qubit。</span><span class="sxs-lookup"><span data-stu-id="1d7c2-110">The qubit whose state is asserted.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="1d7c2-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="1d7c2-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="1d7c2-112">Qubit の測定値が予想される結果を返す確率の許容範囲です。</span><span class="sxs-lookup"><span data-stu-id="1d7c2-112">Tolerance on the probability of a measurement of the qubit returning the expected result.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1d7c2-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1d7c2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1d7c2-114">解説</span><span class="sxs-lookup"><span data-stu-id="1d7c2-114">Remarks</span></span>

<span data-ttu-id="1d7c2-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="1d7c2-115"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d7c2-116">参照</span><span class="sxs-lookup"><span data-stu-id="1d7c2-116">See Also</span></span>

- [<span data-ttu-id="1d7c2-117">AssertQubitIsInStateWithinTolerance です。</span><span class="sxs-lookup"><span data-stu-id="1d7c2-117">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)