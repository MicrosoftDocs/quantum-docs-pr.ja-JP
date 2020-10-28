---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724077"
---
# <a name="blochspherecoordinates-function"></a>BlochSphereCoordinates 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パック [](https://nuget.org/packages/)


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