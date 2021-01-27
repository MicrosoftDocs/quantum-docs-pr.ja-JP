---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841819"
---
# <a name="applyifelsebc-operation"></a>ApplyIfElseBC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


クラシックビットの値に応じて、制御可能な2つの操作のいずれか1つを適用します。

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>説明

が指定され `bit` `trueOp` ている `trueInput` 場合は、がのときの入力としての操作を適用 `bit` し、 `true` がのときに適用され `falseOp(falseInput)` `bit` `false` ます。

## <a name="input"></a>入力

### <a name="bit--bool"></a>bit: [Bool](xref:microsoft.quantum.lang-ref.bool)

またはが適用されるかどうかを判断するために使用されるブール値 `trueOp` `falseOp` 。


### <a name="trueop--t--unit--is-ctl"></a>trueOp: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

がの場合に適用される制御可能 `bit` な操作 `true` 。


### <a name="trueinput--t"></a>trueInput: t

がの場合に提供される入力 `trueOp` `bit` `true` 。


### <a name="falseop--u--unit--is-ctl"></a>False Op: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

がの場合に適用される制御可能 `bit` な操作 `false` 。


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