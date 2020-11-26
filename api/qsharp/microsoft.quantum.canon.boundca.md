---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216883"
---
# <a name="boundca-function"></a>BoundCA 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。
修飾子は、 `CA` 配列内のすべての操作が adjointable および制御可能であることを示します。

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="operations--t--unit--is-adj--ctl"></a>操作: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl []

指定された入力に対して実行される一連の操作。



## <a name="output--t--unit--is-adj--ctl"></a>出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です

入力に基づいて指定された各操作を順番に実行する新しい操作。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列内の各操作が動作するターゲット。

## <a name="see-also"></a>参照

- [Microsoft......](xref:Microsoft.Quantum.Canon.Bound)