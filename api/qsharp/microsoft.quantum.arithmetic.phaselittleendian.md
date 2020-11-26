---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222424"
---
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian ユーザー定義型

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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