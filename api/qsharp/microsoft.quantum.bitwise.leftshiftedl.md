---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842152"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL 関数

名前空間: [Microsoft. Quantum. ビット](xref:Microsoft.Quantum.Bitwise)処理

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```