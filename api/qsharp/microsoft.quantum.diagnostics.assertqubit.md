---
uid: Microsoft.Quantum.Diagnostics.AssertQubit
title: AssertQubit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubit
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.
ms.openlocfilehash: 8fcdd8de9250348e1dd1173052b53be978f2a0c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853447"
---
# <a name="assertqubit-operation"></a><span data-ttu-id="77e33-102">AssertQubit 操作</span><span class="sxs-lookup"><span data-stu-id="77e33-102">AssertQubit operation</span></span>

<span data-ttu-id="77e33-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="77e33-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="77e33-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="77e33-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="77e33-105">Qubit `q` が Pauli Z 演算子の予期される eigenstate にあることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="77e33-105">Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator.</span></span>

```qsharp
operation AssertQubit (expected : Result, q : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="77e33-106">入力</span><span class="sxs-lookup"><span data-stu-id="77e33-106">Input</span></span>

### <a name="expected--__invalidresult__"></a><span data-ttu-id="77e33-107">想定:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="77e33-107">expected : __invalid<Result>__</span></span>

<span data-ttu-id="77e33-108">Qubit があることが予期されている状態: `Zero` または `One` 。</span><span class="sxs-lookup"><span data-stu-id="77e33-108">Which state the qubit is expected to be in: `Zero` or `One`.</span></span>


### <a name="q--qubit"></a><span data-ttu-id="77e33-109">q: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="77e33-109">q : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="77e33-110">状態がアサートされる qubit。</span><span class="sxs-lookup"><span data-stu-id="77e33-110">The qubit whose state is asserted.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77e33-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77e33-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="77e33-112">解説</span><span class="sxs-lookup"><span data-stu-id="77e33-112">Remarks</span></span>

<span data-ttu-id="77e33-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> $Z $ eigenstates だけでなく、任意の qubit 状態をアサートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="77e33-113"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> allows for asserting arbitrary qubit states rather than only $Z$ eigenstates.</span></span>

## <a name="see-also"></a><span data-ttu-id="77e33-114">参照</span><span class="sxs-lookup"><span data-stu-id="77e33-114">See Also</span></span>

- [<span data-ttu-id="77e33-115">AssertQubitIsInStateWithinTolerance です。</span><span class="sxs-lookup"><span data-stu-id="77e33-115">Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)