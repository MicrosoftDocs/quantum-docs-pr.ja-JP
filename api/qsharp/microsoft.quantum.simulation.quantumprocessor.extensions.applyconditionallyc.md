---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: Applyconditionの c 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: 963a85e0e442592c01a2e70fa0dc02d6048d8be7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229037"
---
# <a name="applyconditionallyc-operation"></a><span data-ttu-id="b1911-102">Applyconditionの c 操作</span><span class="sxs-lookup"><span data-stu-id="b1911-102">ApplyConditionallyC operation</span></span>

<span data-ttu-id="b1911-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1911-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="b1911-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="b1911-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="b1911-105">入力</span><span class="sxs-lookup"><span data-stu-id="b1911-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="b1911-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="b1911-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="b1911-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="b1911-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-ctl"></a><span data-ttu-id="b1911-108">onEqualOp:> [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="b1911-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="b1911-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="b1911-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-ctl"></a><span data-ttu-id="b1911-110">onNonEqualOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="b1911-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="b1911-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="b1911-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="b1911-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1911-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1911-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1911-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1911-114">&</span><span class="sxs-lookup"><span data-stu-id="b1911-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="b1911-115">' U</span><span class="sxs-lookup"><span data-stu-id="b1911-115">'U</span></span>

