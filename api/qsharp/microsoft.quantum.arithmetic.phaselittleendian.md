---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719731"
---
# <a name="phaselittleendian-user-defined-type"></a><span data-ttu-id="d246d-102">PhaseLittleEndian ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="d246d-102">PhaseLittleEndian user defined type</span></span>

<span data-ttu-id="d246d-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d246d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d246d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d246d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d246d-105">QFT のリトルエンディアン符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="d246d-105">Little-endian unsigned integers in QFT basis.</span></span>

<span data-ttu-id="d246d-106">たとえば、$ \ket{x} $ が計算のために $ $x 整数のリトルエンディアンエンコーディングである場合、$ \ket{x} $ は QFT の $x $ のエンコーディングとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d246d-106">For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.</span></span>

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="d246d-107">解説</span><span class="sxs-lookup"><span data-stu-id="d246d-107">Remarks</span></span>

<span data-ttu-id="d246d-108">`PhaseLittleEndian` `PhaseLE` ドキュメントでは、のように省略します。</span><span class="sxs-lookup"><span data-stu-id="d246d-108">We abbreviate `PhaseLittleEndian` as `PhaseLE` in the documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d246d-109">参照</span><span class="sxs-lookup"><span data-stu-id="d246d-109">See Also</span></span>

- [<span data-ttu-id="d246d-110">Microsoft... Canon. QFT</span><span class="sxs-lookup"><span data-stu-id="d246d-110">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)
- [<span data-ttu-id="d246d-111">Microsoft. QFTLE</span><span class="sxs-lookup"><span data-stu-id="d246d-111">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)