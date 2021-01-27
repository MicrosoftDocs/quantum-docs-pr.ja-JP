---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830819"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="9bd9b-102">AssertMeasurementProbability 操作</span><span class="sxs-lookup"><span data-stu-id="9bd9b-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="9bd9b-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9bd9b-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9bd9b-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="9bd9b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9bd9b-105">指定された型の指定された qubits を測定すると、特定の確率で特定の結果が許容範囲内にあることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9bd9b-106">入力</span><span class="sxs-lookup"><span data-stu-id="9bd9b-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="9bd9b-107">ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="9bd9b-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="9bd9b-108">の確率をアサートする測定効果。これは、マルチ qubit の P# li 演算子として表現されます。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9bd9b-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9bd9b-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9bd9b-110">アサーションを行うレジスタ。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="9bd9b-111">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9bd9b-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="9bd9b-112">の予期される結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="9bd9b-113">: [ダブル](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9bd9b-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9bd9b-114">指定された結果が返される確率。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="9bd9b-115">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9bd9b-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9bd9b-116">アサーションが失敗した場合に報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="9bd9b-117">を: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9bd9b-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="9bd9b-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9bd9b-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="9bd9b-119">例</span><span class="sxs-lookup"><span data-stu-id="9bd9b-119">Example</span></span>

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a><span data-ttu-id="9bd9b-120">解説</span><span class="sxs-lookup"><span data-stu-id="9bd9b-120">Remarks</span></span>

<span data-ttu-id="9bd9b-121">この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-121">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="9bd9b-122">参照</span><span class="sxs-lookup"><span data-stu-id="9bd9b-122">See Also</span></span>

- [<span data-ttu-id="9bd9b-123">AssertMeasurement です。</span><span class="sxs-lookup"><span data-stu-id="9bd9b-123">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)