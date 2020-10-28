---
uid: Microsoft.Quantum.Arrays.Merged
title: マージされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: da15a36f8f057cdc15062c96070ec21becc4794a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719011"
---
# <a name="merged-function"></a>マージされた関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


2つの並べ替えられた配列を指定した場合、両方のの要素が並べ替えられた順序で格納された単一の配列を返します。 Merge sort によって内部的に使用されます。

```qsharp
function Merged<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="comparison--tt---bool"></a>比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="left--t"></a>左: \ []




### <a name="right--t"></a>right: t []





## <a name="output--t"></a>出力: ' t []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

