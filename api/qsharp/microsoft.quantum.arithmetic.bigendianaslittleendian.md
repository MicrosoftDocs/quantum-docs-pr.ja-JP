---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 5f5d7dc6e08a13fbdc45f9d11c93c29cfcf90bf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223631"
---
# <a name="bigendianaslittleendian-function"></a>BigEndianAsLittleEndian 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubit の `BigEndian` 順序を逆にして、qubit レジスタを `LittleEndian` qubit レジスタに変換します。

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a>入力

### <a name="input--bigendian"></a>入力: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)

形式での qubit レジスタ `BigEndian` 。



## <a name="output--littleendian"></a>出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

形式での qubit レジスタ `LittleEndian` 。