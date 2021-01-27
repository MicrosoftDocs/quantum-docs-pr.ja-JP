---
uid: Microsoft.Quantum.Arrays.Interleaved
title: インターリーブ関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848106"
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

## <a name="example"></a>例

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```