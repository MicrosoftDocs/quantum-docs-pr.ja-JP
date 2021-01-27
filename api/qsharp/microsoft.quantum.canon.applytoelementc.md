---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850741"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の特定の要素に操作を適用します。

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>説明

指定された操作 `op` 、インデックス `index` 、およびターゲットの配列が適用され `targets` `op(targets[index])` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

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