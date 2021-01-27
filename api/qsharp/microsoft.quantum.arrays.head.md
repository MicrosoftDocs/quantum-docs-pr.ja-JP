---
uid: Microsoft.Quantum.Arrays.Head
title: Head 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 6dd181914b5ed3ef16a02b31cb6131daf2a34e19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848569"
---
# <a name="head-function"></a>Head 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最初の要素を返します。

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>入力

### <a name="array--a"></a>配列: ' A []

最初の要素を取得する対象の配列。 配列の長さは少なくとも1である必要があります。



## <a name="output--a"></a>出力: ' A

配列の最初の要素。

## <a name="type-parameters"></a>型パラメーター

### <a name="a"></a>' A

配列要素の型。