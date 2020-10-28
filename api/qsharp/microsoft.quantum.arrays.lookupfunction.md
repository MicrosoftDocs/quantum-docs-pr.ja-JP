---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719071"
---
# <a name="lookupfunction-function"></a>LookupFunction 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列が指定されている場合、その配列の要素を返す関数を返します。

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t []

参照関数として表現される配列。



## <a name="output--int---t"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int) -> t

`f`そのような関数 `f(idx) == f[idx]` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

参照関数として表される配列の要素の型。

## <a name="remarks"></a>解説

この関数は、 `Int -> 'T` 引数として関数を受け取る関数や操作と相互運用する場合に主に役立ちます。 これは、たとえば、ジェネレーター表現ライブラリ内で、配列全体をメモリに記録する必要がないようにするために関数が使用される場合などに共通します。