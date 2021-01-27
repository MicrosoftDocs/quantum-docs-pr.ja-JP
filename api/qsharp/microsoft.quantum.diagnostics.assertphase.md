---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830075"
---
# <a name="assertphase-operation"></a><span data-ttu-id="4447d-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="4447d-102">AssertPhase operation</span></span>

<span data-ttu-id="4447d-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="4447d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="4447d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4447d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4447d-105">等しい法則状態のフェーズに予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="4447d-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="4447d-106">説明</span><span class="sxs-lookup"><span data-stu-id="4447d-106">Description</span></span>

<span data-ttu-id="4447d-107">この操作では、 {2} {0} 任意の real $t $ に対して $ \frac{e ^ {i t}} {\ sqrt} (e ^ {k} \ k) $ として表現されるクォンタムの状態のフェーズ $/phi $ が、予期される値であることをアサートし {1} ます。</span><span class="sxs-lookup"><span data-stu-id="4447d-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="4447d-108">入力</span><span class="sxs-lookup"><span data-stu-id="4447d-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="4447d-109">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4447d-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4447d-110">期待される値 $ \ phi \ in (-\ pi, \ pi) $。</span><span class="sxs-lookup"><span data-stu-id="4447d-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="4447d-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4447d-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4447d-112">予期される状態を格納する qubit。</span><span class="sxs-lookup"><span data-stu-id="4447d-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="4447d-113">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4447d-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4447d-114">実際と予想される差に対する絶対許容値。</span><span class="sxs-lookup"><span data-stu-id="4447d-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4447d-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4447d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="4447d-116">例</span><span class="sxs-lookup"><span data-stu-id="4447d-116">Example</span></span>

<span data-ttu-id="4447d-117">次のアサートが成功しました: `qubit` is in state $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ k {0} + e ^ {i 0.5} \ sqrt {1/2} \ k {1} $;</span><span class="sxs-lookup"><span data-stu-id="4447d-117">The following assert succeeds: `qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.0,qubit,10e-10);`

<span data-ttu-id="4447d-118">`qubit` 状態は、$ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ k {0} + e ^ {-i 0.5} \ sqrt {1/2} \ k {1} $; です</span><span class="sxs-lookup"><span data-stu-id="4447d-118">`qubit` is in state $\ket{\psi}=e^{i 0.5}\sqrt{1/2}\ket{0}+e^{-i 0.5}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(0.5,qubit,10e-10);`

<span data-ttu-id="4447d-119">`qubit` 状態は、$ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ k {0} + e ^ {i 0.2} \ sqrt {1/2} \ k {1} $; です</span><span class="sxs-lookup"><span data-stu-id="4447d-119">`qubit` is in state $\ket{\psi}=e^{-i 2.2}\sqrt{1/2}\ket{0}+e^{i 0.2}\sqrt{1/2}\ket{1}$;</span></span>

- `AssertPhase(-1.2,qubit,10e-10);`