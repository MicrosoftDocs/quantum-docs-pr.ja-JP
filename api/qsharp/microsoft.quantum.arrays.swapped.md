---
uid: Microsoft.Quantum.Arrays.Swapped
title: スワップした関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850950"
---
# <a name="swapped-function"></a>スワップした関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列内の2つの要素のスワップを適用します。

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="firstindex--int"></a>firstIndex: [Int](xref:microsoft.quantum.lang-ref.int)

交換される最初の要素のインデックス。


### <a name="secondindex--int"></a>次のインデックス: [Int](xref:microsoft.quantum.lang-ref.int)

スワップする2番目の要素のインデックス。


### <a name="arr--t"></a>arr: ' t []

交換する要素を含む配列。



## <a name="output--t"></a>出力: ' t []

インプレーススワップが適用された配列。

## <a name="example"></a>例

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

