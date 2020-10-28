---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721334"
---
# <a name="bigendianaslittleendian-function"></a>BigEndianAsLittleEndian 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


Qubit の `BigEndian` 順序を逆にして、qubit レジスタを `LittleEndian` qubit レジスタに変換します。

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a>入力

### <a name="input--bigendian"></a>入力: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)

形式での qubit レジスタ `BigEndian` 。



## <a name="output--littleendian"></a>出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

形式での qubit レジスタ `LittleEndian` 。