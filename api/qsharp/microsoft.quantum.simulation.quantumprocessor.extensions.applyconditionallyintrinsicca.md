---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 7cdddba45824d5e5037270d8578f2cb16c03be83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720134"
---
# <a name="applyconditionallyintrinsicca-operation"></a><span data-ttu-id="3c83d-102">ApplyConditionallyIntrinsicCA 操作</span><span class="sxs-lookup"><span data-stu-id="3c83d-102">ApplyConditionallyIntrinsicCA operation</span></span>

<span data-ttu-id="3c83d-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="3c83d-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3c83d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c83d-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="3c83d-105">入力</span><span class="sxs-lookup"><span data-stu-id="3c83d-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="3c83d-106">measurementResults: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="3c83d-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="3c83d-107">値の値 __: <Result> 無効__ []</span><span class="sxs-lookup"><span data-stu-id="3c83d-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-ctl--adj"></a><span data-ttu-id="3c83d-108">onequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="3c83d-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onnonequalop--unit--unit-ctl--adj"></a><span data-ttu-id="3c83d-109">onnonequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="3c83d-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="3c83d-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c83d-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
