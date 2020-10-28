---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyの Mimionicswap 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 25dd91b200700d1474cf27bf1d0fa71d57f2e09b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718274"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="eb8ee-102">Applyの Mimionicswap 操作</span><span class="sxs-lookup"><span data-stu-id="eb8ee-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="eb8ee-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb8ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb8ee-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb8ee-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb8ee-105">Fermionic SWAP を適用します。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="eb8ee-106">説明</span><span class="sxs-lookup"><span data-stu-id="eb8ee-106">Description</span></span>

<span data-ttu-id="eb8ee-107">これは基本的に、-1 のグローバルフェーズを適用しているときに、両方の qubits が1である場合に、qubits を交換します。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="eb8ee-108">Orbitals の symmetrization を保持します。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="eb8ee-109">詳細については、「」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-109">See  for more information.</span></span>

<span data-ttu-id="eb8ee-110">この操作は、\begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 0 & 1 & 0 & 0 \\ \\ \\ \\ \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}. によって表されます。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="eb8ee-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="eb8ee-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="eb8ee-112">入力</span><span class="sxs-lookup"><span data-stu-id="eb8ee-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="eb8ee-113">qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb8ee-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb8ee-114">交換される最初の qubit。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="eb8ee-115">qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb8ee-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb8ee-116">スワップする2番目の qubit。</span><span class="sxs-lookup"><span data-stu-id="eb8ee-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb8ee-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb8ee-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="eb8ee-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb8ee-118">References</span></span>

- [<span data-ttu-id="eb8ee-119">*ライアン Babbush、Nathan Wiebe、Jarrod McClean、James Mcclアイン、Hartmut Neven、Garnet Kin-Lic チャン* 、arxiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="eb8ee-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan* , arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="eb8ee-120">参照</span><span class="sxs-lookup"><span data-stu-id="eb8ee-120">See Also</span></span>

- [<span data-ttu-id="eb8ee-121">Microsoft.... SWAP</span><span class="sxs-lookup"><span data-stu-id="eb8ee-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)