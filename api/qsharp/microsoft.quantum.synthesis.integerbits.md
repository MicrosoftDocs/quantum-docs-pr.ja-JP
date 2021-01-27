---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: 整数のビット関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855399"
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

## <a name="example"></a>例

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```