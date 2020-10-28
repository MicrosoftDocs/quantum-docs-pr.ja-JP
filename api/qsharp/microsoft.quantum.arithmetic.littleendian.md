---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721046"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="65a42-102">LittleEndian ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="65a42-102">LittleEndian user defined type</span></span>

<span data-ttu-id="65a42-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="65a42-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="65a42-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65a42-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65a42-105">符号なし整数をリトルエンディアン順にエンコードするレジスタ。</span><span class="sxs-lookup"><span data-stu-id="65a42-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="65a42-106">Qubit with index は、 `0` 符号なし整数の最下位ビットをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="65a42-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="65a42-107">解説</span><span class="sxs-lookup"><span data-stu-id="65a42-107">Remarks</span></span>

<span data-ttu-id="65a42-108">`LittleEndian` `LE` ドキュメントでは、のように省略します。</span><span class="sxs-lookup"><span data-stu-id="65a42-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>