---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842093"
---
# <a name="rightshiftedl-function"></a>RightShiftedL 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


数値のビットごとの表現を指定されたビット数だけ右にシフトします。

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>入力

### <a name="value--bigint"></a>値: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ビットごとの表現を右にシフトする数値 (重要ではない)。


### <a name="amount--int"></a>amount: [Int](xref:microsoft.quantum.lang-ref.int)

を右にシフトするときに使用するビット数 `value` 。



## <a name="output--bigint"></a>出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ビットで右にシフトされたの値 `value` `amount` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```