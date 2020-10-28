---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718579"
---
# <a name="rightshiftedi-function"></a>RightShiftedI 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パック [](https://nuget.org/packages/)


数値のビットごとの表現を指定されたビット数だけ右にシフトします。

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>入力

### <a name="value--int"></a>値: [Int](xref:microsoft.quantum.lang-ref.int)

ビットごとの表現を右にシフトする数値 (重要ではない)。


### <a name="amount--int"></a>amount: [Int](xref:microsoft.quantum.lang-ref.int)

を右にシフトするときに使用するビット数 `value` 。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

ビットで右にシフトされたの値 `value` `amount` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```