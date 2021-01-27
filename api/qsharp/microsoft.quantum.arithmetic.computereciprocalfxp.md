---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: コンピューターの Procalfxp 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843258"
---
# <a name="computereciprocalfxp-operation"></a>コンピューターの Procalfxp 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


$ 1/x $ を計算します (固定小数点数 $x $)。

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="x--fixedpoint"></a>x: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

反転する固定小数点数。


### <a name="result--fixedpoint"></a>結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

結果を保持する固定小数点数。 $ \Ket{0.0} $ に初期化する必要があります。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

