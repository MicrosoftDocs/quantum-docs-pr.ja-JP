---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicC
title: ApplyIfElseIntrinsicC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicC
qsharp.summary: ''
ms.openlocfilehash: 178d4b704d84090f1f8592b857c3da659e5c50bb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724786"
---
# <a name="applyifelseintrinsicc-operation"></a><span data-ttu-id="09cd2-102">ApplyIfElseIntrinsicC 操作</span><span class="sxs-lookup"><span data-stu-id="09cd2-102">ApplyIfElseIntrinsicC operation</span></span>

<span data-ttu-id="09cd2-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="09cd2-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="09cd2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09cd2-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicC (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl), onResultOneOp : (Unit => Unit is Ctl)) : Unit
```


## <a name="input"></a><span data-ttu-id="09cd2-105">入力</span><span class="sxs-lookup"><span data-stu-id="09cd2-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="09cd2-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="09cd2-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-ctl"></a><span data-ttu-id="09cd2-107">onResultZeroOp: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="09cd2-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="onresultoneop--unit--unit-ctl"></a><span data-ttu-id="09cd2-108">onResultOneOp: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="09cd2-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="09cd2-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09cd2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

