---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844539"
---
# <a name="bounda-function"></a>BoundA

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。
修飾子は、 `A` 配列内のすべての操作が adjointable であることを示します。

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>入力

### <a name="operations--t--unit--is-adj"></a>操作: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 []

指定された入力に対して実行される一連の操作。



## <a name="output--t--unit--is-adj"></a>出力: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です

入力に基づいて指定された各操作を順番に実行する新しい操作。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列内の各操作が動作するターゲット。

## <a name="example"></a>例

同等のものを次に示します。

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

and

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>参照

- [Microsoft......](xref:Microsoft.Quantum.Canon.Bound)