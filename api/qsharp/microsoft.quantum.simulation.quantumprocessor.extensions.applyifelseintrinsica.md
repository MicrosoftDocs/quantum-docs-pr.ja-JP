---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: f8a2c494bcda6687f3f51044cf4c923213e9d218
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855735"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="cebec-102">ApplyIfElseIntrinsicA 操作</span><span class="sxs-lookup"><span data-stu-id="cebec-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="cebec-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="cebec-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="cebec-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="cebec-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="cebec-105">入力</span><span class="sxs-lookup"><span data-stu-id="cebec-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="cebec-106">measurementResult:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="cebec-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-adj"></a><span data-ttu-id="cebec-107">onResultZeroOp: [単位](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="cebec-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onresultoneop--unit--unit--is-adj"></a><span data-ttu-id="cebec-108">onResultOneOp: [単位](xref:microsoft.quantum.lang-ref.unit) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="cebec-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="cebec-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cebec-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

