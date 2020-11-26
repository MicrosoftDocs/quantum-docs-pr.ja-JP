---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: accc3ca9c0d99c48c713333ce1cc907054c2a860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230788"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="5c919-102">ApplyIfZeroCA 操作</span><span class="sxs-lookup"><span data-stu-id="5c919-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="5c919-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="5c919-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5c919-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="5c919-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5c919-105">入力</span><span class="sxs-lookup"><span data-stu-id="5c919-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="5c919-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="5c919-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="5c919-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="5c919-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="5c919-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="5c919-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="5c919-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c919-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5c919-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c919-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5c919-111">&</span><span class="sxs-lookup"><span data-stu-id="5c919-111">'T</span></span>

