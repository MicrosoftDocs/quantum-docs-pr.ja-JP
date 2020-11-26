---
uid: Microsoft.Quantum.Math.ExpModI
title: Modi 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228492"
---
# <a name="expmodi-function"></a>Modi 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


指定された剰余に関して、指定された指数で累乗された整数を返します。

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>説明

$ $X ドルで底を示し、$ と $p を $N $ で累乗してみましょう。
関数は $x ^ p/演算子名 {mod} N $ を返します。

$N $, $x $ は正の値で、累乗は負ではないと想定しています。

## <a name="input"></a>入力

### <a name="expbase--int"></a>底: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>剰余: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>解説

は、ではなく、のビット数に比例 `power` `power` します。