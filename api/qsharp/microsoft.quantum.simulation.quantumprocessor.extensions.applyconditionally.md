---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: 条件付き操作の適用
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710535"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="5fe80-102">条件付き操作の適用</span><span class="sxs-lookup"><span data-stu-id="5fe80-102">ApplyConditionally operation</span></span>

<span data-ttu-id="5fe80-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="5fe80-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5fe80-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5fe80-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="5fe80-105">入力</span><span class="sxs-lookup"><span data-stu-id="5fe80-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="5fe80-106">measurementResults: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="5fe80-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="5fe80-107">値の値 __: <Result> 無効__ []</span><span class="sxs-lookup"><span data-stu-id="5fe80-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="5fe80-108">onEqualOp:> [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fe80-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="5fe80-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="5fe80-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="5fe80-110">onNonEqualOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fe80-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="5fe80-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="5fe80-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="5fe80-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fe80-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5fe80-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fe80-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5fe80-114">&</span><span class="sxs-lookup"><span data-stu-id="5fe80-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5fe80-115">' U</span><span class="sxs-lookup"><span data-stu-id="5fe80-115">'U</span></span>
