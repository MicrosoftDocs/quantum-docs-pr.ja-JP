---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: Applyifゼロ操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 812b7a830d963b4bb73c32ba1c136e506789e997
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854195"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="4540e-102">Applyifゼロ操作</span><span class="sxs-lookup"><span data-stu-id="4540e-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="4540e-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="4540e-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="4540e-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="4540e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4540e-105">入力</span><span class="sxs-lookup"><span data-stu-id="4540e-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="4540e-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="4540e-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="4540e-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="4540e-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="4540e-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="4540e-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="4540e-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4540e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4540e-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4540e-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4540e-111">&</span><span class="sxs-lookup"><span data-stu-id="4540e-111">'T</span></span>

