---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 2b7321a6c385e2d98a0e91a8f58091ea8dc43ff4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208603"
---
# <a name="applytoheadc-operation"></a>ApplyToHeadC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最初の要素に操作を適用します。

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Head(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-ctl"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

適用する操作。


### <a name="targets--t"></a>ターゲット: ' t []

最初のが適用されるターゲットの配列 `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. ApplyToHead](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [Microsoft. Canon. Applytoヘッド a](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. Canon. Applytoヘッド Ca](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)