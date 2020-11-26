---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: 整数のビット関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231094"
---
# <a name="integerbits-function"></a>整数のビット関数

名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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