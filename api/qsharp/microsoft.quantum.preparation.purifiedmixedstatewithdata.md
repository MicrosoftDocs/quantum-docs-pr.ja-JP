---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: fc7bf8e6157af079ae4233ef45e67ce8ddfb8fe3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854279"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="66462-102">PurifiedMixedStateWithData 関数</span><span class="sxs-lookup"><span data-stu-id="66462-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="66462-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="66462-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="66462-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="66462-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="66462-105">指定されたデータのコレクションを表すレジスタを使用して、指定された混合状態の purification を準備する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="66462-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="66462-106">"Purified mixed state with data" は、Σi √ pi | i ⟩ | xi ⟩ | garbagei ⟩という形式の状態を示します。各 xi は、register | i ⟩に関連付けられたビット文字列エンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="66462-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="66462-107">詳細については、「」を参照してください https://arxiv.org/pdf/1805.03662.pdf?page=15 。</span><span class="sxs-lookup"><span data-stu-id="66462-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="66462-108">説明</span><span class="sxs-lookup"><span data-stu-id="66462-108">Description</span></span>

<span data-ttu-id="66462-109">クォンタム ROM 手法を使用して特定の密度マトリックスを表現し、その表現を状態準備操作として返します。</span><span class="sxs-lookup"><span data-stu-id="66462-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="66462-110">特に、$N $ 係数 $ \ alpha_j $ と、各係数に関連付けられている bitstring $ \vec{x} j $ のリストがあるとします。この関数は、\tilde\rho = \ sum {j = 0} ^ {\begin{align}} p_j \ket{j}\bra{j}/otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ 混合状態 $ $ \begin{align} \rho = \ sum_{j = 0} ^ {N-1} \ frac {| alpha_j |} の _近似を準備するために、クォンタム ROM の手法を使用する操作を返します_。{\ sum_k | \ alpha_k |}\ket{j}\bra{j}/otimes \ket{\vec{x} _j} \bra{\vec{x} _j}、\end{align} $ $。各 $p _j $ は、$ $ \begin{align}/left | を含む、指定された係数 $ \ alpha_j $ に対する近似値です。p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}\ le \frac{\epsilon}{N} \end{align} $ $ $j $。</span><span class="sxs-lookup"><span data-stu-id="66462-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="66462-111">インデックスレジスタとガベージ qubits のレジスタが渡されたとき、初期状態は $ \ket {0} \ket{00\cdots 0} です。返された操作は、両方のレジスタを $ \ チルダ \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}, \end{align} $ $ に登録します。これにより、対象のエラー $ purification $ の中から、必要な準備を行うために、ガベージレジスタをリセット</span><span class="sxs-lookup"><span data-stu-id="66462-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="66462-112">入力</span><span class="sxs-lookup"><span data-stu-id="66462-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="66462-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="66462-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="66462-114">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="66462-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="66462-115">係数: ([Double](xref:microsoft.quantum.lang-ref.double)、[Bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="66462-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="66462-116">各係数に関連付けられた bitstring $ \vec{x} _j $ と共に、基準状態の確率を指定する $N $ 係数の配列。</span><span class="sxs-lookup"><span data-stu-id="66462-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="66462-117">負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。</span><span class="sxs-lookup"><span data-stu-id="66462-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="66462-118">出力: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="66462-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="66462-119">結合インデックスとガベージレジスタに対する purification として $ \ チルダ \rho $ を準備する操作。</span><span class="sxs-lookup"><span data-stu-id="66462-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="66462-120">解説</span><span class="sxs-lookup"><span data-stu-id="66462-120">Remarks</span></span>

<span data-ttu-id="66462-121">この演算に指定された係数は、1基準に従って正規化されます。そのため、係数は常に有効なカテゴリ確率分布を表していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="66462-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="66462-122">References</span><span class="sxs-lookup"><span data-stu-id="66462-122">References</span></span>

- <span data-ttu-id="66462-123">Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="66462-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="66462-124">参照</span><span class="sxs-lookup"><span data-stu-id="66462-124">See Also</span></span>

- [<span data-ttu-id="66462-125">PurifiedMixedState の準備</span><span class="sxs-lookup"><span data-stu-id="66462-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)