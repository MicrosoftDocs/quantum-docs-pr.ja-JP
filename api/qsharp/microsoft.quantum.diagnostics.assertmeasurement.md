---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713036"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="54af1-102">AssertMeasurement 操作</span><span class="sxs-lookup"><span data-stu-id="54af1-102">AssertMeasurement operation</span></span>

<span data-ttu-id="54af1-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="54af1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="54af1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54af1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54af1-105">指定された P# li の指定した qubits を測定すると、常に指定された結果が得られることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="54af1-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="54af1-106">入力</span><span class="sxs-lookup"><span data-stu-id="54af1-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="54af1-107">ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="54af1-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="54af1-108">の確率をアサートする測定効果。これは、マルチ qubit の P# li 演算子として表現されます。</span><span class="sxs-lookup"><span data-stu-id="54af1-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="54af1-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="54af1-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="54af1-110">アサーションを行うレジスタ。</span><span class="sxs-lookup"><span data-stu-id="54af1-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="54af1-111">結果: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="54af1-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="54af1-112">の予期される結果 `Measure(bases, qubits)` 。</span><span class="sxs-lookup"><span data-stu-id="54af1-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="54af1-113">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="54af1-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="54af1-114">アサーションが失敗した場合に報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="54af1-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="54af1-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54af1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="54af1-116">解説</span><span class="sxs-lookup"><span data-stu-id="54af1-116">Remarks</span></span>

<span data-ttu-id="54af1-117">この操作の Adjoint および制御されたバージョンが条件をチェックしないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="54af1-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="54af1-118">参照</span><span class="sxs-lookup"><span data-stu-id="54af1-118">See Also</span></span>

- [<span data-ttu-id="54af1-119">AssertMeasurementProbability です。</span><span class="sxs-lookup"><span data-stu-id="54af1-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)