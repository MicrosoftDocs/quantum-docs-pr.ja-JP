---
uid: Microsoft.Quantum.Arithmetic.ReversedOpBEC
title: ReversedOpBEC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReversedOpBEC
qsharp.summary: Given an operation that takes a big-endian input, returns a new operation that takes a little-endian input.
ms.openlocfilehash: 5e9aa6e6dfef74bca004170cf2b1cd91aa13f0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719678"
---
# <a name="reversedopbec-function"></a>ReversedOpBEC 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


ビッグエンディアン入力を受け取る操作が指定された場合、は、リトルエンディアン入力を受け取る新しい操作を返します。

```qsharp
function ReversedOpBEC (op : (Microsoft.Quantum.Arithmetic.BigEndian => Unit is Ctl)) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="op--bigendian--unit-ctl"></a>op: [bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian) => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

入力を元に戻す操作。



## <a name="output--littleendian--unit-ctl"></a>出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

入力をリトルエンディアンレジスタとして受け入れる新しい操作。

## <a name="see-also"></a>参照

- [ApplyReversedOpBEC です。](xref:Microsoft.Quantum.Arithmetic.ApplyReversedOpBEC)
- [ReversedOpBE です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBE)
- [ReversedOpBEA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBEA)
- [ReversedOpBECA です。](xref:Microsoft.Quantum.Arithmetic.ReversedOpBECA)