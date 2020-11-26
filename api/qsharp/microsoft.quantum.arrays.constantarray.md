---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210065"
---
# <a name="constantarray-function"></a>ConstantArray 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

