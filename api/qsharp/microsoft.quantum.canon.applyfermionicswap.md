---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: Applyの Mimionicswap 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 0c470705843a6360df0a72374570d86571397e41
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218803"
---
# <a name="applyfermionicswap-operation"></a><span data-ttu-id="9b45b-102">Applyの Mimionicswap 操作</span><span class="sxs-lookup"><span data-stu-id="9b45b-102">ApplyFermionicSWAP operation</span></span>

<span data-ttu-id="9b45b-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b45b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b45b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b45b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b45b-105">Fermionic SWAP を適用します。</span><span class="sxs-lookup"><span data-stu-id="9b45b-105">Applies the Fermionic SWAP.</span></span>

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9b45b-106">説明</span><span class="sxs-lookup"><span data-stu-id="9b45b-106">Description</span></span>

<span data-ttu-id="9b45b-107">これは基本的に、-1 のグローバルフェーズを適用しているときに、両方の qubits が1である場合に、qubits を交換します。</span><span class="sxs-lookup"><span data-stu-id="9b45b-107">This essentially swaps the qubits while applying a global phase of -1 if both qubits are 1s.</span></span> <span data-ttu-id="9b45b-108">Orbitals の symmetrization を保持します。</span><span class="sxs-lookup"><span data-stu-id="9b45b-108">Preserves anti-symmetrization of orbitals.</span></span>
<span data-ttu-id="9b45b-109">詳細については、「」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9b45b-109">See  for more information.</span></span>

<span data-ttu-id="9b45b-110">この操作は、\begin{align} f_ {swap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 0 & 0 & 1 & 0 0 & 1 & 0 & 0 \\ \\ \\ \\ \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}. によって表されます。</span><span class="sxs-lookup"><span data-stu-id="9b45b-110">This operation is represented by the unitary operator \begin{align} f_{swap} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -1 \\\\ \end{bmatrix}.</span></span>
<span data-ttu-id="9b45b-111">\end{align}</span><span class="sxs-lookup"><span data-stu-id="9b45b-111">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="9b45b-112">入力</span><span class="sxs-lookup"><span data-stu-id="9b45b-112">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="9b45b-113">qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b45b-113">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b45b-114">交換される最初の qubit。</span><span class="sxs-lookup"><span data-stu-id="9b45b-114">The first qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="9b45b-115">qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b45b-115">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b45b-116">スワップする2番目の qubit。</span><span class="sxs-lookup"><span data-stu-id="9b45b-116">The second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b45b-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b45b-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="9b45b-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="9b45b-118">References</span></span>

- [<span data-ttu-id="9b45b-119">*ライアン Babbush、Nathan Wiebe、Jarrod McClean、James Mcclアイン、Hartmut Neven、Garnet Kin-Lic チャン*、arxiv: 1706.00023</span><span class="sxs-lookup"><span data-stu-id="9b45b-119"> *Ryan Babbush, Nathan Wiebe, Jarrod McClean, James McClain, Hartmut Neven, Garnet Kin-Lic Chan*, arXiv:1706.00023 </span></span>](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a><span data-ttu-id="9b45b-120">参照</span><span class="sxs-lookup"><span data-stu-id="9b45b-120">See Also</span></span>

- [<span data-ttu-id="9b45b-121">Microsoft.... SWAP</span><span class="sxs-lookup"><span data-stu-id="9b45b-121">Microsoft.Quantum.Intrinsic.SWAP</span></span>](xref:Microsoft.Quantum.Intrinsic.SWAP)