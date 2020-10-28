---
uid: Microsoft.Quantum.Logical.Conditioned
title: 条件付き関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720787"
---
# <a name="conditioned-function"></a>条件付き関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パック [](https://nuget.org/packages/)


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