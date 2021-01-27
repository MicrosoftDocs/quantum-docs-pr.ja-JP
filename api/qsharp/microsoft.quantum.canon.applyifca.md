---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b9d5e2c6868dc7b876917abf28f68bb5d0d0f2f7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844995"
---
# <a name="applyifca-operation"></a>ApplyIfCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


古典的なビットに対して条件付きのユニタリ操作を適用します。

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。 `false`の場合、には何も起こりません `target` 。
サフィックスは、 `CA` 適用される操作が、ユニタリ (制御可能および adjointable) であることを示します。

## <a name="input"></a>入力

### <a name="op--t--unit--is-adj--ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

条件付きで適用する操作。


### <a name="bit--bool"></a>bit: [Bool](xref:microsoft.quantum.lang-ref.bool)

op が適用されるかどうかを制御するブール値。


### <a name="target--t"></a>ターゲット: \

操作が適用される入力。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

条件付きで適用される操作の入力型。

## <a name="example"></a>例

次の例では、値の配列として指定された古典的なビット文字列によって表される計算基準の状態に qubits のレジスタを準備し `Bool` ます。

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a>参照

- [Microsoft. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)