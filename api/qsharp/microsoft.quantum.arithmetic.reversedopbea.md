---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 69fd4401e6862a3a6afaa51fb5b8a3592768bb42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222305"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ビッグエンディアン入力を受け取る操作が指定された場合、は、リトルエンディアン入力を受け取る新しい操作を返します。

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="op--bigendian--unit--is-adj"></a>op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

入力を元に戻す操作。



## <a name="output--littleendian--unit--is-adj"></a>出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞

入力をリトルエンディアンレジスタとして受け入れる新しい操作。

## <a name="see-also"></a>参照

- [ApplyReversedOpBEA です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [ReversedOpBE です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [ReversedOpBEC です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [ReversedOpBECA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)