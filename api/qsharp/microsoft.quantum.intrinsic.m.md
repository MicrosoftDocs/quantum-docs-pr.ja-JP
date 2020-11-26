---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: ced3a617a7299e169c7a58a1cd0f83f656b2f0b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212343"
---
# <a name="m-operation"></a><span data-ttu-id="28bf8-102">M 操作</span><span class="sxs-lookup"><span data-stu-id="28bf8-102">M operation</span></span>

<span data-ttu-id="28bf8-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="28bf8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="28bf8-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="28bf8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="28bf8-105">P$Z $ ベースで1つの qubit の測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="28bf8-105">Performs a measurement of a single qubit in the Pauli $Z$ basis.</span></span>

<span data-ttu-id="28bf8-106">出力結果は、distribution \begin{align} (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. によって得られます。</span><span class="sxs-lookup"><span data-stu-id="28bf8-106">The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}.</span></span>
<span data-ttu-id="28bf8-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="28bf8-107">\end{align}</span></span>

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a><span data-ttu-id="28bf8-108">入力</span><span class="sxs-lookup"><span data-stu-id="28bf8-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="28bf8-109">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="28bf8-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="28bf8-110">測定する qubit。</span><span class="sxs-lookup"><span data-stu-id="28bf8-110">Qubit to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="28bf8-111">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="28bf8-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="28bf8-112">`Zero` $ + $1 eigenvalue が観測されている場合は、 `One` $-$1 eigenvalue が観測されている場合はです。</span><span class="sxs-lookup"><span data-stu-id="28bf8-112">`Zero` if the $+1$ eigenvalue is observed, and `One` if the $-1$ eigenvalue is observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="28bf8-113">解説</span><span class="sxs-lookup"><span data-stu-id="28bf8-113">Remarks</span></span>

<span data-ttu-id="28bf8-114">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="28bf8-114">Equivalent to:</span></span>

```qsharp
Measure([PauliZ], [qubit]);
```