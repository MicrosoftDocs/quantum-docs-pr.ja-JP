---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719174"
---
# <a name="indexof-function"></a>IndexOf 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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

