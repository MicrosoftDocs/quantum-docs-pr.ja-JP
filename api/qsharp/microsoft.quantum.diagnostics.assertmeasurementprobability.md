---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: ff0419706d825442492f82e564f1cce86f1b112f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712980"
---
# <a name="assertmeasurementprobability-operation"></a><span data-ttu-id="77147-102">AssertMeasurementProbability 操作</span><span class="sxs-lookup"><span data-stu-id="77147-102">AssertMeasurementProbability operation</span></span>

<span data-ttu-id="77147-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="77147-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="77147-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77147-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77147-105">指定された型の指定された qubits を測定すると、特定の確率で特定の結果が許容範囲内にあることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="77147-105">Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="77147-106">入力</span><span class="sxs-lookup"><span data-stu-id="77147-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="77147-107">ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="77147-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="77147-108">の確率をアサートする測定効果。これは、マルチ qubit の P# li 演算子として表現されます。</span><span class="sxs-lookup"><span data-stu-id="77147-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="77147-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="77147-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="77147-110">アサーションを行うレジスタ。</span><span class="sxs-lookup"><span data-stu-id="77147-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="77147-111">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="77147-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="77147-112">の予期される結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="77147-112">An expected result of `Measure(bases, qubits)`.</span></span>


### <a name="prob--double"></a><span data-ttu-id="77147-113">: [ダブル](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="77147-113">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="77147-114">指定された結果が返される確率。</span><span class="sxs-lookup"><span data-stu-id="77147-114">The probability with which the given result is expected.</span></span>


### <a name="msg--string"></a><span data-ttu-id="77147-115">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="77147-115">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="77147-116">アサーションが失敗した場合に報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="77147-116">A message to be reported if the assertion fails.</span></span>


### <a name="tol--double"></a><span data-ttu-id="77147-117">を: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="77147-117">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="77147-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77147-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="77147-119">解説</span><span class="sxs-lookup"><span data-stu-id="77147-119">Remarks</span></span>

<span data-ttu-id="77147-120">この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="77147-120">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="77147-121">参照</span><span class="sxs-lookup"><span data-stu-id="77147-121">See Also</span></span>

- [<span data-ttu-id="77147-122">AssertMeasurement です。</span><span class="sxs-lookup"><span data-stu-id="77147-122">Microsoft.Quantum.Diagnostics.AssertMeasurement</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)