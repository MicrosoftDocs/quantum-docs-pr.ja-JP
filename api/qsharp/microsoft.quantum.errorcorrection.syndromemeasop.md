---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Syn% Memeasop ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 1314e16d26c7310bab21caa91cb398d4b6f09b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712117"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="e1305-102">Syn% Memeasop ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="e1305-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="e1305-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="e1305-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="e1305-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1305-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1305-105">エラー修正コードブロックのより隣人を測定するために使用される操作を表します。</span><span class="sxs-lookup"><span data-stu-id="e1305-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="e1305-106">解説</span><span class="sxs-lookup"><span data-stu-id="e1305-106">Remarks</span></span>

<span data-ttu-id="e1305-107">このシグネチャは、 `(LogicalRegister => Syndrome)` の qubits と、補助 qubits `LogicalRegister` の後に補助 qubits の測定値を指定して、 `Syndrome` これらの測定値を表す値を抽出する操作を表し `Result[]` ます。</span><span class="sxs-lookup"><span data-stu-id="e1305-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1305-108">参照</span><span class="sxs-lookup"><span data-stu-id="e1305-108">See Also</span></span>

- [<span data-ttu-id="e1305-109">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="e1305-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="e1305-110">より隣人を修正します。</span><span class="sxs-lookup"><span data-stu-id="e1305-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)