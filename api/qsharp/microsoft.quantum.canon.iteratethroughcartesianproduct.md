---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716037"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


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



## <a name="see-also"></a>参照

- [Microsoft. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)