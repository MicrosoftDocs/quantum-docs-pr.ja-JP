---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: e042c03d2a72d9ce4816a8cdb56603e175b22807
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712952"
---
# <a name="assertphase-operation"></a><span data-ttu-id="78958-102">AssertPhase 操作</span><span class="sxs-lookup"><span data-stu-id="78958-102">AssertPhase operation</span></span>

<span data-ttu-id="78958-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="78958-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="78958-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="78958-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="78958-105">等しい法則状態のフェーズに予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="78958-105">Asserts that the phase of an equal superposition state has the expected value.</span></span>

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="78958-106">説明</span><span class="sxs-lookup"><span data-stu-id="78958-106">Description</span></span>

<span data-ttu-id="78958-107">この操作では、 {2} {0} 任意の real $t $ に対して $ \frac{e ^ {i t}} {\ sqrt} (e ^ {k} \ k) $ として表現されるクォンタムの状態のフェーズ $/phi $ が、予期される値であることをアサートし {1} ます。</span><span class="sxs-lookup"><span data-stu-id="78958-107">This operation asserts that the phase $\phi$ of a quantum state that may be expressed as $\frac{e^{i t}}{\sqrt{2}}(e^{i\phi}\ket{0} + e^{-i\phi}\ket{1})$ for some arbitrary real $t$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="78958-108">入力</span><span class="sxs-lookup"><span data-stu-id="78958-108">Input</span></span>

### <a name="expected--double"></a><span data-ttu-id="78958-109">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78958-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78958-110">期待される値 $ \ phi \ in (-\ pi, \ pi) $。</span><span class="sxs-lookup"><span data-stu-id="78958-110">The expected value of $\phi \in (-\pi,\pi]$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="78958-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78958-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78958-112">予期される状態を格納する qubit。</span><span class="sxs-lookup"><span data-stu-id="78958-112">The qubit that stores the expected state.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="78958-113">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78958-113">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78958-114">実際と予想される差に対する絶対許容値。</span><span class="sxs-lookup"><span data-stu-id="78958-114">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78958-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78958-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

