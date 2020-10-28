---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719414"
---
# <a name="constantarray-function"></a>ConstantArray 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


指定された値と等しいすべての要素を使用して、指定された長さの配列を作成します。

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a>入力

### <a name="length--int"></a>長さ: [Int](xref:microsoft.quantum.lang-ref.int)

新しい配列の長さ。


### <a name="value--t"></a>値: ' t '

新しい配列の各要素の値。



## <a name="output--t"></a>出力: ' t []

`length`すべての要素がである、長さの新しい配列 `value` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

