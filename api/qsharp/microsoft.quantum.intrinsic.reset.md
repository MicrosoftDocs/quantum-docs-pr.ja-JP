---
uid: Microsoft.Quantum.Intrinsic.Reset
title: リセット操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720871"
---
# <a name="reset-operation"></a><span data-ttu-id="ee648-102">リセット操作</span><span class="sxs-lookup"><span data-stu-id="ee648-102">Reset operation</span></span>

<span data-ttu-id="ee648-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="ee648-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="ee648-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ee648-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ee648-105">1つの qubit を指定すると、それを測定し、安全に解放できるように、それが | 0 ⟩状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee648-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ee648-106">入力</span><span class="sxs-lookup"><span data-stu-id="ee648-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="ee648-107">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ee648-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ee648-108">状態が $ \ket $ にリセットされる qubit {0} 。</span><span class="sxs-lookup"><span data-stu-id="ee648-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee648-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee648-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

