---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724674"
---
# <a name="settobasisstate-operation"></a><span data-ttu-id="f15a9-102">SetToBasisState 操作</span><span class="sxs-lookup"><span data-stu-id="f15a9-102">SetToBasisState operation</span></span>

<span data-ttu-id="f15a9-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="f15a9-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="f15a9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f15a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f15a9-105">Qubit を測定し、必要に応じてビットフリップを適用することによって、指定された計算基準の状態に qubit を設定します。</span><span class="sxs-lookup"><span data-stu-id="f15a9-105">Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.</span></span>

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f15a9-106">入力</span><span class="sxs-lookup"><span data-stu-id="f15a9-106">Input</span></span>

### <a name="desired--__invalidresult__"></a><span data-ttu-id="f15a9-107">目的: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f15a9-107">desired : __invalid<Result>__</span></span>

<span data-ttu-id="f15a9-108">Qubit を設定する基準の状態。</span><span class="sxs-lookup"><span data-stu-id="f15a9-108">The basis state that the qubit should be set to.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f15a9-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f15a9-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f15a9-110">状態が設定される qubit。</span><span class="sxs-lookup"><span data-stu-id="f15a9-110">The qubit whose state is to be set.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f15a9-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f15a9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f15a9-112">解説</span><span class="sxs-lookup"><span data-stu-id="f15a9-112">Remarks</span></span>

<span data-ttu-id="f15a9-113">この操作の不変性として、の直後にを呼び出すと、 `M(q)` `SetToBasisState(result, q)` が返され `result` ます。</span><span class="sxs-lookup"><span data-stu-id="f15a9-113">As an invariant of this operation, calling `M(q)` immediately after `SetToBasisState(result, q)` will return `result`.</span></span>