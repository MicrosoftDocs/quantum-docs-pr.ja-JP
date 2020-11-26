---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: 6fbf186575775b3ae18a41727c225fb871f8dac0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192623"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="fce3a-102">ApplyIfElseRCA 操作</span><span class="sxs-lookup"><span data-stu-id="fce3a-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="fce3a-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="fce3a-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="fce3a-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fce3a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="fce3a-105">入力</span><span class="sxs-lookup"><span data-stu-id="fce3a-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="fce3a-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="fce3a-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="fce3a-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="fce3a-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="fce3a-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="fce3a-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj--ctl"></a><span data-ttu-id="fce3a-109">onResultOneOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="fce3a-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="fce3a-110">On氏 g: ' U</span><span class="sxs-lookup"><span data-stu-id="fce3a-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="fce3a-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fce3a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fce3a-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fce3a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fce3a-113">&</span><span class="sxs-lookup"><span data-stu-id="fce3a-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="fce3a-114">' U</span><span class="sxs-lookup"><span data-stu-id="fce3a-114">'U</span></span>

