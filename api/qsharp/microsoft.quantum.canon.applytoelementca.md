---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208858"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の特定の要素に操作を適用します。

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-adj--ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

適用する操作。


### <a name="index--int"></a>index: [Int](xref:microsoft.quantum.lang-ref.int)

ターゲットの配列のインデックス。


### <a name="targets--t"></a>ターゲット: ' t []

に対して可能なターゲットの配列 `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- ["Microsoft....."](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)