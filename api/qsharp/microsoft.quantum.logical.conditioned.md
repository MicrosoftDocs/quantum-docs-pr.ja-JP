---
uid: Microsoft.Quantum.Logical.Conditioned
title: 条件付き関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817301"
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

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```