---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 969be01204bad497496ff24cb64213f5fe1f089b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209759"
---
# <a name="xbits-function"></a>XBits 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


P# li 演算子の配列の X ビットを表す整数を返します。

```qsharp
function XBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]

整数として表現される、P# li 演算子の配列。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

$ をバイナリ表現 $ (p_ {62} \, p_ {61} \, \ ドット p_0) $ に $x 整数を指定 \, `paulis[i]` `PauliI` `PauliZ` し `paulis[i]` `PauliX` `PauliY` ます。がまたはの場合は $p _i = $0、がまたはの場合は $p _i = $1 になります。

## <a name="remarks"></a>解説

配列の長さが63より大きい場合、関数はをスローし `paulis` ます。

## <a name="see-also"></a>参照

- [Microsoft では、ビットごとの ZBits](xref:Microsoft.Quantum.Bitwise.ZBits)