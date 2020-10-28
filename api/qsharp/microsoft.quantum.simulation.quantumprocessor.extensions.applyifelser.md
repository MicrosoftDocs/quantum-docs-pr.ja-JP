---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseR
qsharp.summary: ''
ms.openlocfilehash: ca9db334bb62e043933f99e405612957831efdcb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724772"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="76b3c-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="76b3c-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="76b3c-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="76b3c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="76b3c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="76b3c-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseR<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit), zeroArg : 'T), (onResultOneOp : ('U => Unit), oneArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="76b3c-105">入力</span><span class="sxs-lookup"><span data-stu-id="76b3c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="76b3c-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="76b3c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit"></a><span data-ttu-id="76b3c-107">onResultZeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76b3c-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="zeroarg--t"></a><span data-ttu-id="76b3c-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="76b3c-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit"></a><span data-ttu-id="76b3c-109">onResultOneOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76b3c-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--u"></a><span data-ttu-id="76b3c-110">On氏 g: ' U</span><span class="sxs-lookup"><span data-stu-id="76b3c-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="76b3c-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="76b3c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="76b3c-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="76b3c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="76b3c-113">&</span><span class="sxs-lookup"><span data-stu-id="76b3c-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="76b3c-114">' U</span><span class="sxs-lookup"><span data-stu-id="76b3c-114">'U</span></span>

