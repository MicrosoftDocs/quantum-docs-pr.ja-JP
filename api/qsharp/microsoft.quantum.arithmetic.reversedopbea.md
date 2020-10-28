---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEA
title: ReversedOpBEA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEA
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: b2418911e71c0b98e1a78247b2ae066887d89cd8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719695"
---
# <a name="reversedopbea-function"></a>ReversedOpBEA 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


ビッグエンディアン入力を受け取る操作が指定された場合、は、リトルエンディアン入力を受け取る新しい操作を返します。

```qsharp
function ReversedOpBEA (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="op--bigendian--unit-adj"></a>op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞

入力を元に戻す操作。



## <a name="output--littleendian--unit-adj"></a>出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

入力をリトルエンディアンレジスタとして受け入れる新しい操作。

## <a name="see-also"></a>参照

- [ApplyReversedOpBEA です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEA)
- [ReversedOpBE です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [ReversedOpBEC です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEC)
- [ReversedOpBECA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)