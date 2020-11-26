---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Applyconditionの Ca 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: 18db01f8e5e00c2f115b8ffe73c0f8eea275beb0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230244"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="d38de-102">Applyconditionの Ca 操作</span><span class="sxs-lookup"><span data-stu-id="d38de-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="d38de-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="d38de-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d38de-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="d38de-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d38de-105">入力</span><span class="sxs-lookup"><span data-stu-id="d38de-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="d38de-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="d38de-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="d38de-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="d38de-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj--ctl"></a><span data-ttu-id="d38de-108">onEqualOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d38de-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="d38de-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="d38de-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj--ctl"></a><span data-ttu-id="d38de-110">onNonEqualOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="d38de-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="d38de-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="d38de-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="d38de-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d38de-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d38de-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d38de-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d38de-114">&</span><span class="sxs-lookup"><span data-stu-id="d38de-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="d38de-115">' U</span><span class="sxs-lookup"><span data-stu-id="d38de-115">'U</span></span>

