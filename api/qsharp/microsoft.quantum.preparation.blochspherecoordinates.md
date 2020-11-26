---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 594896a72fe40e5ba994e08500c3ce71b185bfff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193558"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="7c0f1-102">BlochSphereCoordinates 関数</span><span class="sxs-lookup"><span data-stu-id="7c0f1-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="7c0f1-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7c0f1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7c0f1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c0f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c0f1-105">シングル qubit 状態の Bloch 球座標を計算します。</span><span class="sxs-lookup"><span data-stu-id="7c0f1-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="7c0f1-106">2つの複素数を $a 0、a1 $ は qubit 状態を表し、\ket が 0 {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i/phi/2}\cos{(\ シータ/2)} \ket {0} + e ^ {i/phi/2}\sin{(\ シータ/2)} \ket) $ $a というように計算され {1} ます。</span><span class="sxs-lookup"><span data-stu-id="7c0f1-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="7c0f1-107">入力</span><span class="sxs-lookup"><span data-stu-id="7c0f1-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="7c0f1-108">a0: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7c0f1-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7c0f1-109">状態 $ \ket $ の複合係数 {0} 。</span><span class="sxs-lookup"><span data-stu-id="7c0f1-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="7c0f1-110">a1: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="7c0f1-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="7c0f1-111">状態 $ \ket $ の複合係数 {1} 。</span><span class="sxs-lookup"><span data-stu-id="7c0f1-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="7c0f1-112">出力: ([Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)、[double](xref:microsoft.quantum.lang-ref.double)、[double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="7c0f1-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="7c0f1-113">を含むタプル `(ComplexPolar(r, t), phi, theta)` 。</span><span class="sxs-lookup"><span data-stu-id="7c0f1-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>