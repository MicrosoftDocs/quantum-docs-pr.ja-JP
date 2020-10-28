---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: Applyifゼロ操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 124c5bbabc9e22804734ddbde955312db9655187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725701"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="a42e4-102">Applyifゼロ操作</span><span class="sxs-lookup"><span data-stu-id="a42e4-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="a42e4-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="a42e4-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a42e4-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a42e4-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="a42e4-105">入力</span><span class="sxs-lookup"><span data-stu-id="a42e4-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="a42e4-106">measurementResult: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a42e4-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj"></a><span data-ttu-id="a42e4-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="a42e4-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="a42e4-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="a42e4-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="a42e4-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a42e4-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a42e4-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a42e4-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a42e4-111">&</span><span class="sxs-lookup"><span data-stu-id="a42e4-111">'T</span></span>

