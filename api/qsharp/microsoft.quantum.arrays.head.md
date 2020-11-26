---
uid: Microsoft.Quantum.Arrays.Head
title: Head 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 834cbe2384122463be6a0efcb6e09785aae9c092
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221115"
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