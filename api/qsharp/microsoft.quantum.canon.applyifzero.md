---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718062"
---
# <a name="applyifzero-operation"></a>ApplyIfZero 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


従来の結果値に対する条件付き操作を0に適用します。

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>説明

`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `Zero` ます。 `One`の場合、には何も起こりません `target` 。

## <a name="input"></a>入力

### <a name="result--__invalidresult__"></a>結果: __無効 <Result>__

Op が適用されるかどうかを制御する測定結果。


### <a name="op--t--unit"></a>op: t => [単位](xref:microsoft.quantum.lang-ref.unit) 

条件付きで適用する操作。


### <a name="target--t"></a>ターゲット: \

操作が適用される入力。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

条件付きで適用される操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft....。](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft....。](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)