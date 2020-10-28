---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Applyto最も c 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717171"
---
# <a name="applytomostc-operation"></a>Applyto最も c 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


配列の最後の要素以外のすべてに操作を適用します。

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit-ctl"></a>op: ' t [] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

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
- [Microsoft. Canon. Applytoほとんどの Ca](xref:Microsoft.Quantum.Canon.ApplyToMostCA)