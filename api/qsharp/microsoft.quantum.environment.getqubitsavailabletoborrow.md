---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201463"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="79a2f-102">GetQubitsAvailableToBorrow 操作</span><span class="sxs-lookup"><span data-stu-id="79a2f-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="79a2f-103">名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="79a2f-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="79a2f-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="79a2f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="79a2f-105">現在借用で使用可能な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="79a2f-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="79a2f-106">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79a2f-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79a2f-107">借用可能で、ステートメントの一部として割り当てられない qubits の数 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="79a2f-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="79a2f-108">使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="79a2f-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="79a2f-109">参照</span><span class="sxs-lookup"><span data-stu-id="79a2f-109">See Also</span></span>

- [<span data-ttu-id="79a2f-110">GetQubitsAvailableToUse (Microsoft Quantum)</span><span class="sxs-lookup"><span data-stu-id="79a2f-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)