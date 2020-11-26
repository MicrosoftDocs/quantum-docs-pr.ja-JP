---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 8117fd632b78c24c9ecb8545274eaf296645b645
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230414"
---
# <a name="applyconditionallya-operation"></a><span data-ttu-id="797e8-102">ApplyConditionallyA 操作</span><span class="sxs-lookup"><span data-stu-id="797e8-102">ApplyConditionallyA operation</span></span>

<span data-ttu-id="797e8-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="797e8-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="797e8-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="797e8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="797e8-105">入力</span><span class="sxs-lookup"><span data-stu-id="797e8-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="797e8-106">measurementResults:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="797e8-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="797e8-107">値の値 __: <Result> 無効__[]</span><span class="sxs-lookup"><span data-stu-id="797e8-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit--is-adj"></a><span data-ttu-id="797e8-108">onEqualOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="797e8-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="797e8-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="797e8-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit--is-adj"></a><span data-ttu-id="797e8-110">onNonEqualOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="797e8-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="797e8-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="797e8-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="797e8-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="797e8-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="797e8-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="797e8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="797e8-114">&</span><span class="sxs-lookup"><span data-stu-id="797e8-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="797e8-115">' U</span><span class="sxs-lookup"><span data-stu-id="797e8-115">'U</span></span>

