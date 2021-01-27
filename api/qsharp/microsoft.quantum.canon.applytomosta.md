---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850585"
---
# <a name="applytomosta-operation"></a>ApplyToMostA 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最後の要素以外のすべてに操作を適用します。

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-adj"></a>op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

適用する操作。


### <a name="targets--t"></a>ターゲット: ' t []

ターゲットの配列。最後のすべてのが適用され `op` ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft...。](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft....。](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. Canon. Applytoほとんどの Ca](xref:Microsoft.Quantum.Canon.ApplyToMostCA)