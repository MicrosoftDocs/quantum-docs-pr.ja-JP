---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827796"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="cb372-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="cb372-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="cb372-103">名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="cb372-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="cb372-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="cb372-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cb372-105">現在使用できる qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="cb372-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="cb372-106">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb372-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb372-107">ステートメントで割り当てることができる qubits の数 `using` 。</span><span class="sxs-lookup"><span data-stu-id="cb372-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="cb372-108">使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="cb372-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb372-109">参照</span><span class="sxs-lookup"><span data-stu-id="cb372-109">See Also</span></span>

- [<span data-ttu-id="cb372-110">GetQubitsAvailableToBorrow (Microsoft Quantum)</span><span class="sxs-lookup"><span data-stu-id="cb372-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)