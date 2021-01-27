---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843201"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="74b3b-102">FixedPoint ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="74b3b-102">FixedPoint user defined type</span></span>

<span data-ttu-id="74b3b-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="74b3b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="74b3b-104">パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="74b3b-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="74b3b-105">固定小数点数をエンコードする qubits のレジスタを表します。</span><span class="sxs-lookup"><span data-stu-id="74b3b-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="74b3b-106">は、バイナリポイントの左側にある qubits の数と等しい整数で構成されます。つまり、1以上の重みの qubits と、クォンタムレジスタです。</span><span class="sxs-lookup"><span data-stu-id="74b3b-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

