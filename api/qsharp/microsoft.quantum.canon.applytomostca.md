---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: Applytoall Ca 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841309"
---
# <a name="applytomostca-operation"></a>Applytoall Ca 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最後の要素以外のすべてに操作を適用します。

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Most(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit--is-adj--ctl"></a>op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

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