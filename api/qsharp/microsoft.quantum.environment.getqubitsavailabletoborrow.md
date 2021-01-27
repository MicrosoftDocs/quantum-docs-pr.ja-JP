---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: f2294fadb9c10d800b7a743fbfe0810f36f18516
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853244"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="b0d47-102">GetQubitsAvailableToBorrow 操作</span><span class="sxs-lookup"><span data-stu-id="b0d47-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="b0d47-103">名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="b0d47-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="b0d47-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="b0d47-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b0d47-105">現在借用で使用可能な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="b0d47-105">Returns the number of qubits currently available to borrow.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="b0d47-106">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b0d47-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b0d47-107">借用可能で、ステートメントの一部として割り当てられない qubits の数 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="b0d47-107">The number of qubits that could be borrowed and won't be allocated as part of a `borrowing` statement.</span></span>
<span data-ttu-id="b0d47-108">使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="b0d47-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0d47-109">参照</span><span class="sxs-lookup"><span data-stu-id="b0d47-109">See Also</span></span>

- [<span data-ttu-id="b0d47-110">GetQubitsAvailableToUse (Microsoft Quantum)</span><span class="sxs-lookup"><span data-stu-id="b0d47-110">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)