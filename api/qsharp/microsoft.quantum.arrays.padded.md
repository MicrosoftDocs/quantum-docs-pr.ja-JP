---
uid: Microsoft.Quantum.Arrays.Padded
title: 埋め込み関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845563"
---
# <a name="padded-function"></a>埋め込み関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された値で指定した長さまで、に埋め込まれた配列を返します。

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="nelementstotal--int"></a>nElementsTotal: [Int](xref:microsoft.quantum.lang-ref.int)

埋め込まれた配列の長さ。 正の場合、 `inputArray` はヘッドに埋め込まれます。 負の値の場合、 `inputArray` は末尾に埋め込まれます。


### <a name="defaultelement--t"></a>defaultElement: ' t

要素の埋め込みに使用する既定値。


### <a name="inputarray--t"></a>inputArray: ' t []

値が出力配列の先頭にある配列。



## <a name="output--t"></a>出力: ' t []

`output` `inputArray` `defaultElement` がの長さになるまで、s に埋め込まれた配列。 `output``nElementsTotal`

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列要素の型。

## <a name="example"></a>例

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```