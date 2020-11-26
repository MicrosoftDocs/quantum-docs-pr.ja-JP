---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: AssertQubitIsInStateWithinTolerance 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 1ceb7243cba93e42c67cc3655283a5d07c96863e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202211"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a><span data-ttu-id="339f4-102">AssertQubitIsInStateWithinTolerance 操作</span><span class="sxs-lookup"><span data-stu-id="339f4-102">AssertQubitIsInStateWithinTolerance operation</span></span>

<span data-ttu-id="339f4-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="339f4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="339f4-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="339f4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="339f4-105">予期される状態の qubit をアサートします。</span><span class="sxs-lookup"><span data-stu-id="339f4-105">Asserts that a qubit in the expected state.</span></span>

<span data-ttu-id="339f4-106">`expected` 複合ベクター、$ \ket{\psi} = \begin{bmatrix}a & b\ end {bmatrix} ^ {\mathrm{T}} $ を表します。</span><span class="sxs-lookup"><span data-stu-id="339f4-106">`expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$.</span></span>
<span data-ttu-id="339f4-107">各 $a $、$b $ を表す組の最初の要素は複素数の実数部ですが、2番目の要素は虚数部です。</span><span class="sxs-lookup"><span data-stu-id="339f4-107">The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part.</span></span>
<span data-ttu-id="339f4-108">最後の引数は、アサーションが行われる許容範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="339f4-108">The last argument defines the tolerance with which assertion is made.</span></span>

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="339f4-109">入力</span><span class="sxs-lookup"><span data-stu-id="339f4-109">Input</span></span>

### <a name="expected--complexcomplex"></a><span data-ttu-id="339f4-110">が必要です: ([complex](xref:Microsoft.Quantum.Math.Complex)、[complex](xref:Microsoft.Quantum.Math.Complex))</span><span class="sxs-lookup"><span data-stu-id="339f4-110">expected : ([Complex](xref:Microsoft.Quantum.Math.Complex),[Complex](xref:Microsoft.Quantum.Math.Complex))</span></span>

<span data-ttu-id="339f4-111">$ \Ket {0} $ と $ \ket $ には、それぞれ複雑な振幅が必要です {1} 。</span><span class="sxs-lookup"><span data-stu-id="339f4-111">Expected complex amplitudes for $\ket{0}$ and $\ket{1}$, respectively.</span></span>


### <a name="register--qubit"></a><span data-ttu-id="339f4-112">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="339f4-112">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="339f4-113">状態がアサートされる qubit。</span><span class="sxs-lookup"><span data-stu-id="339f4-113">Qubit whose state is to be asserted.</span></span> <span data-ttu-id="339f4-114">この qubit は、割り当てられた他の qubit から分離可能であり、entangled ではないと見なされます。</span><span class="sxs-lookup"><span data-stu-id="339f4-114">Note that this qubit is assumed to be separable from other allocated qubits, and not entangled.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="339f4-115">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="339f4-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="339f4-116">実際の振幅が予期された値と異なることが許容される加法許容範囲。</span><span class="sxs-lookup"><span data-stu-id="339f4-116">Additive tolerance by which actual amplitudes are allowed to deviate from expected.</span></span>
<span data-ttu-id="339f4-117">詳細については、以下の解説を参照してください。</span><span class="sxs-lookup"><span data-stu-id="339f4-117">See remarks below for details.</span></span>



## <a name="output--unit"></a><span data-ttu-id="339f4-118">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="339f4-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="339f4-119">解説</span><span class="sxs-lookup"><span data-stu-id="339f4-119">Remarks</span></span>

<span data-ttu-id="339f4-120">次の Mathematica コードは、mi、mx、my、mz の式を検証するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="339f4-120">The following Mathematica code can be used to verify expressions for mi, mx, my, mz:</span></span>

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

<span data-ttu-id="339f4-121">許容範囲は $L、 \_ 3 次元の実数ベクトル (x ₂) 間の {\ infty} $ 距離です。 x ₃、x ₄) で定義されている $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ および実数ベクトル (y ₂、y ₃、y ₄) によって定義された複素数 = y ₁ I + y ₂ x + y ₃ y + y ₄ Z</span><span class="sxs-lookup"><span data-stu-id="339f4-121">The tolerance is the $L\_{\infty}$ distance between 3 dimensional real vector (x₂,x₃,x₄) defined by $\langle\psi|\psi\rangle = x\_1 I + x\_2 X + x\_3 Y + x\_4 Z$ and real vector (y₂,y₃,y₄) defined by ρ = y₁I + y₂X + y₃Y + y₄Z where ρ is the density matrix corresponding to the state of the register.</span></span>
<span data-ttu-id="339f4-122">これは、Tr (複素数) と Tr (| ψ⟩⟨ψ |) が両方とも 1 (たとえば、x ₁ = 1/2、y ₁ = 1/2) であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="339f4-122">This is only true under the assumption that Tr(ρ) and Tr(|ψ⟩⟨ψ|) are both 1 (e.g. x₁ = 1/2, y₁ = 1/2).</span></span>
<span data-ttu-id="339f4-123">そうでない場合、関数は、(x ₂-x ₁、x ₃₁、x ₄-x ₁、x ₄ + x ₁) と (y ₂-y ₁、y ₃-y ₁、y ₄-y ₁、y ₄ + y ₁) が tolerance パラメーターより小さいことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="339f4-123">If this is not the case, the function asserts that l∞ distance between (x₂-x₁,x₃-x₁,x₄-x₁,x₄+x₁) and (y₂-y₁,y₃-y₁,y₄-y₁,y₄+y₁) is less than the tolerance parameter.</span></span>