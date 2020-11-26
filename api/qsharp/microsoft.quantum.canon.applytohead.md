---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217341"
---
# <a name="applytohead-operation"></a>ApplyToHead 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最初の要素に操作を適用します。

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit"></a>op: t => [単位](xref:microsoft.quantum.lang-ref.unit) 

適用する操作。


### <a name="targets--t"></a>ターゲット: ' t []

最初のが適用されるターゲットの配列 `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. Applytoヘッド a](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. Canon. Applytoヘッド c](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Canon. Applytoヘッド Ca](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)