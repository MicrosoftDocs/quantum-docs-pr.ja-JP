---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846172"
---
# <a name="emptyarray-function"></a>EmptyArray 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された型の空の配列を返します。

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>出力: ' TElement []

空の配列。

## <a name="type-parameters"></a>型パラメーター

### <a name="telement"></a>' TElement '

配列の要素の型。

## <a name="example"></a>例

```qsharp
let empty = EmptyArray<Int>();
```