---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 62643f64a6b829949fa708e300d9d262527dbb29
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855894"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


シングル qubit 状態の Bloch 球座標を計算します。

2つの複素数を $a 0、a1 $ は qubit 状態を表し、\ket が 0 {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i/phi/2}\cos{(\ シータ/2)} \ket {0} + e ^ {i/phi/2}\sin{(\ シータ/2)} \ket) $ $a というように計算され {1} ます。

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a>入力

### <a name="a0--complexpolar"></a>a0: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

状態 $ \ket $ の複合係数 {0} 。


### <a name="a1--complexpolar"></a>a1: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)

状態 $ \ket $ の複合係数 {1} 。



## <a name="output--complexpolardoubledouble"></a>出力: ([Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)、[double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))

を含むタプル `(ComplexPolar(r, t), phi, theta)` 。