---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZero
qsharp.summary: ''
ms.openlocfilehash: 867e2e78ea787c2376fb2b1dcc6c72694fe08621
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230907"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="fc0ac-102">ApplyIfZero 操作</span><span class="sxs-lookup"><span data-stu-id="fc0ac-102">ApplyIfZero operation</span></span>

<span data-ttu-id="fc0ac-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="fc0ac-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="fc0ac-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fc0ac-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZero<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="fc0ac-105">入力</span><span class="sxs-lookup"><span data-stu-id="fc0ac-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="fc0ac-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="fc0ac-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="fc0ac-107">onResultZeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc0ac-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="fc0ac-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="fc0ac-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="fc0ac-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fc0ac-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fc0ac-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc0ac-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc0ac-111">&</span><span class="sxs-lookup"><span data-stu-id="fc0ac-111">'T</span></span>

