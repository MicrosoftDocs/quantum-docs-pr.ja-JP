---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209861"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定されたビット数だけ左にある数値のビットごとの表現をシフトします。

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>入力

### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

ビットごとの表現を左にシフトする数値 (より大きい)。


### <a name="amount--int"></a>amount: [Int](xref:microsoft.quantum.lang-ref.int)

を左にシフトするときに使用するビット数 `value` 。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

ビットで左にシフトされたの値 `value` `amount` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```