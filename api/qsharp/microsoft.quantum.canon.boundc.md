---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716667"
---
# <a name="boundc-function"></a>BoundC 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パック [](https://nuget.org/packages/)


1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。
修飾子は、 `C` 配列内のすべての操作が制御可能であることを示します。

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>入力

### <a name="operations--t--unit-ctl"></a>操作: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl []

指定された入力に対して実行される一連の操作。



## <a name="output--t--unit-ctl"></a>出力: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl

入力に基づいて指定された各操作を順番に実行する新しい操作。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列内の各操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft......](xref:Microsoft.Quantum.Canon.Bound)