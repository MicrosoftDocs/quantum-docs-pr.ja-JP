---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721147"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="78268-102">FixedPoint ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="78268-102">FixedPoint user defined type</span></span>

<span data-ttu-id="78268-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="78268-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="78268-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78268-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78268-105">固定小数点数をエンコードする qubits のレジスタを表します。</span><span class="sxs-lookup"><span data-stu-id="78268-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="78268-106">は、バイナリポイントの左側にある qubits の数と等しい整数で構成されます。つまり、1以上の重みの qubits と、クォンタムレジスタです。</span><span class="sxs-lookup"><span data-stu-id="78268-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

