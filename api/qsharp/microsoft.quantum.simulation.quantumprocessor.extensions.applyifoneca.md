---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneCA
qsharp.summary: ''
ms.openlocfilehash: 8dd2d501d4598b1de69daa87f7a0941262b7d435
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858906"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="3bad7-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="3bad7-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="3bad7-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="3bad7-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="3bad7-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3bad7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneCA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Ctl + Adj), oneArg : 'T)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3bad7-105">入力</span><span class="sxs-lookup"><span data-stu-id="3bad7-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="3bad7-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3bad7-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj--ctl"></a><span data-ttu-id="3bad7-107">onResultOneOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="3bad7-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onearg--t"></a><span data-ttu-id="3bad7-108">On氏 g: t</span><span class="sxs-lookup"><span data-stu-id="3bad7-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="3bad7-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bad7-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3bad7-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3bad7-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3bad7-111">&</span><span class="sxs-lookup"><span data-stu-id="3bad7-111">'T</span></span>

