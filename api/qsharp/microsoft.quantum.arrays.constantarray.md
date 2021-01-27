---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846217"
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



## <a name="example"></a>例

次のコードでは、3つのブール値の配列が作成されます。それぞれが次の値に等しく `true` なります。

```qsharp
let array = ConstantArray(3, true);
```