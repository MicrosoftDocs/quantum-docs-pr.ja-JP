---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Syn% Memeasop ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200256"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="eff40-102">Syn% Memeasop ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="eff40-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="eff40-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="eff40-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="eff40-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eff40-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eff40-105">エラー修正コードブロックのより隣人を測定するために使用される操作を表します。</span><span class="sxs-lookup"><span data-stu-id="eff40-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="eff40-106">解説</span><span class="sxs-lookup"><span data-stu-id="eff40-106">Remarks</span></span>

<span data-ttu-id="eff40-107">このシグネチャは、 `(LogicalRegister => Syndrome)` の qubits と、補助 qubits `LogicalRegister` の後に補助 qubits の測定値を指定して、 `Syndrome` これらの測定値を表す値を抽出する操作を表し `Result[]` ます。</span><span class="sxs-lookup"><span data-stu-id="eff40-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="eff40-108">参照</span><span class="sxs-lookup"><span data-stu-id="eff40-108">See Also</span></span>

- [<span data-ttu-id="eff40-109">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="eff40-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="eff40-110">より隣人を修正します。</span><span class="sxs-lookup"><span data-stu-id="eff40-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)