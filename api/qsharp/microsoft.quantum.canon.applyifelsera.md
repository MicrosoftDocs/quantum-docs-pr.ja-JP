---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 3ebd09b1e5876ff397f3524ba828ba26a271e91e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218599"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


従来の結果の値に応じて、2つの adjointable 操作のいずれかを適用します。

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a>説明

結果が返された場合 `result` 、 `zeroOp` `zeroInput` は、がと等しいときにを入力として操作を適用し、when にを `result` 適用し `Zero` `oneOp(oneInput)` `result == One` ます。

## <a name="input"></a>入力

### <a name="result--__invalidresult__"></a>結果:__無効 <Result>__

またはが適用されているかどうかを判断するために使用される測定結果 `zeroOp` `oneOp` 。


### <a name="zeroop--t--unit--is-adj"></a>zeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

に適用される adjointable 操作 `result == Zero` 。


### <a name="zeroinput--t"></a>ゼロ入力: ' t '

時に提供される入力 `zeroOp` `result == Zero` 。


### <a name="oneop--u--unit--is-adj"></a>oneOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

に適用される adjointable 操作 `result == One` 。


### <a name="oneinput--u"></a>oneInput: ' U

時に提供される入力 `oneOp` `result == One` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

`zeroOp`条件付きで適用される操作の入力型。
### <a name="u"></a>' U

`oneOp`条件付きで適用される操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft.....。](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft... ".."](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)