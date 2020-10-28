---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: 68d9e02fd19df008f2d42b4f04b585a441b2408a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720122"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="d1281-102">ApplyIfElseIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="d1281-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="d1281-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="d1281-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d1281-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d1281-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="d1281-105">入力</span><span class="sxs-lookup"><span data-stu-id="d1281-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="d1281-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d1281-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-adj"></a><span data-ttu-id="d1281-107">onResultZeroOp: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="d1281-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onresultoneop--unit--unit-adj"></a><span data-ttu-id="d1281-108">onResultOneOp: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="d1281-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="d1281-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1281-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

