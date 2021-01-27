---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: 6dfa2a5cf88029ac772b09bc2d36a5f19ef37a14
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844950"
---
# <a name="applyifelserca-operation"></a>ApplyIfElseRCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


古典的な結果の値に応じて、2つのいずれかのユニタリ操作を適用します。

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

結果が返された場合 `result` 、 `zeroOp` `zeroInput` は、がと等しいときにを入力として操作を適用し、when にを `result` 適用し `Zero` `oneOp(oneInput)` `result == One` ます。

## <a name="input"></a>入力

### <a name="result--__invalidresult__"></a>結果:__無効 <Result>__

またはが適用されているかどうかを判断するために使用される測定結果 `zeroOp` `oneOp` 。


### <a name="zeroop--t--unit--is-adj--ctl"></a>zeroOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

の場合に適用される、ユニタリ操作 `result == Zero` 。


### <a name="zeroinput--t"></a>ゼロ入力: ' t '

時に提供される入力 `zeroOp` `result == Zero` 。


### <a name="oneop--u--unit--is-adj--ctl"></a>oneOp: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

の場合に適用される、ユニタリ操作 `result == One` 。


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