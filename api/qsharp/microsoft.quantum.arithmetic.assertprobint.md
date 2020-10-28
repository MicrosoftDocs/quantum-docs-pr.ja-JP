---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721363"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="292a9-102">AssertProbInt 操作</span><span class="sxs-lookup"><span data-stu-id="292a9-102">AssertProbInt operation</span></span>

<span data-ttu-id="292a9-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="292a9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="292a9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="292a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="292a9-105">クォンタムレジスタの特定の状態の確率に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="292a9-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="292a9-106">説明</span><span class="sxs-lookup"><span data-stu-id="292a9-106">Description</span></span>

<span data-ttu-id="292a9-107">$ \Ket{\psi} = \ sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $ という $n が指定されている場合、$j $ によってインデックスが作成された状態 $ \ket{j} $ の確率 $ | \ alpha_j | ^ 2 $ が予期される値であることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="292a9-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="292a9-108">入力</span><span class="sxs-lookup"><span data-stu-id="292a9-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="292a9-109">stateIndex: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="292a9-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="292a9-110">レジスタによって表される状態 $ \ket{j} $ の $j $ のインデックス `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="292a9-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="292a9-111">が必要です。 [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="292a9-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="292a9-112">予期される値 $ | \ alpha_j | ^ 2 $。</span><span class="sxs-lookup"><span data-stu-id="292a9-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="292a9-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="292a9-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="292a9-114">リトルエンディアン形式で $ \ket{\psi} $ を格納する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="292a9-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="292a9-115">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="292a9-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="292a9-116">実際と予想される差に対する絶対許容値。</span><span class="sxs-lookup"><span data-stu-id="292a9-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="292a9-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="292a9-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

