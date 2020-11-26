---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222781"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="e0022-102">LittleEndian ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="e0022-102">LittleEndian user defined type</span></span>

<span data-ttu-id="e0022-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e0022-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e0022-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0022-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0022-105">符号なし整数をリトルエンディアン順にエンコードするレジスタ。</span><span class="sxs-lookup"><span data-stu-id="e0022-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="e0022-106">Qubit with index は、 `0` 符号なし整数の最下位ビットをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="e0022-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="e0022-107">解説</span><span class="sxs-lookup"><span data-stu-id="e0022-107">Remarks</span></span>

<span data-ttu-id="e0022-108">`LittleEndian` `LE` ドキュメントでは、のように省略します。</span><span class="sxs-lookup"><span data-stu-id="e0022-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>