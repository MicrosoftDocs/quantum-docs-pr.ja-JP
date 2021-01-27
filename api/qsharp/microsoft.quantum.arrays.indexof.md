---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848520"
---
# <a name="indexof-function"></a>IndexOf 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された述語を満たす配列内の最初の要素の最初のインデックスを返します。 そのような要素が存在しない場合は、-1 を返します。

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a>入力

### <a name="predicate--t---bool"></a>述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)

配列の要素に対して動作する述語関数。


### <a name="arr--t"></a>arr: ' t []

指定された述語を使用して検索される配列。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

`idx`が true であるような最小のインデックス `predicate(arr[idx])` 。そのような要素が存在しない場合は-1。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="example"></a>例

は、 `IsEven : Int -> Bool` 入力が偶数の場合にのみを返す関数であるとし `true` ます。 次に、これをと共に使用して、 `IndexOf` 配列内の最初の偶数の要素を検索できます。

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```