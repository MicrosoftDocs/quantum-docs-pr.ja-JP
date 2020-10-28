---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: fa1f52da5a011cd914a0fda69b78cf5a4fd71e16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712943"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="af986-102">AssertQubit 操作</span><span class="sxs-lookup"><span data-stu-id="af986-102">AssertQubit operation</span></span>

<span data-ttu-id="af986-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="af986-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="af986-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af986-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="af986-105">Qubit `q` が Pauli Z 演算子の予期される eigenstate にあることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="af986-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="af986-106">入力</span><span class="sxs-lookup"><span data-stu-id="af986-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="af986-107">想定: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="af986-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="af986-108">Qubit があることが予期されている状態: `Zero` または `One` 。</span><span class="sxs-lookup"><span data-stu-id="af986-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="af986-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="af986-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="af986-110">状態がアサートされる qubit。</span><span class="sxs-lookup"><span data-stu-id="af986-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="af986-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af986-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="af986-112">解説</span><span class="sxs-lookup"><span data-stu-id="af986-112">Remarks</span></span>

<span data-ttu-id="af986-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="af986-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="af986-114">参照</span><span class="sxs-lookup"><span data-stu-id="af986-114">See Also</span></span>

- [<span data-ttu-id="af986-115">AssertQubitIsInStateWithinTolerance です。</span><span class="sxs-lookup"><span data-stu-id="af986-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)