---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: ce08907646c3210f76244f29aa0d936e2bd6ee43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718202"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


従来のビットの値に応じて、2つの adjointable 操作のいずれかを適用します。

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit
```


## <a name="description"></a>説明

が指定され `bit` `trueOp` ている `trueInput` 場合は、がのときの入力としての操作を適用 `bit` し、 `true` がのときに適用され `falseOp(falseInput)` `bit` `false` ます。

## <a name="input"></a>入力

### <a name="bit--bool"></a>bit: [Bool](xref:microsoft.quantum.lang-ref.bool)

またはが適用されるかどうかを判断するために使用されるブール値 `trueOp` `falseOp` 。


### <a name="trueop--t--unit-adj"></a>trueOp: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

がの場合に適用される adjointable 操作 `bit` `true` 。


### <a name="trueinput--t"></a>trueInput: t

がの場合に提供される入力 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit-adj"></a>False Op: ' U => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

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