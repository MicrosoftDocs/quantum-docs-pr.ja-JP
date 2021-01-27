---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844982"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


従来のビットの値に応じて、2つの adjointable 操作のいずれかを適用します。

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>説明

が指定され `bit` `trueOp` ている `trueInput` 場合は、がのときの入力としての操作を適用 `bit` し、 `true` がのときに適用され `falseOp(falseInput)` `bit` `false` ます。

## <a name="input"></a>入力

### <a name="bit--bool"></a>bit: [Bool](xref:microsoft.quantum.lang-ref.bool)

またはが適用されるかどうかを判断するために使用されるブール値 `trueOp` `falseOp` 。


### <a name="trueop--t--unit--is-adj"></a>trueOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

がの場合に適用される adjointable 操作 `bit` `true` 。


### <a name="trueinput--t"></a>trueInput: t

がの場合に提供される入力 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit--is-adj"></a>False Op: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

がの場合に適用される adjointable 操作 `bit` `false` 。


### <a name="falseinput--u"></a>False 入力: ' U

がの場合に提供される入力 `falseOp` `bit` `false` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

`trueOp`条件付きで適用される操作の入力型。
### <a name="u"></a>' U

`falseOp`条件付きで適用される操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft.....。](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft... ".."](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)