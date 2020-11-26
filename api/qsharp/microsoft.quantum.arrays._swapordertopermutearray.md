---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221710"
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

## <a name="remarks"></a>解説

## <a name="psuedocode"></a>Psuedocode

(インデックスが 0.. Length (Neの場合)-1) {while neの [index]! = index {Switch Neder [index] (ne、neて [index]]}})