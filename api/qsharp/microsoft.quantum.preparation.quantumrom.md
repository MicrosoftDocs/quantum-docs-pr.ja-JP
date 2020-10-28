---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722957"
---
# <a name="quantumrom-function"></a><span data-ttu-id="5eb40-102">QuantumROM 関数</span><span class="sxs-lookup"><span data-stu-id="5eb40-102">QuantumROM function</span></span>

<span data-ttu-id="5eb40-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5eb40-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5eb40-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5eb40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5eb40-105">は、指定された密度マトリックスを表すために、クォンタム ROM の手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="5eb40-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="5eb40-106">$N $ 係数 $ \ alpha_j $ のリストが指定されている場合、$U この例では、クォンタム-ROM 手法を使用して近似 $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j 密度マトリックス $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} の purification の \ket{j}\bra{j} $ を準備します。{\ sum_k | \ alpha_k |}\ket{j}\bra{j} $。</span><span class="sxs-lookup"><span data-stu-id="5eb40-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="5eb40-107">この近似値では、$/イプシロン $ というエラーが $ | p_j-\frac{| alpha_j |} のようになります。{\ sum_k | \ alpha_k |} |\ le/イプシロン/N $ と $ \| \tilde\rho-\rho \| $。</span><span class="sxs-lookup"><span data-stu-id="5eb40-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="5eb40-108">つまり、$ $ \begin{align} U\ket {0} ^ {\lceil\ log_2 N\r ceil} \ k {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \ sqrt{p_j} \ket{j}\ket{\text{garbage} _j} です。</span><span class="sxs-lookup"><span data-stu-id="5eb40-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="5eb40-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5eb40-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="5eb40-110">入力</span><span class="sxs-lookup"><span data-stu-id="5eb40-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="5eb40-111">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5eb40-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5eb40-112">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="5eb40-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="5eb40-113">係数: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5eb40-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5eb40-114">ベース状態の確率を指定する $N $ 係数の配列。</span><span class="sxs-lookup"><span data-stu-id="5eb40-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="5eb40-115">負の値 $-\ alpha_j $ は、正の $ | \ alpha_j | $ として処理されます。</span><span class="sxs-lookup"><span data-stu-id="5eb40-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="5eb40-116">出力: (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl)</span><span class="sxs-lookup"><span data-stu-id="5eb40-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="5eb40-117">最初のパラメーター</span><span class="sxs-lookup"><span data-stu-id="5eb40-117">First parameter</span></span>

<span data-ttu-id="5eb40-118">は、 `(x,(y,z))` `x = y + z` 割り当てられた qubits の合計数、は `y` レジスタの qubits の数、は `LittleEndian` `z` ガベージ qubits の数であるタプルです。</span><span class="sxs-lookup"><span data-stu-id="5eb40-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="5eb40-119">2番目のパラメーター</span><span class="sxs-lookup"><span data-stu-id="5eb40-119">Second parameter</span></span>

<span data-ttu-id="5eb40-120">係数配列の1基準 $ \ sum_j | \ alpha_j | $。</span><span class="sxs-lookup"><span data-stu-id="5eb40-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="5eb40-121">3番目のパラメーター</span><span class="sxs-lookup"><span data-stu-id="5eb40-121">Third parameter</span></span>

<span data-ttu-id="5eb40-122">$U のユニタリは $ です。</span><span class="sxs-lookup"><span data-stu-id="5eb40-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="5eb40-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="5eb40-123">References</span></span>

- <span data-ttu-id="5eb40-124">Babbush、Spectra、Gidney、Dominic W Berry、Nathan Wiebe、Jarrod McClean、Alexandru Er、オースティン Fowler、Hartmut Neven の各クォンタム回線での電子商取引のエンコード https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="5eb40-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>