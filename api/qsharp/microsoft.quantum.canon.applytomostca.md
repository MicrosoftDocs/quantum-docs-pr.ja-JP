---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Applytoall Ca 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717166"
---
# <a name="applytomostca-operation"></a>Applytoall Ca 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


配列の最後の要素以外のすべてに操作を適用します。

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit-adj--ctl"></a>op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl

適用する操作。


### <a name="targets--t"></a>ターゲット: ' t []

ターゲットの配列。最後のすべてのが適用され `op` ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft....。](xref:Microsoft.Quantum.Canon.ApplyToMostC)