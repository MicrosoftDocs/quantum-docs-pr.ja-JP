---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: Applyiの Ea 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: c18133403a545f7dc7b9f213a42ed09cd194f2d7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725393"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="e1ebe-102">Applyiの Ea 操作</span><span class="sxs-lookup"><span data-stu-id="e1ebe-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="e1ebe-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="e1ebe-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e1ebe-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1ebe-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="e1ebe-105">入力</span><span class="sxs-lookup"><span data-stu-id="e1ebe-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e1ebe-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="e1ebe-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-adj"></a><span data-ttu-id="e1ebe-107">onResultOneOp: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="e1ebe-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="e1ebe-108">On氏 g: t</span><span class="sxs-lookup"><span data-stu-id="e1ebe-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="e1ebe-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1ebe-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e1ebe-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1ebe-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1ebe-111">&</span><span class="sxs-lookup"><span data-stu-id="e1ebe-111">'T</span></span>

