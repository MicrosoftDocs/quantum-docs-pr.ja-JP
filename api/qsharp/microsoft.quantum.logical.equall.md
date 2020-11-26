---
uid: Microsoft.Quantum.Logical.EqualL
title: すべての関数を返します。
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 395b8fedd3b3334939c2a4b5602ee19e0c6e34b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198114"
---
# <a name="equall-function"></a>すべての関数を返します。

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2つの入力が等しい場合にのみ true を返します。

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>入力

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

比較する最初の値。


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がに等しい場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a == b;
let cond = EqualL(a, b);
```