---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroC
title: Applyifゼロ c 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroC
qsharp.summary: ''
ms.openlocfilehash: 9a73ea9ec607bec89c996c096b235a72185b453d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230839"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="ff10c-102">Applyifゼロ c 操作</span><span class="sxs-lookup"><span data-stu-id="ff10c-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="ff10c-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff10c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ff10c-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="ff10c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroC<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl), zeroArg : 'T)) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="ff10c-105">入力</span><span class="sxs-lookup"><span data-stu-id="ff10c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="ff10c-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="ff10c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-ctl"></a><span data-ttu-id="ff10c-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="ff10c-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="ff10c-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="ff10c-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="ff10c-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff10c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff10c-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff10c-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff10c-111">&</span><span class="sxs-lookup"><span data-stu-id="ff10c-111">'T</span></span>

