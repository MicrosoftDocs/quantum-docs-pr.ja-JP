---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicA
title: ApplyConditionallyIntrinsicA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: b22cb94a835f0504116e7152a4a1bfe66c483c10
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858518"
---
# <a name="applyconditionallyintrinsica-operation"></a><span data-ttu-id="ed185-102">ApplyConditionallyIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="ed185-102">ApplyConditionallyIntrinsicA operation</span></span>

<span data-ttu-id="ed185-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed185-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ed185-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="ed185-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Adj), onNonEqualOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="ed185-105">入力</span><span class="sxs-lookup"><span data-stu-id="ed185-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="ed185-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="ed185-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="ed185-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="ed185-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-adj"></a><span data-ttu-id="ed185-108">onequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  と形容詞</span><span class="sxs-lookup"><span data-stu-id="ed185-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onnonequalop--unit--unit--is-adj"></a><span data-ttu-id="ed185-109">onnonequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  と形容詞</span><span class="sxs-lookup"><span data-stu-id="ed185-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="ed185-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed185-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

