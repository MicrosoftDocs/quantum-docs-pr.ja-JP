---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRCA
qsharp.summary: ''
ms.openlocfilehash: fb2f7ded44708a93d97d7041bf15be2c8c48990a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719894"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="54e12-102">ApplyIfElseRCA 操作</span><span class="sxs-lookup"><span data-stu-id="54e12-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="54e12-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="54e12-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="54e12-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54e12-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRCA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj + Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj + Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="54e12-105">入力</span><span class="sxs-lookup"><span data-stu-id="54e12-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="54e12-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="54e12-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj--ctl"></a><span data-ttu-id="54e12-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="54e12-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="54e12-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="54e12-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-adj--ctl"></a><span data-ttu-id="54e12-109">onResultOneOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="54e12-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="54e12-110">On氏 g: ' U</span><span class="sxs-lookup"><span data-stu-id="54e12-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="54e12-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="54e12-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="54e12-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="54e12-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="54e12-113">&</span><span class="sxs-lookup"><span data-stu-id="54e12-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="54e12-114">' U</span><span class="sxs-lookup"><span data-stu-id="54e12-114">'U</span></span>

