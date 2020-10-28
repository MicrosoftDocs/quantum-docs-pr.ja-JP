---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718634"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パック [](https://nuget.org/packages/)


指定されたビット数だけ左にある数値のビットごとの表現をシフトします。

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>入力

### <a name="value--bigint"></a>値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ビットごとの表現を左にシフトする数値 (より大きい)。


### <a name="amount--int"></a>amount: [Int](xref:microsoft.quantum.lang-ref.int)

を左にシフトするときに使用するビット数 `value` 。



## <a name="output--bigint"></a>出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ビットで左にシフトされたの値 `value` `amount` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```