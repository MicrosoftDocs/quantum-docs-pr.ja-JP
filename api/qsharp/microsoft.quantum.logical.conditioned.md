---
uid: Microsoft.Quantum.Logical.Conditioned
title: 条件付き関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198488"
---
# <a name="conditioned-function"></a>条件付き関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


ブール条件の値に応じて、2つの値のいずれかを返します。

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>入力

### <a name="condition--bool"></a>条件: [Bool](xref:microsoft.quantum.lang-ref.bool)

返される入力を制御するために使用される条件。


### <a name="iftrue--t"></a>ifTrue: ' t '

がの場合に返される `condition` 値 `true` 。


### <a name="iffalse--t"></a>ifFalse: t

がの場合に返される `condition` 値 `false` 。



## <a name="output--t"></a>出力: t

`ifTrue``condition`が `true` の場合は `ifFalse` 。それ以外の場合は。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

演算子とは異なり `?|` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。

ショートサーキットの動作は、次のようになります。

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```