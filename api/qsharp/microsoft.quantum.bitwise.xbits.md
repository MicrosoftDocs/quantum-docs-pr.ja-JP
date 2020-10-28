---
uid: Microsoft.Quantum.Bitwise.XBits
title: XBits 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: XBits
qsharp.summary: Returns an integer representing the X bits of an array of Pauli operators.
ms.openlocfilehash: 91619803c7efe56e617b16637f5302aa0b7978ec
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718562"
---
# <a name="xbits-function"></a>XBits 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パック [](https://nuget.org/packages/)


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