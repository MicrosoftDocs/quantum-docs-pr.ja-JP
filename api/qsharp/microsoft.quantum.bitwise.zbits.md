---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: 3ded981dc53236a48f1fb8f6ae12e39c17469447
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219449"
---
# <a name="zbits-function"></a>ZBits 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


P# li 演算子の配列の Z ビットを表す整数を返します。

```qsharp
function ZBits (paulis : Pauli[]) : Int
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]

整数として表現される、P# li 演算子の配列。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

$ をバイナリ表現 $ (p_ {62} \, p_ {61} \, \ ドット p_0) $ に $x 整数を指定 \, `paulis[i]` `PauliI` `PauliX` し `paulis[i]` `PauliY` `PauliZ` ます。がまたはの場合は $p _i = $0、がまたはの場合は $p _i = $1 になります。

## <a name="remarks"></a>解説

配列の長さが63より大きい場合、関数はをスローし `paulis` ます。

## <a name="see-also"></a>参照

- [Microsoft...... x ビット](xref:Microsoft.Quantum.Bitwise.XBits)