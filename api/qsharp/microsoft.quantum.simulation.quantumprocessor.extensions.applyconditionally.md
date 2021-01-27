---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: 条件付き操作の適用
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 67a4dcba5c193222c06ab429813adf12d7bbedfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847898"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="3f0a1-102">条件付き操作の適用</span><span class="sxs-lookup"><span data-stu-id="3f0a1-102">ApplyConditionally operation</span></span>

<span data-ttu-id="3f0a1-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f0a1-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3f0a1-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3f0a1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="3f0a1-105">入力</span><span class="sxs-lookup"><span data-stu-id="3f0a1-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="3f0a1-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="3f0a1-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="3f0a1-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="3f0a1-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="3f0a1-108">onEqualOp:> [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f0a1-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="3f0a1-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="3f0a1-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="3f0a1-110">onNonEqualOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f0a1-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="3f0a1-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="3f0a1-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="3f0a1-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3f0a1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3f0a1-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3f0a1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3f0a1-114">&</span><span class="sxs-lookup"><span data-stu-id="3f0a1-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="3f0a1-115">' U</span><span class="sxs-lookup"><span data-stu-id="3f0a1-115">'U</span></span>

