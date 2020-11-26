---
uid: Microsoft.Quantum.Arrays.Prefixes
title: プレフィックス関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220392"
---
# <a name="prefixes-function"></a>プレフィックス関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列を指定すると、そのすべてのプレフィックスが返されます。

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>説明

すべてのプレフィックスの配列を返します。最初の要素が配列全体になるまで、最初の要素のみが含まれています。

## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t []

要素の配列。



## <a name="output--t"></a>出力: ' t [] []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。