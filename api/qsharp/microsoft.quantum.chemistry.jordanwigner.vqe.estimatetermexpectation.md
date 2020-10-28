---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713727"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="95eae-102">EstimateTermExpectation 操作</span><span class="sxs-lookup"><span data-stu-id="95eae-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="95eae-103">名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="95eae-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="95eae-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95eae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95eae-105">指定された Jordan-Wigner Hamiltonian term に関連するエネルギーを計算します</span><span class="sxs-lookup"><span data-stu-id="95eae-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="95eae-106">説明</span><span class="sxs-lookup"><span data-stu-id="95eae-106">Description</span></span>

<span data-ttu-id="95eae-107">この操作では、各測定演算子に関連付けられた予測値を推定し、サンプリングを使用して対応する係数で乗算します。</span><span class="sxs-lookup"><span data-stu-id="95eae-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="95eae-108">結果は、Jordan-Wigner 用語のエネルギーを含む変数に集計されます。</span><span class="sxs-lookup"><span data-stu-id="95eae-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="95eae-109">入力</span><span class="sxs-lookup"><span data-stu-id="95eae-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="95eae-110">inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="95eae-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="95eae-111">状態の準備に使用されるユニタリ。</span><span class="sxs-lookup"><span data-stu-id="95eae-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="95eae-112">ops: [Pの li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="95eae-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="95eae-113">Jordan-Wigner 用語の測定演算子。</span><span class="sxs-lookup"><span data-stu-id="95eae-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="95eae-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="95eae-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="95eae-115">Jordan-Wigner 用語の係数。</span><span class="sxs-lookup"><span data-stu-id="95eae-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="95eae-116">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95eae-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95eae-117">分子システムをシミュレートするために必要な qubits の数。</span><span class="sxs-lookup"><span data-stu-id="95eae-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="95eae-118">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="95eae-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="95eae-119">想定用語の推定に使用するサンプル数。</span><span class="sxs-lookup"><span data-stu-id="95eae-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="95eae-120">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="95eae-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="95eae-121">Jordan-Wigner 用語に関連付けられているエネルギー。</span><span class="sxs-lookup"><span data-stu-id="95eae-121">The energy associated to the Jordan-Wigner term.</span></span>