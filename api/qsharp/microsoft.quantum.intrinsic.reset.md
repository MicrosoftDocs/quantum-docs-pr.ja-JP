---
uid: Microsoft.Quantum.Intrinsic.Reset
title: リセット操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198675"
---
# <a name="reset-operation"></a><span data-ttu-id="3c647-102">リセット操作</span><span class="sxs-lookup"><span data-stu-id="3c647-102">Reset operation</span></span>

<span data-ttu-id="3c647-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3c647-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3c647-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3c647-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3c647-105">1つの qubit を指定すると、それを測定し、安全に解放できるように、それが | 0 ⟩状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c647-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="3c647-106">入力</span><span class="sxs-lookup"><span data-stu-id="3c647-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="3c647-107">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3c647-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3c647-108">状態が $ \ket $ にリセットされる qubit {0} 。</span><span class="sxs-lookup"><span data-stu-id="3c647-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c647-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c647-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

