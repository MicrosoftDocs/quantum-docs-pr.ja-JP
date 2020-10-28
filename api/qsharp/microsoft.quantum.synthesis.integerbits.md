---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: 整数のビット関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719846"
---
# <a name="integerbits-function"></a>整数のビット関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パック [](https://nuget.org/packages/)


整数のビットが設定されているすべての位置を返します。

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>入力

### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

負でない数値。


### <a name="length--int"></a>長さ: [Int](xref:microsoft.quantum.lang-ref.int)

のバイナリ展開に含まれるビット数 `value` 。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

すべての `value` ビットが位置することを考慮 `length - 1` したバイナリ展開の1であるすべてのビット位置 (0 から始まる) を含む配列。  配列内のすべての位置は、位置によって昇順に並べ替えられます。