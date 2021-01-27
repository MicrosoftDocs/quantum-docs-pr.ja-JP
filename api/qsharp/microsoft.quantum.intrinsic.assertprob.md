---
uid: Microsoft.Quantum.Intrinsic.AssertProb
title: AssertProb 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: AssertProb
qsharp.summary: >-
  > [!WARNING]

  > AssertProb has been deprecated. Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.
ms.openlocfilehash: a3bdf8d6ae64f0d462da1781a723b27b6e1db05e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849451"
---
# <a name="assertprob-operation"></a><span data-ttu-id="7bedc-102">AssertProb 操作</span><span class="sxs-lookup"><span data-stu-id="7bedc-102">AssertProb operation</span></span>

<span data-ttu-id="7bedc-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="7bedc-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="7bedc-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="7bedc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


> [!WARNING]
> <span data-ttu-id="7bedc-105">AssertProb は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="7bedc-105">AssertProb has been deprecated.</span></span> <span data-ttu-id="7bedc-106">代わりに、<xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7bedc-106">Please use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> instead.</span></span>



```qsharp
operation AssertProb (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7bedc-107">入力</span><span class="sxs-lookup"><span data-stu-id="7bedc-107">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="7bedc-108">ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="7bedc-108">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="7bedc-109">qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7bedc-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="result--__invalidresult__"></a><span data-ttu-id="7bedc-110">結果:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7bedc-110">result : __invalid<Result>__</span></span>




### <a name="prob--double"></a><span data-ttu-id="7bedc-111">: [ダブル](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7bedc-111">prob : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="msg--string"></a><span data-ttu-id="7bedc-112">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7bedc-112">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>




### <a name="tol--double"></a><span data-ttu-id="7bedc-113">を: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7bedc-113">tol : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--unit"></a><span data-ttu-id="7bedc-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7bedc-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

