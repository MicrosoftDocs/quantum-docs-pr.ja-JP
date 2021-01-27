---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840276"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


複数の範囲のデカルト積の各インデックスに対して操作を適用します。

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>説明

`0..(bounds[0] - 1)`、、 `0..(bounds[1] - 1)` ...、のデカルト積の各要素に対して、反復的に操作を適用します。`0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>入力

### <a name="bounds--int"></a>境界: [Int](xref:microsoft.quantum.lang-ref.int)[]

反復処理する範囲を指定する配列。各範囲は整数長として指定されます。


### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit) 

指定されたデカルト積の各要素に対して呼び出される操作。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

操作を指定した `op` 場合、次の2つのスニペットは同等です。

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>参照

- [Microsoft. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)