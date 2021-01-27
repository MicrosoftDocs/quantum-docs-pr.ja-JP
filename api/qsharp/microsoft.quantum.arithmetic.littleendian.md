---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846561"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian ユーザー定義型

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


符号なし整数をリトルエンディアン順にエンコードするレジスタ。 Qubit with index は、 `0` 符号なし整数の最下位ビットをエンコードします。

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>解説

`LittleEndian` `LE` ドキュメントでは、のように省略します。