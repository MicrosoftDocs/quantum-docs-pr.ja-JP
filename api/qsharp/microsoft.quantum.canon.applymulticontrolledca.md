---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841696"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


1つの操作の制御された複数のバージョンを適用します。
修飾子は、 `CA` single qubit 操作が制御可能で adjointable であることを示します。

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>Sing(Controlledop): [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

1つの qubit で制御される操作。
操作の引数の最初の qubit はコントロールであると想定され、残りはターゲット qubit と見なされます。
`ApplyMultiControlled` は常に `singlyControlledOp` 、長さが1以上の引数を使用してを呼び出します。


### <a name="ccnot--ccnotop"></a>ccnot: [Ccnotop](xref:Microsoft.Quantum.Canon.CCNOTop)

構築に使用する制御制御された非対応のゲート。


### <a name="controls--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

`singlyControlledOp`で制御される qubits。
の長さは `controls` 1 以上である必要があります。


### <a name="targets--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

に対して動作するターゲットの qubits `singlyControlledOp` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

この操作では、clean ancilla qubits のみを使用します。

説明とサーキットの図については、図4.10 のセクション4.3 を参照してください & 語

## <a name="references"></a>References

- [*Michael、Isaac、語*、量子計算、およびクォンタム情報](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>参照

- [Microsoft. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)