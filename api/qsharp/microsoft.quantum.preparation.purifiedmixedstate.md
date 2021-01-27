---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854299"
---
# <a name="purifiedmixedstate-function"></a><span data-ttu-id="72817-102">PurifiedMixedState 関数</span><span class="sxs-lookup"><span data-stu-id="72817-102">PurifiedMixedState function</span></span>

<span data-ttu-id="72817-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="72817-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="72817-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="72817-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="72817-105">指定された混合状態の purification を準備する操作を返します。</span><span class="sxs-lookup"><span data-stu-id="72817-105">Returns an operation that prepares a a purification of a given mixed state.</span></span>
<span data-ttu-id="72817-106">"Purified mixed state" は、係数 {pi} のベクターによって指定されたフォーム | ψ⟩ = Σi √ pi | i ⟩ | garbagei ⟩の状態を示します。</span><span class="sxs-lookup"><span data-stu-id="72817-106">A "purified mixed state" refers to states of the form |ψ⟩ = Σᵢ √𝑝ᵢ |𝑖⟩ |garbageᵢ⟩ specified by a vector of coefficients {𝑝ᵢ}.</span></span> <span data-ttu-id="72817-107">このフォームの状態は、混合状態複素数≔ pi | i ⟩⟨ i | に減らすことができます。"ガベージ" レジスタをトレースする (つまり、コンピューティングのために対角線が斜めである混合状態)。</span><span class="sxs-lookup"><span data-stu-id="72817-107">States of this form can be reduced to mixed states ρ ≔ 𝑝ᵢ |𝑖⟩⟨𝑖| by tracing over the "garbage" register (that is, a mixed state that is diagonal in the computational basis).</span></span>

<span data-ttu-id="72817-108">詳細については、「」を参照してください https://arxiv.org/pdf/1805.03662.pdf?page=15 。</span><span class="sxs-lookup"><span data-stu-id="72817-108">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="72817-109">説明</span><span class="sxs-lookup"><span data-stu-id="72817-109">Description</span></span>

<span data-ttu-id="72817-110">クォンタム ROM 手法を使用して特定の密度マトリックスを表現し、その表現を状態準備操作として返します。</span><span class="sxs-lookup"><span data-stu-id="72817-110">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="72817-111">特に、$N $ 係数 $ \ alpha_j $ のリストがあるとします。この関数は、\tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ の混合状態 $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ frac {| alpha_j |} の近似値を準備するために、クォンタム ROM の手法を使用する操作を返します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j}, \end{align} $ $ (各 $p _j $ は、$ $ \begin{align}/left | を含む指定された係数 $ \ alpha_j $ に対する近似値です。p_j-\frac{| \ alpha_j |}{\ sum_k | \ alpha_k |}\ le \frac{\epsilon}{N} \end{align} $ $ $j $。</span><span class="sxs-lookup"><span data-stu-id="72817-111">In particular, given a list of $N$ coefficients $\alpha_j$, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="72817-112">インデックスレジスタとガベージ qubits のレジスタが渡された場合 state $ \ket \ket{00\cdots 0} の初期状態では {0} 、返された操作は両方のレジスタを $ \ チルダ \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $ の purification に準備します。これにより、対象のエラー $ $ の前に、必要な準備</span><span class="sxs-lookup"><span data-stu-id="72817-112">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="72817-113">入力</span><span class="sxs-lookup"><span data-stu-id="72817-113">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="72817-114">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="72817-114">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="72817-115">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="72817-115">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="72817-116">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="72817-116">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="72817-117">ベース状態の確率を指定する $N $ 係数の配列。</span><span class="sxs-lookup"><span data-stu-id="72817-117">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="72817-118">負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。</span><span class="sxs-lookup"><span data-stu-id="72817-118">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="72817-119">出力: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="72817-119">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="72817-120">結合インデックスとガベージレジスタに対する purification として $ \ チルダ \rho $ を準備する操作。</span><span class="sxs-lookup"><span data-stu-id="72817-120">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="example"></a><span data-ttu-id="72817-121">例</span><span class="sxs-lookup"><span data-stu-id="72817-121">Example</span></span>

<span data-ttu-id="72817-122">次のコードスニペットは、$ 3 $-qubit state $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} の purification を準備します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $,、$ \ vec\ alpha = (1.0, 2.0, 3.0, 4.0, 5.0) $,、ターゲットエラーは $10 ^ {-3} $:</span><span class="sxs-lookup"><span data-stu-id="72817-122">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0, 2.0, 3.0, 4.0, 5.0)$, and the target error is $10^{-3}$:</span></span>

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="72817-123">解説</span><span class="sxs-lookup"><span data-stu-id="72817-123">Remarks</span></span>

<span data-ttu-id="72817-124">この演算に指定された係数は、1基準に従って正規化されます。そのため、係数は常に有効なカテゴリ確率分布を表していると見なされます。</span><span class="sxs-lookup"><span data-stu-id="72817-124">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="72817-125">References</span><span class="sxs-lookup"><span data-stu-id="72817-125">References</span></span>

- <span data-ttu-id="72817-126">Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="72817-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="72817-127">参照</span><span class="sxs-lookup"><span data-stu-id="72817-127">See Also</span></span>

- [<span data-ttu-id="72817-128">PurifiedMixedStateWithData の準備</span><span class="sxs-lookup"><span data-stu-id="72817-128">Microsoft.Quantum.Preparation.PurifiedMixedStateWithData</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)