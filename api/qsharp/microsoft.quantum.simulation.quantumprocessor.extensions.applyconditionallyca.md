---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyCA
title: Applyconditionの Ca 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyCA
qsharp.summary: ''
ms.openlocfilehash: e456ed5d8f7f17a914401473948c89c020174903
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720175"
---
# <a name="applyconditionallyca-operation"></a><span data-ttu-id="a97e0-102">Applyconditionの Ca 操作</span><span class="sxs-lookup"><span data-stu-id="a97e0-102">ApplyConditionallyCA operation</span></span>

<span data-ttu-id="a97e0-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="a97e0-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="a97e0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a97e0-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyCA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl + Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl + Adj), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="a97e0-105">入力</span><span class="sxs-lookup"><span data-stu-id="a97e0-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="a97e0-106">measurementResults: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="a97e0-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="a97e0-107">値の値 __: <Result> 無効__ []</span><span class="sxs-lookup"><span data-stu-id="a97e0-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--t--unit-ctl--adj"></a><span data-ttu-id="a97e0-108">onEqualOp: t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="a97e0-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="equalarg--t"></a><span data-ttu-id="a97e0-109">equalArg: t</span><span class="sxs-lookup"><span data-stu-id="a97e0-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit-ctl--adj"></a><span data-ttu-id="a97e0-110">onNonEqualOp: ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="a97e0-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="nonequalarg--u"></a><span data-ttu-id="a97e0-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="a97e0-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="a97e0-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a97e0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a97e0-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a97e0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a97e0-114">&</span><span class="sxs-lookup"><span data-stu-id="a97e0-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="a97e0-115">' U</span><span class="sxs-lookup"><span data-stu-id="a97e0-115">'U</span></span>

