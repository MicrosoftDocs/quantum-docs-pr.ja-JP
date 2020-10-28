---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713750"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="cb698-102">EstimateEnergy 操作</span><span class="sxs-lookup"><span data-stu-id="cb698-102">EstimateEnergy operation</span></span>

<span data-ttu-id="cb698-103">名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="cb698-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="cb698-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb698-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb698-105">個々の Jordan-Wigner の条件によって得たエネルギーを合計することによって、分子のエネルギーを見積もります。</span><span class="sxs-lookup"><span data-stu-id="cb698-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="cb698-106">説明</span><span class="sxs-lookup"><span data-stu-id="cb698-106">Description</span></span>

<span data-ttu-id="cb698-107">この操作は、スピンアップダウンインデックス作成規則に暗黙的に依存します。</span><span class="sxs-lookup"><span data-stu-id="cb698-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="cb698-108">入力</span><span class="sxs-lookup"><span data-stu-id="cb698-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="cb698-109">Jwhamiltonwh: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="cb698-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="cb698-110">Jordan-Wigner Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="cb698-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="cb698-111">nSamples: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb698-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb698-112">期待される用語の推定に使用するサンプルの数。</span><span class="sxs-lookup"><span data-stu-id="cb698-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="cb698-113">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cb698-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cb698-114">分子の予測エネルギー</span><span class="sxs-lookup"><span data-stu-id="cb698-114">The estimated energy of the molecule</span></span>