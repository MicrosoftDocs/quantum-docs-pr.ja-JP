---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 33b3adfca87410480108eafd090632006117f7b2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192640"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="f9b02-102">ApplyIfElseRC 操作</span><span class="sxs-lookup"><span data-stu-id="f9b02-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="f9b02-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="f9b02-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="f9b02-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="f9b02-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f9b02-105">入力</span><span class="sxs-lookup"><span data-stu-id="f9b02-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="f9b02-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f9b02-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="f9b02-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="f9b02-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="f9b02-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="f9b02-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-ctl"></a><span data-ttu-id="f9b02-109">onResultOneOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="f9b02-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="f9b02-110">On氏 g: ' U</span><span class="sxs-lookup"><span data-stu-id="f9b02-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="f9b02-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9b02-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9b02-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f9b02-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9b02-113">&</span><span class="sxs-lookup"><span data-stu-id="f9b02-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="f9b02-114">' U</span><span class="sxs-lookup"><span data-stu-id="f9b02-114">'U</span></span>

