---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian ディアンユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721358"
---
# <a name="bigendian-user-defined-type"></a>BigEndian ディアンユーザー定義型

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


ビッグエンディアンの順序で符号なし整数をエンコードするレジスタ。 Qubit with index は、 `0` 符号なし整数の最上位ビットをエンコードします。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>解説

`BigEndian` `BE` ドキュメントでは、のように省略します。