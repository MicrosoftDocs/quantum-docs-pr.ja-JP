---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: 条件付き操作の適用
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229071"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="1a7cd-102">条件付き操作の適用</span><span class="sxs-lookup"><span data-stu-id="1a7cd-102">ApplyConditionally operation</span></span>

<span data-ttu-id="1a7cd-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="1a7cd-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="1a7cd-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="1a7cd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="1a7cd-105">入力</span><span class="sxs-lookup"><span data-stu-id="1a7cd-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="1a7cd-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="1a7cd-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="1a7cd-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="1a7cd-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="1a7cd-108">onEqualOp:> [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a7cd-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="1a7cd-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="1a7cd-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="1a7cd-110">onNonEqualOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a7cd-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="1a7cd-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="1a7cd-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1a7cd-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1a7cd-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1a7cd-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a7cd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1a7cd-114">&</span><span class="sxs-lookup"><span data-stu-id="1a7cd-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="1a7cd-115">' U</span><span class="sxs-lookup"><span data-stu-id="1a7cd-115">'U</span></span>

