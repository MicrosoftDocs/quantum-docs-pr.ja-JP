---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicC
title: ApplyConditionallyIntrinsicC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 64c6693181704d229e36a3e3748258f66e093d96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855742"
---
# <a name="applyconditionallyintrinsicc-operation"></a><span data-ttu-id="af0ab-102">ApplyConditionallyIntrinsicC 操作</span><span class="sxs-lookup"><span data-stu-id="af0ab-102">ApplyConditionallyIntrinsicC operation</span></span>

<span data-ttu-id="af0ab-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="af0ab-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="af0ab-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="af0ab-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicC (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl), onNonEqualOp : (Unit => Unit is Ctl)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="af0ab-105">入力</span><span class="sxs-lookup"><span data-stu-id="af0ab-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="af0ab-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="af0ab-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="af0ab-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="af0ab-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--unit--unit--is-ctl"></a><span data-ttu-id="af0ab-108">onequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="af0ab-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onnonequalop--unit--unit--is-ctl"></a><span data-ttu-id="af0ab-109">onnonequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="af0ab-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="af0ab-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af0ab-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

