---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711039"
---
# <a name="multim-operation"></a><span data-ttu-id="38904-102">MultiM 操作</span><span class="sxs-lookup"><span data-stu-id="38904-102">MultiM operation</span></span>

<span data-ttu-id="38904-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="38904-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="38904-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="38904-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="38904-105">指定された配列内の各 qubit を標準ベースで測定します。</span><span class="sxs-lookup"><span data-stu-id="38904-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="38904-106">入力</span><span class="sxs-lookup"><span data-stu-id="38904-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="38904-107">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="38904-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="38904-108">測定する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="38904-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="38904-109">出力: __無効 <Result> な__ []</span><span class="sxs-lookup"><span data-stu-id="38904-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="38904-110">測定結果の配列。</span><span class="sxs-lookup"><span data-stu-id="38904-110">An array of measurement results.</span></span>