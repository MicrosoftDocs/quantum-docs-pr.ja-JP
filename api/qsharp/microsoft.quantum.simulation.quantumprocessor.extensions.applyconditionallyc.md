---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Applyconditionの c 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: fc1cf50b7befd40cf20720032329438715a9b856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720187"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="6578b-102">Applyconditionの c 操作</span><span class="sxs-lookup"><span data-stu-id="6578b-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="6578b-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="6578b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="6578b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6578b-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="6578b-105">入力</span><span class="sxs-lookup"><span data-stu-id="6578b-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="6578b-106">measurementResults: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="6578b-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="6578b-107">値の値 __: <Result> 無効__ []</span><span class="sxs-lookup"><span data-stu-id="6578b-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-ctl"></a><span data-ttu-id="6578b-108">onEqualOp: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="6578b-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="6578b-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="6578b-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-ctl"></a><span data-ttu-id="6578b-110">onNonEqualOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="6578b-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="6578b-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="6578b-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="6578b-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6578b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6578b-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6578b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6578b-114">&</span><span class="sxs-lookup"><span data-stu-id="6578b-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="6578b-115">' U</span><span class="sxs-lookup"><span data-stu-id="6578b-115">'U</span></span>

