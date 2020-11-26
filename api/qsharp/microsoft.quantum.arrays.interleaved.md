---
uid: Microsoft.Quantum.Arrays.Interleaved
title: インターリーブ関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220962"
---
# <a name="interleaved-function"></a>インターリーブ関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


(ほぼ) 同じサイズの2つの配列を相互に保持します。

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>説明

この関数は、2つの配列のインターリーブを返します。最初の配列の最初の要素、2番目の配列の最初の要素、およびなどが含まれます。

最初の配列は、2番目の配列と同じ長さであるか、または1つ以上の要素を持つことができます。

## <a name="input"></a>入力

### <a name="first--t"></a>最初: ' t []

インターリーブされる最初の配列。


### <a name="second--t"></a>2番目: ' t []

インターリーブする2番目の配列。



## <a name="output--t"></a>出力: ' t []

インターリーブ配列

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

およびの各要素の型 `first` `second` 。