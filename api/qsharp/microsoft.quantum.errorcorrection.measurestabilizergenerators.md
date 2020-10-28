---
uid: Microsoft.Quantum.ErrorCorrection.MeasureStabilizerGenerators
title: MeasureStabilizerGenerators 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: MeasureStabilizerGenerators
qsharp.summary: Measures the given set of generators of a stabilizer group.
ms.openlocfilehash: a3f48ff24a39d13a57f7a144e21d4e41bb8a8b49
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712266"
---
# <a name="measurestabilizergenerators-operation"></a><span data-ttu-id="76187-102">MeasureStabilizerGenerators 操作</span><span class="sxs-lookup"><span data-stu-id="76187-102">MeasureStabilizerGenerators operation</span></span>

<span data-ttu-id="76187-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="76187-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="76187-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76187-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="76187-105">安定板グループの特定のジェネレーターセットを測定します。</span><span class="sxs-lookup"><span data-stu-id="76187-105">Measures the given set of generators of a stabilizer group.</span></span>

```qsharp
operation MeasureStabilizerGenerators (stabilizerGroup : Pauli[][], logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister, gadget : ((Pauli[], Qubit[]) => Result)) : Microsoft.Quantum.ErrorCorrection.Syndrome
```


## <a name="input"></a><span data-ttu-id="76187-106">入力</span><span class="sxs-lookup"><span data-stu-id="76187-106">Input</span></span>

### <a name="stabilizergroup--pauli"></a><span data-ttu-id="76187-107">stabilizerGroup: [p li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="76187-107">stabilizerGroup : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="76187-108">Multiqubit P# li 演算子の配列。</span><span class="sxs-lookup"><span data-stu-id="76187-108">An array of multiqubit Pauli operators.</span></span>
<span data-ttu-id="76187-109">たとえば、 `stabilizerGroup[0]` は、シングル qubit の P# li マトリックスのリストです。これは、安定板のジェネレーターです。</span><span class="sxs-lookup"><span data-stu-id="76187-109">For example, `stabilizerGroup[0]` is a list of single-qubit Pauli matrices, the tensor product of which is a stabilizer generator.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="76187-110">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="76187-110">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="76187-111">安定板のコードが定義されている qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="76187-111">An array of qubits where the stabilizer code is defined.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="76187-112">ガジェット: ( [p、li](xref:microsoft.quantum.lang-ref.pauli)[]、 [qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = __無効 <Result>__ ></span><span class="sxs-lookup"><span data-stu-id="76187-112">gadget : ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="76187-113">Multiqubit の P# li 演算子を測定する方法を指定する操作。</span><span class="sxs-lookup"><span data-stu-id="76187-113">An operation that specifies how to measure a multiqubit Pauli operator.</span></span>



## <a name="output--syndrome"></a><span data-ttu-id="76187-114">出力: [より隣人](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="76187-114">Output : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="76187-115">測定の結果。</span><span class="sxs-lookup"><span data-stu-id="76187-115">The result of measurements.</span></span>

## <a name="remarks"></a><span data-ttu-id="76187-116">解説</span><span class="sxs-lookup"><span data-stu-id="76187-116">Remarks</span></span>

<span data-ttu-id="76187-117">これは、指定されたジェネレーターのセットが通勤されているかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="76187-117">This does not check if the given set of generators are commuting.</span></span>
<span data-ttu-id="76187-118">通勤でない場合は、測定の結果が任意である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76187-118">If they are not commuting, the result of measurements may be arbitrary.</span></span>