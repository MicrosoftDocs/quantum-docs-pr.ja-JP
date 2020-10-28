---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717451"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


配列の特定の要素に操作を適用します。

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>説明

指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。

## <a name="input"></a>入力

### <a name="op--t--unit-ctl"></a>op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

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
- [Microsoft. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)