---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712411"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="475e2-102">DecodeOp ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="475e2-102">DecodeOp user defined type</span></span>

<span data-ttu-id="475e2-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="475e2-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="475e2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="475e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="475e2-105">エンコードされたレジスタを物理レジスタにデコードし、より隣人を記録するために使用するスクラッチのビットをデコードする操作を表します。</span><span class="sxs-lookup"><span data-stu-id="475e2-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="475e2-106">DecodeOp の引数は、EncodeOp からの戻り値と同じです。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="475e2-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

