---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712579"
---
# <a name="getqubitsavailabletouse-operation"></a><span data-ttu-id="3150e-102">GetQubitsAvailableToUse 操作</span><span class="sxs-lookup"><span data-stu-id="3150e-102">GetQubitsAvailableToUse operation</span></span>

<span data-ttu-id="3150e-103">名前空間: [Microsoft... 環境](xref:Microsoft.Quantum.Environment)</span><span class="sxs-lookup"><span data-stu-id="3150e-103">Namespace: [Microsoft.Quantum.Environment](xref:Microsoft.Quantum.Environment)</span></span>

<span data-ttu-id="3150e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3150e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3150e-105">現在使用できる qubits の数を返します。</span><span class="sxs-lookup"><span data-stu-id="3150e-105">Returns the number of qubits currently available to use.</span></span>

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a><span data-ttu-id="3150e-106">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3150e-106">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3150e-107">ステートメントで割り当てることができる qubits の数 `using` 。</span><span class="sxs-lookup"><span data-stu-id="3150e-107">The number of qubits that could be allocated in a `using` statement.</span></span>
<span data-ttu-id="3150e-108">使用されているターゲットコンピューターがこの情報を提供していない場合 `-1` は、が返されます。</span><span class="sxs-lookup"><span data-stu-id="3150e-108">If the target machine being used does not provide this information, then `-1` is returned.</span></span>

## <a name="see-also"></a><span data-ttu-id="3150e-109">参照</span><span class="sxs-lookup"><span data-stu-id="3150e-109">See Also</span></span>

- [<span data-ttu-id="3150e-110">GetQubitsAvailableToBorrow (Microsoft Quantum)</span><span class="sxs-lookup"><span data-stu-id="3150e-110">Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow</span></span>](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)