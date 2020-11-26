---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209776"
---
# <a name="rightshiftedi-function"></a>RightShiftedI 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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