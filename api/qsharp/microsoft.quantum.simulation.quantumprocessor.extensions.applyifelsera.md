---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseRA
title: ApplyIfElseRA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseRA
qsharp.summary: ''
ms.openlocfilehash: 11427026d66fc6f46f05004db4dae6f9fa05d921
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855661"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="95004-102">ApplyIfElseRA 操作</span><span class="sxs-lookup"><span data-stu-id="95004-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="95004-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="95004-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="95004-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="95004-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseRA<'T, 'U> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T), (onResultOneOp : ('U => Unit is Adj), oneArg : 'U)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="95004-105">入力</span><span class="sxs-lookup"><span data-stu-id="95004-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="95004-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="95004-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="95004-107">onResultZeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="95004-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="95004-108">ゼロ Arg: ' '</span><span class="sxs-lookup"><span data-stu-id="95004-108">zeroArg : 'T</span></span>




### <a name="onresultoneop--u--unit--is-adj"></a><span data-ttu-id="95004-109">onResultOneOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="95004-109">onResultOneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--u"></a><span data-ttu-id="95004-110">On氏 g: ' U</span><span class="sxs-lookup"><span data-stu-id="95004-110">oneArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="95004-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95004-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="95004-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="95004-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="95004-113">&</span><span class="sxs-lookup"><span data-stu-id="95004-113">'T</span></span>


### <a name="u"></a><span data-ttu-id="95004-114">' U</span><span class="sxs-lookup"><span data-stu-id="95004-114">'U</span></span>

