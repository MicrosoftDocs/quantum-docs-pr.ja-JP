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
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian ユーザー定義型

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


QFT のリトルエンディアン符号なし整数。

たとえば、$ \ket{x} $ が計算のために $ $x 整数のリトルエンディアンエンコーディングである場合、$ \ket{x} $ は QFT の $x $ のエンコーディングとして使用されます。

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>解説

`PhaseLittleEndian` `PhaseLE` ドキュメントでは、のように省略します。

## <a name="see-also"></a>参照

- [Microsoft... Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)