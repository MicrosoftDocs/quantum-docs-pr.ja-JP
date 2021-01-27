---
uid: Microsoft.Quantum.Math.ExpModL
title: 関数の集計関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 127f2e51e19c76f4f7973bf1ac2217d4fffd72f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848368"
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