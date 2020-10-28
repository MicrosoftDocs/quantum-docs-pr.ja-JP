---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroCA
qsharp.summary: ''
ms.openlocfilehash: 978964888a89ca46847ae7aa01a2c180ee322436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725673"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="af446-102">ApplyIfZeroCA 操作</span><span class="sxs-lookup"><span data-stu-id="af446-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="af446-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="af446-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="af446-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="af446-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroCA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Ctl + Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="af446-105">入力</span><span class="sxs-lookup"><span data-stu-id="af446-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="af446-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="af446-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-ctl--adj"></a><span data-ttu-id="af446-107">onResultZeroOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="af446-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="af446-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="af446-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="af446-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="af446-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="af446-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="af446-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="af446-111">&</span><span class="sxs-lookup"><span data-stu-id="af446-111">'T</span></span>

