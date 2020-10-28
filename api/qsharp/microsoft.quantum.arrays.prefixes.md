---
uid: Microsoft.Quantum.Arrays.Prefixes
title: プレフィックス関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718939"
---
# <a name="prefixes-function"></a>プレフィックス関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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