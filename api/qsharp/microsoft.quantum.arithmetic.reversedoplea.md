---
uid: Microsoft.Quantum.Arithmetic.ReversedOpLEA
title: ReversedOpLEA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpLEA
qsharp.summary: Given an operation that takes a little-endian input, returns a new operation that takes a big-endian input.
ms.openlocfilehash: eabeb8e068ef32cf6717efd6e818271a667b39b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719642"
---
# <a name="reversedoplea-function"></a>ReversedOpLEA 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


リトルエンディアン入力を受け取る操作が指定された場合、は、ビッグエンディアン入力を受け取る新しい操作を返します。

```qsharp
function ReversedOpLEA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj)) : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="op--littleendian--unit-adj"></a>op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

入力を元に戻す操作。



## <a name="output--bigendian--unit-adj"></a>出力: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞

ビッグエンディアンレジスタとしての入力を受け入れる新しい操作。

## <a name="see-also"></a>参照

- [ApplyReversedOpLEA です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpLEA)
- [ReversedOpLE です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLE)
- [ReversedOpLEC です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLEC)
- [ReversedOpLECA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpLECA)