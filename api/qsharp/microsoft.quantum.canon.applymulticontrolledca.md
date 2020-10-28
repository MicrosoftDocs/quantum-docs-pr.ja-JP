---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717964"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


1つの操作の制御された複数のバージョンを適用します。
修飾子は、 `CA` single qubit 操作が制御可能で adjointable であることを示します。

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="singlycontrolledop--qubit--unit-adj"></a>Sing(Controlledop): [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

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

## <a name="references"></a>関連項目

- [*Michael、Isaac、語* 、量子計算、およびクォンタム情報](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>参照

- [Microsoft. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)