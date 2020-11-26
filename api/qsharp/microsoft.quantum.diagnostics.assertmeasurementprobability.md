---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 032b9224ad728f0637596668c2928a889deeba55
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202364"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="592b9-102">AssertMeasurementProbability 操作</span><span class="sxs-lookup"><span data-stu-id="592b9-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="592b9-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="592b9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="592b9-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="592b9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="592b9-105">指定された型の指定された qubits を測定すると、特定の確率で特定の結果が許容範囲内にあることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="592b9-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="592b9-106">入力</span><span class="sxs-lookup"><span data-stu-id="592b9-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="592b9-107">ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="592b9-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="592b9-108">の確率をアサートする測定効果。これは、マルチ qubit の P# li 演算子として表現されます。</span><span class="sxs-lookup"><span data-stu-id="592b9-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="592b9-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="592b9-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="592b9-110">アサーションを行うレジスタ。</span><span class="sxs-lookup"><span data-stu-id="592b9-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="592b9-111">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="592b9-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="592b9-112">の予期される結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="592b9-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="592b9-113">: [ダブル](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="592b9-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="592b9-114">指定された結果が返される確率。</span><span class="sxs-lookup"><span data-stu-id="592b9-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="592b9-115">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="592b9-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="592b9-116">アサーションが失敗した場合に報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="592b9-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="592b9-117">を: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="592b9-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="592b9-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="592b9-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="592b9-119">解説</span><span class="sxs-lookup"><span data-stu-id="592b9-119">Remarks</span></span>

<span data-ttu-id="592b9-120">この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="592b9-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="592b9-121">参照</span><span class="sxs-lookup"><span data-stu-id="592b9-121">See Also</span></span>

- [<span data-ttu-id="592b9-122">AssertMeasurement です。</span><span class="sxs-lookup"><span data-stu-id="592b9-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)