---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: GetQubitsAvailableToBorrow 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712588"
---
# <a name="getqubitsavailabletoborrow-operation"></a><span data-ttu-id="7af00-102">GetQubitsAvailableToBorrow 操作</span><span class="sxs-lookup"><span data-stu-id="7af00-102">GetQubitsAvailableToBorrow operation</span></span>

<span data-ttu-id="7af00-103">名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="7af00-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="7af00-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7af00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7af00-105">現在借用で使用可能な qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="7af00-105">Returns the number of qubits currently available to borrow.</span></span>
<span data-ttu-id="7af00-106">これには未使用の qubits が含まれます。つまり、これにはによって返される qubits が含まれ `GetQubitsAvailableToUse` ます。</span><span class="sxs-lookup"><span data-stu-id="7af00-106">This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.</span></span>

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a><span data-ttu-id="7af00-107">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7af00-107">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7af00-108">ステートメントで割り当てることができる qubits の数 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="7af00-108">The number of qubits that could be allocated in a `borrowing` statement.</span></span>
<span data-ttu-id="7af00-109">使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="7af00-109">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="7af00-110">参照</span><span class="sxs-lookup"><span data-stu-id="7af00-110">See Also</span></span>

- [<span data-ttu-id="7af00-111">GetQubitsAvailableToUse (Microsoft Quantum)</span><span class="sxs-lookup"><span data-stu-id="7af00-111">Microsoft.Quantum.Environment.GetQubitsAvailableToUse</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)