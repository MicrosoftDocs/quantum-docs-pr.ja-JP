---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalI
title: コンピューターの Procali 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalI
qsharp.summary: Computes the reciprocal 1/x for an unsigned integer x using integer division. The result, interpreted as an integer, will be `floor(2^(2*n-1) / x)`.
ms.openlocfilehash: c28027f7a2533885102a54a028bec37eb608f2b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846718"
---
# <a name="computereciprocali-operation"></a>コンピューターの Procali 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


整数除算を使用して、符号なし整数 x の逆数 1/x を計算します。 整数として解釈される結果はになり `floor(2^(2*n-1) / x)` ます。

```qsharp
operation ComputeReciprocalI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

n ビット符号なし整数


### <a name="result--littleendian"></a>結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

2n ビット出力は、最初に $ \ket $ にある必要があり {0} ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

入力 x = 0 の場合、出力はすべて1になります。