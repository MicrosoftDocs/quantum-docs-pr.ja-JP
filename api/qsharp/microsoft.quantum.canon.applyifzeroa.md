---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: Applyifゼロ操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: ab5b05791213da7c8bee5915764c342cb0bed851
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218497"
---
# <a name="applyifzeroa-operation"></a>Applyifゼロ操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


従来の結果値が0である adjointable 操作を適用します。

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a>説明

`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `Zero` ます。 `One`の場合、には何も起こりません `target` 。
サフィックスは、 `A` 適用される操作が adjointable であることを示します。

## <a name="input"></a>入力

### <a name="result--__invalidresult__"></a>結果:__無効 <Result>__

Op が適用されるかどうかを制御する測定結果。


### <a name="op--t--unit--is-adj"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

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