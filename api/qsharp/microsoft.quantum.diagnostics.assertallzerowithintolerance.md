---
uid: Microsoft.Quantum.Diagnostics.AssertAllZeroWithinTolerance
title: AssertAllZeroWithinTolerance 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertAllZeroWithinTolerance
qsharp.summary: Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.
ms.openlocfilehash: 5e401904086323fabef7914d34463f50e4c38862
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713041"
---
# <a name="assertallzerowithintolerance-operation"></a><span data-ttu-id="cbc60-102">AssertAllZeroWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="cbc60-102">AssertAllZeroWithinTolerance operation</span></span>

<span data-ttu-id="cbc60-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cbc60-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cbc60-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbc60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbc60-105">指定された qubits のアサートはすべて、指定された許容範囲内の $ \ket {0} $ 状態にあります。</span><span class="sxs-lookup"><span data-stu-id="cbc60-105">Assert that given qubits are all in $\ket{0}$ state up to a given tolerance.</span></span>

```qsharp
operation AssertAllZeroWithinTolerance (qubits : Qubit[], tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="cbc60-106">入力</span><span class="sxs-lookup"><span data-stu-id="cbc60-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="cbc60-107">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cbc60-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cbc60-108">$ \Ket $ 状態になるようにアサートされた qubits {0} 。</span><span class="sxs-lookup"><span data-stu-id="cbc60-108">Qubits that are asserted to be in $\ket{0}$ state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="cbc60-109">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cbc60-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cbc60-110">状態を $ \ket $ 状態にするための精度 {0}</span><span class="sxs-lookup"><span data-stu-id="cbc60-110">Accuracy with which the state should be in $\ket{0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbc60-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbc60-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cbc60-112">参照</span><span class="sxs-lookup"><span data-stu-id="cbc60-112">See Also</span></span>

- [<span data-ttu-id="cbc60-113">AssertQubitWithinTolerance です。</span><span class="sxs-lookup"><span data-stu-id="cbc60-113">Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance)