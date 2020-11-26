---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223104"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="f59e5-102">FixedPoint ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="f59e5-102">FixedPoint user defined type</span></span>

<span data-ttu-id="f59e5-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f59e5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f59e5-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f59e5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f59e5-105">固定小数点数をエンコードする qubits のレジスタを表します。</span><span class="sxs-lookup"><span data-stu-id="f59e5-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="f59e5-106">は、バイナリポイントの左側にある qubits の数と等しい整数で構成されます。つまり、1以上の重みの qubits と、クォンタムレジスタです。</span><span class="sxs-lookup"><span data-stu-id="f59e5-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

