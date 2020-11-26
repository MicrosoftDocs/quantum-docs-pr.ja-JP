---
uid: Microsoft.Quantum.Math.ExpModL
title: 関数の集計関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210750"
---
# <a name="expmodl-function"></a>関数の集計関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された剰余に関して、指定された指数で累乗された整数を返します。

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>説明

$ $X ドルで底を示し、$ と $p を $N $ で累乗してみましょう。
関数は $x ^ p/演算子名 {mod} N $ を返します。

$N $, $x $ は正の値で、累乗は負ではないと想定しています。

## <a name="input"></a>入力

### <a name="expbase--bigint"></a>基本: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>power: [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>剰余: [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>解説

は、ではなく、のビット数に比例 `power` `power` します。