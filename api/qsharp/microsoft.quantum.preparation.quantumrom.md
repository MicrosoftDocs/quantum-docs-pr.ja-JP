---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 1ee805fb2ea02121daaab7fc3eb5dbbcb134b470
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229887"
---
# <a name="quantumrom-function"></a><span data-ttu-id="7ccc8-102">QuantumROM 関数</span><span class="sxs-lookup"><span data-stu-id="7ccc8-102">QuantumROM function</span></span>

<span data-ttu-id="7ccc8-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="7ccc8-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="7ccc8-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ccc8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="7ccc8-105">QuantumROM は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="7ccc8-106">代わりに、<xref:Microsoft.Quantum.Preparation.PurifiedMixedState> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="7ccc8-107">は、指定された密度マトリックスを表すために、クォンタム ROM の手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="7ccc8-108">$N $ 係数 $ \ alpha_j $ のリストが指定されている場合、$U この例では、クォンタム-ROM 手法を使用して近似 $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j 密度マトリックス $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} の purification の \ket{j}\bra{j} $ を準備します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="7ccc8-109">この近似値では、$/イプシロン $ というエラーが $ | p_j-\frac{| alpha_j |} のようになります。{\ sum_k | \ alpha_k |} |\ le/イプシロン/N $ と $ \| \tilde\rho-\rho \| $。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="7ccc8-110">つまり、$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\r ceil} \ k {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j}\ket{\text{garbage} _j} です。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="7ccc8-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="7ccc8-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="7ccc8-112">入力</span><span class="sxs-lookup"><span data-stu-id="7ccc8-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="7ccc8-113">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ccc8-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ccc8-114">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="7ccc8-115">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="7ccc8-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="7ccc8-116">ベース状態の確率を指定する $N $ 係数の配列。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="7ccc8-117">負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="7ccc8-118">出力: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl)</span><span class="sxs-lookup"><span data-stu-id="7ccc8-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="7ccc8-119">最初のパラメーター</span><span class="sxs-lookup"><span data-stu-id="7ccc8-119">First parameter</span></span>

<span data-ttu-id="7ccc8-120">は、 `(x,(y,z))` `x = y + z` 割り当てられた qubits の合計数、は `y` レジスタの qubits の数、は `LittleEndian` `z` ガベージ qubits の数であるタプルです。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="7ccc8-121">2番目のパラメーター</span><span class="sxs-lookup"><span data-stu-id="7ccc8-121">Second parameter</span></span>

<span data-ttu-id="7ccc8-122">係数配列の1基準 $ \ sum_j | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="7ccc8-123">3番目のパラメーター</span><span class="sxs-lookup"><span data-stu-id="7ccc8-123">Third parameter</span></span>

<span data-ttu-id="7ccc8-124">$U のユニタリは $ です。</span><span class="sxs-lookup"><span data-stu-id="7ccc8-124">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="7ccc8-125">リファレンス</span><span class="sxs-lookup"><span data-stu-id="7ccc8-125">References</span></span>

- <span data-ttu-id="7ccc8-126">Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="7ccc8-126">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>