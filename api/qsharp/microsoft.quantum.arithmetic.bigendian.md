---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian ディアンユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223665"
---
# <a name="bigendian-user-defined-type"></a>BigEndian ディアンユーザー定義型

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ビッグエンディアンの順序で符号なし整数をエンコードするレジスタ。 Qubit with index は、 `0` 符号なし整数の最上位ビットをエンコードします。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>解説

`BigEndian` `BE` ドキュメントでは、のように省略します。