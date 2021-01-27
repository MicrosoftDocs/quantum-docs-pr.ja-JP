---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: ff8e4e23dde7d69f93054a275548ded49d5b0bfb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846292"
---
# <a name="_swapordertopermutearray-function"></a>_SwapOrderToPermuteArray 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


順序付けされた配列を生成するために、配列内の順序要素を交換する必要があることを返します。
スワップが行われることを前提としています。

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a>入力

### <a name="neworder--int"></a>Ne・ Der: [Int](xref:microsoft.quantum.lang-ref.int)[]

新しい配列のインデックスの順列を含む配列。 $ Elements $n が必要です。各要素は $0 $ から $n-$1 の一意の整数です。



## <a name="output--intint"></a>出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

組は、スワップする2つのインデックスを表します。 スワップは最低のインデックスから開始されます。

## <a name="example"></a>例

```qsharp
// The following returns [(0, 5),(0, 4),(0, 1),(0, 3)];
let swapOrder = _SwapOrderToPermuteArray([5, 3, 2, 0, 1, 4]);
```

## <a name="remarks"></a>解説

## <a name="psuedocode"></a>Psuedocode

(インデックスが 0.. Length (Neの場合)-1) {while neの [index]! = index {Switch Neder [index] (ne、neて [index]]}})