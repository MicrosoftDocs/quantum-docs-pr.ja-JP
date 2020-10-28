---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: d8f388698c0c6d1557c7903ec68b317728986031
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725696"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="e44dd-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="e44dd-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="e44dd-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="e44dd-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e44dd-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e44dd-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="e44dd-105">入力</span><span class="sxs-lookup"><span data-stu-id="e44dd-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e44dd-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="e44dd-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-ctl--adj"></a><span data-ttu-id="e44dd-107">onResultOneOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="e44dd-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="e44dd-108">On氏 g: t</span><span class="sxs-lookup"><span data-stu-id="e44dd-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="e44dd-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e44dd-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e44dd-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e44dd-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e44dd-111">&</span><span class="sxs-lookup"><span data-stu-id="e44dd-111">'T</span></span>

