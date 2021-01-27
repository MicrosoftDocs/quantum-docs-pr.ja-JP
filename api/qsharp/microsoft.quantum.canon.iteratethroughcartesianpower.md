---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840296"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


整数範囲のデカルト乗の各インデックスに演算を適用します。

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>説明

範囲のデカルト乗の各要素に対して、反復的に操作を適用 `0..(bound - 1)` します。

## <a name="input"></a>入力

### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

範囲が発生する必要があるデカルト指数 `0..(bound - 1)` 。


### <a name="bound--int"></a>バインド済み: [Int](xref:microsoft.quantum.lang-ref.int)

反復処理する範囲を指定します。範囲の長さとして指定します。


### <a name="op--int--unit"></a>op: [Int](xref:microsoft.quantum.lang-ref.int)[] => [単位](xref:microsoft.quantum.lang-ref.unit) 

指定されたデカルト乗の各要素に対して呼び出される操作。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>例

操作を指定した `op` 場合、次の2つのスニペットは同等です。

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>参照

- [Microsoft. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)