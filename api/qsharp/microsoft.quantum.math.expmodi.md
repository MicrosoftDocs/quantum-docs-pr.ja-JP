---
uid: Microsoft.Quantum.Math.ExpModI
title: Modi 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857031"
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