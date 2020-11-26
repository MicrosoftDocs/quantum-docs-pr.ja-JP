---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201412"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="5ee17-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="5ee17-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="5ee17-103">名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="5ee17-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="5ee17-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="5ee17-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5ee17-105">現在使用できる qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="5ee17-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="5ee17-106">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5ee17-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5ee17-107">ステートメントで割り当てることができる qubits の数 `using` 。</span><span class="sxs-lookup"><span data-stu-id="5ee17-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="5ee17-108">使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="5ee17-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ee17-109">参照</span><span class="sxs-lookup"><span data-stu-id="5ee17-109">See Also</span></span>

- [<span data-ttu-id="5ee17-110">GetQubitsAvailableToBorrow (Microsoft Quantum)</span><span class="sxs-lookup"><span data-stu-id="5ee17-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)