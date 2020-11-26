---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLE
title: ReversedOpLE 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLE
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: 91b98663028b8a1d54c546e70d8bfe603d71d041
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222254"
---
# <a name="reversedople-function"></a>ReversedOpLE 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。

```qsharp
function ReversedOpLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit)
```


## <a name="input"></a>入力

### <a name="op--littleendian--unit"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

入力を元に戻す操作。



## <a name="output--bigendian--unit"></a>出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) 

ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。

## <a name="see-also"></a>参照

- [ApplyReversedOpLE です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLE)
- [ReversedOpLEA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEA)
- [ReversedOpLEC です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [ReversedOpLECA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)