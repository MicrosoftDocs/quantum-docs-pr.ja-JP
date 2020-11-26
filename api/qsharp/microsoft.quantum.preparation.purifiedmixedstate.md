---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230023"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="e29ee-102">PurifiedMixedState 関数</span><span class="sxs-lookup"><span data-stu-id="e29ee-102">PurifiedMixedState function</span></span>

<span data-ttu-id="e29ee-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e29ee-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e29ee-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e29ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e29ee-105">指定された混合状態の purification を準備する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="e29ee-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="e29ee-106">"Purified mixed state" は、係数 {pi} のベクターによって指定されたフォーム | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="e29ee-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="e29ee-107">このフォームの状態は、混合状態複素数≔ pi | i ⟩⟨ i | に減らすことができます。"ガベージ" レジスタをトレースする (つまり、コンピューティングのために対角線が斜めである混合状態)。</span><span class="sxs-lookup"><span data-stu-id="e29ee-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="e29ee-108">詳細については、「」を参照してください https://arxiv.org/pdf/1805.03662.pdf?page=15 。</span><span class="sxs-lookup"><span data-stu-id="e29ee-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="e29ee-109">説明</span><span class="sxs-lookup"><span data-stu-id="e29ee-109">Description</span></span>

<span data-ttu-id="e29ee-110">クォンタム ROM 手法を使用して特定の密度マトリックスを表現し、その表現を状態準備操作として返します。</span><span class="sxs-lookup"><span data-stu-id="e29ee-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="e29ee-111">特に、$N $ 係数 $ \ alpha_j $ のリストがあるとします。この関数は、\tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ の混合状態 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} の近似値を準備するために、クォンタム ROM の手法を使用する操作を返します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j}, \end{align} $ $ (各 $p _j $ は、$ $ \begin{align}/left | を含む指定された係数 $ \ alpha_j $ に対する近似値です。p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}\ le \frac{\epsilon}{N} \end{align} $ $ $j $。</span><span class="sxs-lookup"><span data-stu-id="e29ee-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="e29ee-112">インデックスレジスタとガベージ qubits のレジスタが渡された場合 state $ \ket \ket{00\cdots 0} の初期状態では {0} 、返された操作は両方のレジスタを $ \ チルダ \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $ の purification に準備します。これにより、対象のエラー $ $ の前に、必要な準備</span><span class="sxs-lookup"><span data-stu-id="e29ee-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="e29ee-113">入力</span><span class="sxs-lookup"><span data-stu-id="e29ee-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="e29ee-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e29ee-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e29ee-115">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="e29ee-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="e29ee-116">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e29ee-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e29ee-117">ベース状態の確率を指定する $N $ 係数の配列。</span><span class="sxs-lookup"><span data-stu-id="e29ee-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="e29ee-118">負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。</span><span class="sxs-lookup"><span data-stu-id="e29ee-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="e29ee-119">出力: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="e29ee-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="e29ee-120">結合インデックスとガベージレジスタに対する purification として $ \ チルダ \rho $ を準備する操作。</span><span class="sxs-lookup"><span data-stu-id="e29ee-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="e29ee-121">解説</span><span class="sxs-lookup"><span data-stu-id="e29ee-121">Remarks</span></span>

<span data-ttu-id="e29ee-122">この演算に指定された係数は、1基準に従って正規化されます。そのため、係数は常に有効なカテゴリ確率分布を表していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="e29ee-122">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="e29ee-123">リファレンス</span><span class="sxs-lookup"><span data-stu-id="e29ee-123">References</span></span>

- <span data-ttu-id="e29ee-124">Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e29ee-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="e29ee-125">参照</span><span class="sxs-lookup"><span data-stu-id="e29ee-125">See Also</span></span>

- [<span data-ttu-id="e29ee-126">PurifiedMixedStateWithData の準備</span><span class="sxs-lookup"><span data-stu-id="e29ee-126">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)