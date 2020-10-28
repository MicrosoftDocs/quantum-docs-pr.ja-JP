---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: Applyiの Ec 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 9a2e020c596b02d9cb38309d02ca02056c1dec75
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718090"
---
# <a name="applyifonec-operation"></a>Applyiの Ec 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


古典的な結果値が1であるという制御可能な操作を適用します。

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a>説明

`op`がの場合、操作と結果の値がに適用され `result` `op` `target` `result` `One` ます。 `Zero`の場合、には何も起こりません `target` 。
サフィックスは、 `C` 適用される操作が制御可能であることを示します。

## <a name="input"></a>入力

### <a name="result--__invalidresult__"></a>結果: __無効 <Result>__

Op が適用されるかどうかを制御する測定結果。


### <a name="op--t--unit-ctl"></a>op: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

条件付きで適用する操作。


### <a name="target--t"></a>ターゲット: \

操作が適用される入力。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

条件付きで適用される操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. Applyi(Ec)](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [Microsoft. Canon. Applyi(Ea)](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [Microsoft. ApplyIfOneCA](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)