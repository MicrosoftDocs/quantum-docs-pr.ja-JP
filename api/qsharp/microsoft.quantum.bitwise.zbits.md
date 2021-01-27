---
uid: Microsoft.Quantum.Bitwise.ZBits
title: ZBits 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: ZBits
qsharp.summary: Returns an integer representing the Z bits of an array of Pauli operators.
ms.openlocfilehash: d1ddc2a4cdbdfd3945885de856456b3108592594
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842057"
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