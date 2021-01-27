---
uid: Microsoft.Quantum.Arrays.Merged
title: マージされた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Merged
qsharp.summary: Given two sorted arrays, returns a single array containing the elements of both in sorted order. Used internally by merge sort.
ms.openlocfilehash: 262e7450188370212a7e2a57bf15e9f8ab162814
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845611"
---
# <a name="merged-function"></a>マージされた関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

