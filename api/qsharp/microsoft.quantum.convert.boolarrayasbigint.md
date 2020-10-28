---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: ブール Arrayasbigint 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713615"
---
# <a name="boolarrayasbigint-function"></a>ブール Arrayasbigint 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


指定したブール値の配列を等価の大きい整数に変換します。
配列の0要素は、大きい整数の最下位ビットです。

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a>入力

### <a name="a--bool"></a>a: [Bool](xref:microsoft.quantum.lang-ref.bool)[]





## <a name="output--bigint"></a>出力: [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>解説

詳細については、「 [C# BigInteger コンストラクター](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 」を参照してください。