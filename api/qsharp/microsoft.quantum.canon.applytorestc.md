---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850491"
---
# <a name="applytorestc-operation"></a>ApplyToRestC 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最初の要素以外のすべてに操作を適用します。

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-ctl"></a>op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です

適用する操作。


### <a name="targets--t"></a>ターゲット: ' t []

ターゲットの配列。すべてのものが最初に適用され `op` ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. ApplyToRest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)