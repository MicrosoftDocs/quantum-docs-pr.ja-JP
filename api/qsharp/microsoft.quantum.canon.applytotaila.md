---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: 操作の適用
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716975"
---
# <a name="applytotaila-operation"></a>操作の適用

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


配列の最後の要素に操作を適用します。

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a>説明

指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。

## <a name="input"></a>入力

### <a name="op--t--unit-adj"></a>op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞

適用する操作。


### <a name="targets--t"></a>ターゲット: ' t []

最後のが適用されるターゲットの配列 `op` 。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

適用する操作の入力型。

## <a name="see-also"></a>参照

- [Microsoft. Canon. 適用](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [Microsoft......。](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [Microsoft... の証明機関](xref:Microsoft.Quantum.Canon.ApplyToTailCA)