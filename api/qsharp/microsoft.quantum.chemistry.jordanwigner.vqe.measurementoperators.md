---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: MeasurementOperators 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713680"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="4cd15-102">MeasurementOperators 関数</span><span class="sxs-lookup"><span data-stu-id="4cd15-102">MeasurementOperators function</span></span>

<span data-ttu-id="4cd15-103">名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="4cd15-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="4cd15-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4cd15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4cd15-105">Jordan-Wigner 用語の予測を計算するために必要なすべての測定演算子を計算します。</span><span class="sxs-lookup"><span data-stu-id="4cd15-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="4cd15-106">入力</span><span class="sxs-lookup"><span data-stu-id="4cd15-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="4cd15-107">nQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4cd15-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4cd15-108">分子システムをシミュレートするために必要な qubits の数。</span><span class="sxs-lookup"><span data-stu-id="4cd15-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="4cd15-109">インデックス: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4cd15-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4cd15-110">各 P# li 演算子が適用される qubit のインデックスを格納している配列。</span><span class="sxs-lookup"><span data-stu-id="4cd15-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="4cd15-111">termType: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4cd15-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4cd15-112">Jordan-Wigner 用語の型。</span><span class="sxs-lookup"><span data-stu-id="4cd15-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="4cd15-113">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="4cd15-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="4cd15-114">測定演算子の配列 (それぞれが Pan Li の配列)。</span><span class="sxs-lookup"><span data-stu-id="4cd15-114">An array of measurement operators (each being an array of Pauli).</span></span>