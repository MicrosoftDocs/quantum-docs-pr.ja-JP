---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRC
qsharp.summary: ''
ms.openlocfilehash: 21069c43c16bc9712973ac4e0afea8320c0d83a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709466"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="0f255-102">ApplyIfElseRC 操作</span><span class="sxs-lookup"><span data-stu-id="0f255-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="0f255-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f255-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="0f255-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f255-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseRC<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T), (onResultOneOp : ('U => Unit is Ctl), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="0f255-105">入力</span><span class="sxs-lookup"><span data-stu-id="0f255-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="0f255-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0f255-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl"></a><span data-ttu-id="0f255-107">onResultZeroOp: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="0f255-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="0f255-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="0f255-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit-ctl"></a><span data-ttu-id="0f255-109">onResultOneOp: ' U => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="0f255-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onearg--u"></a><span data-ttu-id="0f255-110">On氏 g: ' U</span><span class="sxs-lookup"><span data-stu-id="0f255-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="0f255-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f255-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0f255-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f255-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f255-113">&</span><span class="sxs-lookup"><span data-stu-id="0f255-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="0f255-114">' U</span><span class="sxs-lookup"><span data-stu-id="0f255-114">'U</span></span>

