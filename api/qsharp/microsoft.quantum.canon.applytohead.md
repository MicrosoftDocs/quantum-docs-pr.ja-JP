---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 4e627b467e9354e774c2ead8b89ddd3ff3a42ef7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841332"
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

## <a name="example"></a>例

次の Q # スニペットは同等です。

```qsharp
ApplyToHead(H, register);
H(Head(register));
```

## <a name="see-also"></a>参照

- [Microsoft. Canon. Applytoヘッド a](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [Microsoft. Canon. Applytoヘッド c](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [Microsoft. Canon. Applytoヘッド Ca](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)