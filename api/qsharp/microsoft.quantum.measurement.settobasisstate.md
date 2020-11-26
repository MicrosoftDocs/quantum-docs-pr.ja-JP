---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: 2612bfe488c830abd835be89b2f8ea6795abf675
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194153"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="bee9f-102">SetToBasisState 操作</span><span class="sxs-lookup"><span data-stu-id="bee9f-102">SetToBasisState operation</span></span>

<span data-ttu-id="bee9f-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="bee9f-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="bee9f-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="bee9f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bee9f-105">Qubit を測定し、必要に応じてビットフリップを適用することによって、指定された計算基準の状態に qubit を設定します。</span><span class="sxs-lookup"><span data-stu-id="bee9f-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bee9f-106">入力</span><span class="sxs-lookup"><span data-stu-id="bee9f-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="bee9f-107">目的:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="bee9f-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="bee9f-108">Qubit を設定する基準の状態。</span><span class="sxs-lookup"><span data-stu-id="bee9f-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bee9f-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bee9f-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bee9f-110">状態が設定される qubit。</span><span class="sxs-lookup"><span data-stu-id="bee9f-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bee9f-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bee9f-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bee9f-112">解説</span><span class="sxs-lookup"><span data-stu-id="bee9f-112">Remarks</span></span>

<span data-ttu-id="bee9f-113">この操作の不変性として、の直後にを呼び出すと、 `M(q)` `SetToBasisState(result, q)` が返され `result` ます。</span><span class="sxs-lookup"><span data-stu-id="bee9f-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>