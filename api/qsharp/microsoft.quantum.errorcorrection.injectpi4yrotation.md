---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200800"
---
# <a name="injectpi4yrotation-operation"></a>InjectPi4YRotation 操作

名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Y 軸について1つの qubit をπ/4 で回転します。

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a>説明

に対してπ/4 回転を実行 `Y` します。

回転はマジック状態を使用して実行されます。つまり、$ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \ sin \frac{\pi} \ket という状態のコピー {8} です {1} 。
\end{align} $ $

## <a name="input"></a>入力

### <a name="data--qubit"></a>データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

$Y $ ($ \ pi/$4) について回転する qubit。


### <a name="magic--qubit"></a>マジック: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

マジック状態の最初の qubit。 この操作の次のアプリケーション `magic` は、$ \ket {0} $ 状態に戻ります。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

同等のものを次に示します。

```qsharp
Ry(PI() / 4.0, data);
```

and

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

この操作では、ファンクタがサポートされます。この `Adjoint` 場合、同じマジック状態が使用されますが、データ qubit への影響は $-\ pi/4 $ $Y $-ローテーションです。