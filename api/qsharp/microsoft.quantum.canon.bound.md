---
uid: Microsoft.Quantum.Canon.Bound
title: バインドされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716704"
---
# <a name="bound-function"></a>バインドされた関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>入力

### <a name="operations--t--unit-"></a>操作: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) []

指定された入力に対して実行される一連の操作。



## <a name="output--t--unit"></a>出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit) 

入力に基づいて指定された各操作を順番に実行する新しい操作。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列内の各操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Canon. BoundA](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft............... Fr-ca](xref:Microsoft.Quantum.Canon.BoundCA)