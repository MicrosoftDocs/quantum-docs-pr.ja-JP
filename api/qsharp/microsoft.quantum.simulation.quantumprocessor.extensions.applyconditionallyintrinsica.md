---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicA
title: ApplyConditionallyIntrinsicA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: c914ae48646501851cb115d723a28f65c86881de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720151"
---
# <a name="applyconditionallyintrinsica-operation"></a><span data-ttu-id="727fb-102">ApplyConditionallyIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="727fb-102">ApplyConditionallyIntrinsicA operation</span></span>

<span data-ttu-id="727fb-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="727fb-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="727fb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="727fb-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsicA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Adj), onNonEqualOp : (Unit => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="727fb-105">入力</span><span class="sxs-lookup"><span data-stu-id="727fb-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="727fb-106">measurementResults: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="727fb-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="727fb-107">値の値 __: <Result> 無効__ []</span><span class="sxs-lookup"><span data-stu-id="727fb-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit-adj"></a><span data-ttu-id="727fb-108">onequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="727fb-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onnonequalop--unit--unit-adj"></a><span data-ttu-id="727fb-109">onnonequalop: [ユニット](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="727fb-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="727fb-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="727fb-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

