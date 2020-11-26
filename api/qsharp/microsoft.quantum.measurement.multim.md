---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226997"
---
# <a name="multim-operation"></a><span data-ttu-id="f9278-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="f9278-102">MultiM operation</span></span>

<span data-ttu-id="f9278-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="f9278-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="f9278-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9278-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9278-105">指定された配列内の各 qubit を標準ベースで測定します。</span><span class="sxs-lookup"><span data-stu-id="f9278-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="f9278-106">入力</span><span class="sxs-lookup"><span data-stu-id="f9278-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="f9278-107">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f9278-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f9278-108">測定する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="f9278-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f9278-109">出力:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="f9278-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="f9278-110">測定結果の配列。</span><span class="sxs-lookup"><span data-stu-id="f9278-110">An array of measurement results.</span></span>