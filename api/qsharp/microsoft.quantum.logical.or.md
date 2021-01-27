---
uid: Microsoft.Quantum.Logical.Or
title: Or 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848477"
---
# <a name="or-function"></a>Or 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの値の論理和を返します。

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a>入力

### <a name="a--bool"></a>a: [Bool](xref:microsoft.quantum.lang-ref.bool)

考慮される最初の値。


### <a name="b--bool"></a>b: [Bool](xref:microsoft.quantum.lang-ref.bool)

考慮する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`またはのいずれか `b` がの場合にのみ `true` 。

## <a name="remarks"></a>解説

演算子とは異なり `or` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。

ショートサーキットの動作は、次のようになります。

```qsharp
let x = a or b;
let x = Or(a, b);
```