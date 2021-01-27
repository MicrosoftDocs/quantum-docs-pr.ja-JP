---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835664"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="4fc9f-102">EstimateTermExpectation 操作</span><span class="sxs-lookup"><span data-stu-id="4fc9f-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="4fc9f-103">名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="4fc9f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="4fc9f-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4fc9f-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4fc9f-105">指定された Jordan-Wigner Hamiltonian term に関連するエネルギーを計算します</span><span class="sxs-lookup"><span data-stu-id="4fc9f-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="4fc9f-106">説明</span><span class="sxs-lookup"><span data-stu-id="4fc9f-106">Description</span></span>

<span data-ttu-id="4fc9f-107">この操作では、各測定演算子に関連付けられた予測値を推定し、サンプリングを使用して対応する係数で乗算します。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="4fc9f-108">結果は、Jordan-Wigner 用語のエネルギーを含む変数に集計されます。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="4fc9f-109">入力</span><span class="sxs-lookup"><span data-stu-id="4fc9f-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="4fc9f-110">inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="4fc9f-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="4fc9f-111">状態の準備に使用されるユニタリ。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="4fc9f-112">ops: [Pの li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="4fc9f-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="4fc9f-113">Jordan-Wigner 用語の測定演算子。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="4fc9f-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4fc9f-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4fc9f-115">Jordan-Wigner 用語の係数。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="4fc9f-116">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fc9f-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4fc9f-117">分子システムをシミュレートするために必要な qubits の数。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="4fc9f-118">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fc9f-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4fc9f-119">想定用語の推定に使用するサンプル数。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="4fc9f-120">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4fc9f-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4fc9f-121">Jordan-Wigner 用語に関連付けられているエネルギー。</span><span class="sxs-lookup"><span data-stu-id="4fc9f-121">The energy associated to the Jordan-Wigner term.</span></span>