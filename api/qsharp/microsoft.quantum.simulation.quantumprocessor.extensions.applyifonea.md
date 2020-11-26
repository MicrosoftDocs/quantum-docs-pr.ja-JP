---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: Applyiの Ea 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 93a72ee7174b0022b1fe30cd779dfc57e96d8033
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228272"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="f1c3f-102">Applyiの Ea 操作</span><span class="sxs-lookup"><span data-stu-id="f1c3f-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="f1c3f-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1c3f-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f1c3f-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="f1c3f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f1c3f-105">入力</span><span class="sxs-lookup"><span data-stu-id="f1c3f-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f1c3f-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f1c3f-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="f1c3f-107">onResultOneOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="f1c3f-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="f1c3f-108">On氏 g: t</span><span class="sxs-lookup"><span data-stu-id="f1c3f-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="f1c3f-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1c3f-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f1c3f-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f1c3f-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1c3f-111">&</span><span class="sxs-lookup"><span data-stu-id="f1c3f-111">'T</span></span>

