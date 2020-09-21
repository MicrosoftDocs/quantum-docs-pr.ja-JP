---
title: 標準ライブラリでのエラー修正 Q#
description: プログラムでエラー修正コードを使用し Q# ながら、qubits の状態を保護する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: dad0db4d2aab27e5ae46d4df10ee050f785d8bb8
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835555"
---
# <a name="error-correction"></a><span data-ttu-id="f1761-103">エラーの修正</span><span class="sxs-lookup"><span data-stu-id="f1761-103">Error Correction</span></span> #

## <a name="introduction"></a><span data-ttu-id="f1761-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="f1761-104">Introduction</span></span> ##

<span data-ttu-id="f1761-105">従来のコンピューティングでは、エラーに対して1つの保護が必要な場合は、データビットを繰り返すことによって、そのビットを *論理ビット* で表現するのが十分な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1761-105">In classical computing, if one wants to protect a bit against errors, it can often suffice to represent that bit by a *logical bit* by repeating the data bit.</span></span>
<span data-ttu-id="f1761-106">たとえば、$0 $ > は、 {0} データビット0のエンコーディングとして使用します。この場合、ラベル0の上の行を使用して、0状態のビットのエンコーディングであることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1761-106">For instance, let $\overline{0} = 000$ be the encoding of the data bit 0, where we use the a line above the label 0 to indicate that it is an encoding of a bit in the 0 state.</span></span>
<span data-ttu-id="f1761-107">同様に $/の前に {1} = $111 がある場合は、1つのビットフリップエラーから保護する単純な繰り返しコードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f1761-107">If we similarly let $\overline{1} = 111$, then we have a simple repetition code that protects against any one bit flip error.</span></span>
<span data-ttu-id="f1761-108">つまり、3つのビットのいずれかが反転されている場合は、過半数の投票を行って論理ビットの状態を復旧できます。</span><span class="sxs-lookup"><span data-stu-id="f1761-108">That is, if any of the three bits are flipped, then we can recover the state of the logical bit by taking a majority vote.</span></span>
<span data-ttu-id="f1761-109">古典的なエラー修正は、この特定の例 ( [コード理論の概要を説明する](https://www.springer.com/us/book/9783540641339)ことをお勧めします) の方がはるかに豊富ですが、上記の繰り返しコードでは、クォンタム情報の保護に関する問題が既に考えられています。</span><span class="sxs-lookup"><span data-stu-id="f1761-109">Though classical error correction is a much richer subject that this particular example (we recommend [Lint's introduction to coding theory](https://www.springer.com/us/book/9783540641339)), the repetition code above already points to a possible problem in protecting quantum information.</span></span>
<span data-ttu-id="f1761-110">つまり、 [複製なしの定理](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) は、個々の qubit を測定して、上記の古典的なコードと比較して大部分の投票を行うと、保護しようとしている正確な情報が失われていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f1761-110">Namely, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implies that if we measure each individual qubit and take a majority vote by analogy to classical code above, then we have lost the precise information that we are trying to protect.</span></span>

<span data-ttu-id="f1761-111">[クォンタム] 設定には、測定値が問題であることが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f1761-111">In the quantum setting, we will see that the measurement is problematic.</span></span> <span data-ttu-id="f1761-112">上記のエンコードを実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="f1761-112">We can still implement the encoding above.</span></span>
<span data-ttu-id="f1761-113">これを行うと、エラー修正をクォンタムケースに一般化する方法を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="f1761-113">It is helpful to do so to see how we can generalize error correction to the quantum case.</span></span>
<span data-ttu-id="f1761-114">したがって、let $ \ket{\overline {0} } = \ket {000} = \ket {0} /otimes \ket、 {0} otimes \ket {0} $、let $ \ket{\overline {1} } = \ket {111} $。</span><span class="sxs-lookup"><span data-stu-id="f1761-114">Thus, let $\ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, and let $\ket{\overline{1}} = \ket{111}$.</span></span>
<span data-ttu-id="f1761-115">次に、直線性により、すべての入力に対して繰り返しコードを定義しました。たとえば、$ \ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} })/\ sqrt {2} = (\ket {000} + \ket {111} )/\ sqrt $ のように {2} なります。</span><span class="sxs-lookup"><span data-stu-id="f1761-115">Then, by linearity, we have defined our repetition code for all inputs; for instance, $\ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}}) / \sqrt{2} = (\ket{000} + \ket{111}) / \sqrt{2}$.</span></span>
<span data-ttu-id="f1761-116">具体的には、ビットフリップエラーによって、真ん中の qubit に対して _1 $ act $X します。両方の分岐で必要とされる修正が、正確には _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \ket ( {1} {2} X_1 + {000} X_1 \ket \ {111} ) $X \\ \\ & =-frac {1} {/sqrt {2} } \ left (\ket {010} + \ket/ {101} right) であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f1761-116">In particular, letting a bit-flip error $X_1$ act on the middle qubit, we see that the correction needed in both branches is precisely $X_1$: $$ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left( X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{010} + \ket{101} \right).</span></span>
<span data-ttu-id="f1761-117">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f1761-117">\end{align} $$</span></span>

<span data-ttu-id="f1761-118">保護しようとしている状態を測定せずにこの問題が発生していることを特定する方法を確認するには、それぞれのビットフリップエラーが論理的な状態にどのようになるかを記述することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1761-118">To see how we can identify that this is the case without measuring the very state we are trying to protect, it is helpful to write down what each different bit flip error does to our logical states:</span></span>

| <span data-ttu-id="f1761-119">エラー $E $</span><span class="sxs-lookup"><span data-stu-id="f1761-119">Error $E$</span></span> | <span data-ttu-id="f1761-120">$E \ket{\overline {0} } $</span><span class="sxs-lookup"><span data-stu-id="f1761-120">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="f1761-121">$E \ket{\overline {1} } $</span><span class="sxs-lookup"><span data-stu-id="f1761-121">$E\ket{\overline{1}}$</span></span> |
| --- | --- | --- |
| <span data-ttu-id="f1761-122">$\boldone$</span><span class="sxs-lookup"><span data-stu-id="f1761-122">$\boldone$</span></span> | <span data-ttu-id="f1761-123">$ \ket {000} $</span><span class="sxs-lookup"><span data-stu-id="f1761-123">$\ket{000}$</span></span> | <span data-ttu-id="f1761-124">$ \ket {111} $</span><span class="sxs-lookup"><span data-stu-id="f1761-124">$\ket{111}$</span></span> |
| <span data-ttu-id="f1761-125">$X_0$</span><span class="sxs-lookup"><span data-stu-id="f1761-125">$X_0$</span></span> | <span data-ttu-id="f1761-126">$ \ket {100} $</span><span class="sxs-lookup"><span data-stu-id="f1761-126">$\ket{100}$</span></span> | <span data-ttu-id="f1761-127">$ \ket {011} $</span><span class="sxs-lookup"><span data-stu-id="f1761-127">$\ket{011}$</span></span> |
| <span data-ttu-id="f1761-128">$X_1$</span><span class="sxs-lookup"><span data-stu-id="f1761-128">$X_1$</span></span> | <span data-ttu-id="f1761-129">$ \ket {010} $</span><span class="sxs-lookup"><span data-stu-id="f1761-129">$\ket{010}$</span></span> | <span data-ttu-id="f1761-130">$ \ket {101} $</span><span class="sxs-lookup"><span data-stu-id="f1761-130">$\ket{101}$</span></span> |
| <span data-ttu-id="f1761-131">$X_2$</span><span class="sxs-lookup"><span data-stu-id="f1761-131">$X_2$</span></span> | <span data-ttu-id="f1761-132">$ \ket {001} $</span><span class="sxs-lookup"><span data-stu-id="f1761-132">$\ket{001}$</span></span> | <span data-ttu-id="f1761-133">$ \ket {110} $</span><span class="sxs-lookup"><span data-stu-id="f1761-133">$\ket{110}$</span></span> |

<span data-ttu-id="f1761-134">エンコードされている状態を保護するためには、3つのエラーを相互に区別できる必要があります。また、$ \ket{\overline {0} } $ と $ \ket{\overline} $ を区別せずに、id $ > から id $ > を区別できるようにする必要があり {1} ます。</span><span class="sxs-lookup"><span data-stu-id="f1761-134">In order to protect the state that we're encoding, we need to be able to distinguish the three errors from each other and from the identity $\boldone$ without distinguishing between $\ket{\overline{0}}$ and $\ket{\overline{1}}$.</span></span>
<span data-ttu-id="f1761-135">たとえば、$Z 0 $ を測定する場合、 {0} エラーなしのケースでは $ \ket{\overline} $ および $ \ket{\overline} $ に対して異なる結果が得られるため、はエンコードされた {1} 状態を折りたたみます。</span><span class="sxs-lookup"><span data-stu-id="f1761-135">For example, if we measure $Z_0$, we get a different result for $\ket{\overline{0}}$ and $\ket{\overline{1}}$ in the no-error case, so that collapses the encoded state.</span></span>
<span data-ttu-id="f1761-136">一方、各計算基準の状態の最初の2ビットのパリティである $Z 0 Z_1 $ を測定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="f1761-136">On the other hand, consider measuring $Z_0 Z_1$, the parity of the first two bits in each computational basis state.</span></span>
<span data-ttu-id="f1761-137">Pauli 演算子の各測定値がどの eigenvalue に対応しているかを確認します。そのため、上の表の各州 $ \ket{\psi} $ では、$ \pm\ket{\psi} $ を取得するかどうかを確認するために、0 Z_1 \ket{\psi} $ $Z 計算できます。</span><span class="sxs-lookup"><span data-stu-id="f1761-137">Recall that each measurement of a Pauli operator checks which eigenvalue  the state being measured corresponds to, so for each state $\ket{\psi}$ in the table above, we can compute $Z_0 Z_1 \ket{\psi}$ to see if we get $\pm\ket{\psi}$.</span></span>
<span data-ttu-id="f1761-138">$Z 0 Z_1 \ket {000} = \ket {000} $ で $Z 0 Z_1 \ket = \ket $ であることに注意して {111} ください。これにより、 {111} この測定では、エンコードされた両方の状態が同じであることが結論となります。</span><span class="sxs-lookup"><span data-stu-id="f1761-138">Note that $Z_0 Z_1 \ket{000} = \ket{000}$ and that $Z_0 Z_1 \ket{111} = \ket{111}$, so that we conclude that this measurement does the same thing to both encoded states.</span></span>
<span data-ttu-id="f1761-139">一方、$Z 0 Z_1 \ket {100} =-\ket {100} $ and $Z 0 Z_1 \ket {011} =-\ket {011} $ のように指定すると、0 $Z $ を測定した結果として、発生したエラーに関する有用な情報が示されます。</span><span class="sxs-lookup"><span data-stu-id="f1761-139">On the other hand, $Z_0 Z_1 \ket{100} = - \ket{100}$ and $Z_0 Z_1 \ket{011} = -\ket{011}$, so the result of measuring $Z_0 Z_1$ reveals useful information about which error occurred.</span></span>

<span data-ttu-id="f1761-140">このことを強調するために、上記の表を繰り返しますが、各行に 0 Z_1 $ および $Z _1 Z_2 $ $Z 測定した結果を追加します。</span><span class="sxs-lookup"><span data-stu-id="f1761-140">To emphasize this, we repeat the table above, but add the results of measuring $Z_0 Z_1$ and $Z_1 Z_2$ on each row.</span></span>
<span data-ttu-id="f1761-141">各測定の結果は、 Q# `Result` それぞれとの値に対応する $ + $ または $-$ のいずれかの eigenvalue の符号によって示され `Zero` `One` ます。</span><span class="sxs-lookup"><span data-stu-id="f1761-141">We denote the results of each measurement by the sign of the eigenvalue that is observed, either $+$ or $-$, corresponding to the Q# `Result` values of `Zero` and `One`, respectively.</span></span>

| <span data-ttu-id="f1761-142">エラー $E $</span><span class="sxs-lookup"><span data-stu-id="f1761-142">Error $E$</span></span> | <span data-ttu-id="f1761-143">$E \ket{\overline {0} } $</span><span class="sxs-lookup"><span data-stu-id="f1761-143">$E\ket{\overline{0}}$</span></span> | <span data-ttu-id="f1761-144">$E \ket{\overline {1} } $</span><span class="sxs-lookup"><span data-stu-id="f1761-144">$E\ket{\overline{1}}$</span></span> | <span data-ttu-id="f1761-145">$Z 0 Z_1 $ の結果</span><span class="sxs-lookup"><span data-stu-id="f1761-145">Result of $Z_0 Z_1$</span></span> | <span data-ttu-id="f1761-146">$Z _1 Z_2 $ の結果</span><span class="sxs-lookup"><span data-stu-id="f1761-146">Result of $Z_1 Z_2$</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="f1761-147">$\boldone$</span><span class="sxs-lookup"><span data-stu-id="f1761-147">$\boldone$</span></span> | <span data-ttu-id="f1761-148">$ \ket {000} $</span><span class="sxs-lookup"><span data-stu-id="f1761-148">$\ket{000}$</span></span> | <span data-ttu-id="f1761-149">$ \ket {111} $</span><span class="sxs-lookup"><span data-stu-id="f1761-149">$\ket{111}$</span></span> | $+$ | $+$ |
| <span data-ttu-id="f1761-150">$X_0$</span><span class="sxs-lookup"><span data-stu-id="f1761-150">$X_0$</span></span> | <span data-ttu-id="f1761-151">$ \ket {100} $</span><span class="sxs-lookup"><span data-stu-id="f1761-151">$\ket{100}$</span></span> | <span data-ttu-id="f1761-152">$ \ket {011} $</span><span class="sxs-lookup"><span data-stu-id="f1761-152">$\ket{011}$</span></span> | $-$ | $+$ |
| <span data-ttu-id="f1761-153">$X_1$</span><span class="sxs-lookup"><span data-stu-id="f1761-153">$X_1$</span></span> | <span data-ttu-id="f1761-154">$ \ket {010} $</span><span class="sxs-lookup"><span data-stu-id="f1761-154">$\ket{010}$</span></span> | <span data-ttu-id="f1761-155">$ \ket {101} $</span><span class="sxs-lookup"><span data-stu-id="f1761-155">$\ket{101}$</span></span> | $-$ | $-$ |
| <span data-ttu-id="f1761-156">$X_2$</span><span class="sxs-lookup"><span data-stu-id="f1761-156">$X_2$</span></span> | <span data-ttu-id="f1761-157">$ \ket {001} $</span><span class="sxs-lookup"><span data-stu-id="f1761-157">$\ket{001}$</span></span> | <span data-ttu-id="f1761-158">$ \ket {110} $</span><span class="sxs-lookup"><span data-stu-id="f1761-158">$\ket{110}$</span></span> | $+$ | $-$ |

<span data-ttu-id="f1761-159">したがって、2つの測定値の結果によって、どのビットフリップエラーが発生したかが一意に判断されますが、エンコードされた状態に関する情報は表示されません。</span><span class="sxs-lookup"><span data-stu-id="f1761-159">Thus, the results of the two measurements uniquely determines which bit-flip error occurred, but without revealing any information about which state we encoded.</span></span>
<span data-ttu-id="f1761-160">これらの結果を *より隣人*と呼びます。また、より隣人を *復旧*の原因となったエラーにマッピングするプロセスについても説明します。</span><span class="sxs-lookup"><span data-stu-id="f1761-160">We call these results a *syndrome*, and refer to the process of mapping a syndrome back to the error that caused it as *recovery*.</span></span>
<span data-ttu-id="f1761-161">特に、回復は、発生したより隣人を入力として受け取り、発生した可能性のあるエラーを修正する方法の処方箋を返す、 *古典* 的な推定手順であることを強調しています。</span><span class="sxs-lookup"><span data-stu-id="f1761-161">In particular, we emphasize that recovery is a *classical* inference procedure which takes as its input the syndrome which occurred, and returns a prescription for how to fix any errors that may have occurred.</span></span>

> [!NOTE]
> <span data-ttu-id="f1761-162">上記のビットフリップコードは、シングルビットフリップエラーに対してのみ修正できます。つまり、 `X` 1 つの qubit に対して動作する操作です。</span><span class="sxs-lookup"><span data-stu-id="f1761-162">The bit-flip code above can only correct against single bit-flip errors; that is, an `X` operation acting on a single qubit.</span></span>
> <span data-ttu-id="f1761-163">複数の `X` qubit にを適用すると、 {0} 復旧後に $ \ket{\overline} $ が $ \ket{\overline} $ にマップされ {1} ます。</span><span class="sxs-lookup"><span data-stu-id="f1761-163">Applying `X` to more than one qubit will map $\ket{\overline{0}}$ to $\ket{\overline{1}}$ following recovery.</span></span>
> <span data-ttu-id="f1761-164">同様に、フェーズフリップ操作を適用する `Z` と $ \ket{\overline {1} } $ が $-\ket{\overline} $ にマップされる {1} ため、$ \ket{\overline{+}} $ が $ \ket{\overline} $ にマップされ {-} ます。</span><span class="sxs-lookup"><span data-stu-id="f1761-164">Similarly, applying a phase flip operation `Z` will map $\ket{\overline{1}}$ to $-\ket{\overline{1}}$, and hence will map $\ket{\overline{+}}$ to $\ket{\overline{-}}$.</span></span>
> <span data-ttu-id="f1761-165">一般的には、コードを作成して、より多くのエラーを処理したり、$ errors $Z 処理したり、$ errors を $X したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="f1761-165">More generally, codes can be created to handle larger number of errors, and to handle $Z$ errors as well as $X$ errors.</span></span>

<span data-ttu-id="f1761-166">すべてのコード状態で同じように動作するクォンタムエラー修正の測定値を記述できるという洞察は、安定板の *形式*の本質です。</span><span class="sxs-lookup"><span data-stu-id="f1761-166">The insight that we can describe measurements in quantum error correction that act the same way on all code states, is the essence of the *stabilizer formalism*.</span></span>
<span data-ttu-id="f1761-167">キャノンは、 Q# 安定板のコードに対してエンコードを記述し、それをエラーからどのように回復するかを説明するためのフレームワークを提供します。</span><span class="sxs-lookup"><span data-stu-id="f1761-167">The Q# canon provides a framework for describing encoding into and decoding from stabilizer codes, and for describing how one recovers from errors.</span></span>
<span data-ttu-id="f1761-168">このセクションでは、このフレームワークとそのアプリケーションについて、いくつかの単純なクォンタムエラー修正コードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1761-168">In this section, we describe this framework and its application to a few simple quantum error-correcting codes.</span></span>

> [!TIP]
> <span data-ttu-id="f1761-169">安定板形式の詳細については、このセクションでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="f1761-169">A full introduction to the stabilizer formalism is beyond the scope of this section.</span></span>
> <span data-ttu-id="f1761-170">[Gottesman 2009](https://arxiv.org/abs/0904.2557)の詳細については、読者を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1761-170">We refer readers interested in learning more to [Gottesman 2009](https://arxiv.org/abs/0904.2557).</span></span>

## <a name="representing-error-correcting-codes-in-no-locq"></a><span data-ttu-id="f1761-171">エラー修正コードを表す Q#</span><span class="sxs-lookup"><span data-stu-id="f1761-171">Representing Error Correcting Codes in Q#</span></span> ##

<span data-ttu-id="f1761-172">エラー修正コードを指定するために、 Q# キャノン社はいくつかの異なるユーザー定義型を提供しています。</span><span class="sxs-lookup"><span data-stu-id="f1761-172">To help specify error correcting codes, the Q# canon provides several distinct user-defined types:</span></span>

- <span data-ttu-id="f1761-173"><xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`: Qubits のレジスタは、エラー修正コードのコードブロックとして解釈される必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1761-173"><xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: Denotes that a register of qubits should be interpreted as the code block of an error-correcting code.</span></span>
- <span data-ttu-id="f1761-174"><xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`: 測定結果の配列を、コードブロックで測定されるより隣人として解釈する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1761-174"><xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: Denotes that an array of measurement results should be interpreted as the syndrome measured on a code block.</span></span>
- <span data-ttu-id="f1761-175"><xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`: より隣人を解釈し、適用する必要のある修正を返すために、*古典*関数を使用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1761-175"><xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: Denotes that a *classical* function should be used to interpret a syndrome and return a correction that should be applied.</span></span>
- <span data-ttu-id="f1761-176"><xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`: エラー修正コードのコードブロックを生成するために、操作がデータを表す qubits を新しい ancilla qubits と共に受け取ることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1761-176"><xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: Denotes that an operation takes qubits representing data along with fresh ancilla qubits in order to produce a code block of an error-correcting code.</span></span>
- <span data-ttu-id="f1761-177"><xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`: データ qubits にコードを修正するコードブロックとより隣人情報を表すために使用される ancilla qubits を分解されする操作であることを示します。</span><span class="sxs-lookup"><span data-stu-id="f1761-177"><xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: Denotes than an operation decomposes a code block of an error correcting code into the data qubits and the ancilla qubits used to represent syndrome information.</span></span>
- <span data-ttu-id="f1761-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`: コードブロックからより隣人情報を抽出するために使用する必要がある操作を表します。コードによって保護されている状態には支障がありません。</span><span class="sxs-lookup"><span data-stu-id="f1761-178"><xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: Denotes an operation that should be used to extract syndrome information from a code block, without disturbing the state protected by the code.</span></span>

<span data-ttu-id="f1761-179">最後に、キャノンの <xref:microsoft.quantum.errorcorrection.qecc> エラー修正コードを定義するために必要な他の型を収集するための型を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1761-179">Finally, the canon provides the <xref:microsoft.quantum.errorcorrection.qecc> type to collect the other types required to define a quantum error-correcting code.</span></span> <span data-ttu-id="f1761-180">各安定板クォンタムコードに関連付けられているコードの長さは $n $、論理 qubits の数 $k $、および最小距離 $d $ で、多くの場合、⟦ $n $、$k $、$d $ ⟧の表記でグループ化します。</span><span class="sxs-lookup"><span data-stu-id="f1761-180">Associated with each stabilizer quantum code is the code length $n$, the number $k$ of logical qubits, and the minimum distance $d$, often conveniently grouped together in the notation ⟦$n$, $k$, $d$⟧.</span></span> <span data-ttu-id="f1761-181">たとえば、関数は、 <xref:microsoft.quantum.errorcorrection.bitflipcode> ⟦ 3, 1, 1 ⟧ビットフリップコードを定義します。</span><span class="sxs-lookup"><span data-stu-id="f1761-181">For example, the <xref:microsoft.quantum.errorcorrection.bitflipcode> function defines the ⟦3, 1, 1⟧ bit flip code:</span></span>

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

<span data-ttu-id="f1761-182">`QECC`型に復旧関数が含ま*れていない*ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f1761-182">Notice that the `QECC` type does *not* include a recovery function.</span></span>
<span data-ttu-id="f1761-183">これにより、コード自体の定義を変更することなく、エラーの修正に使用される復旧関数を変更できます。この機能は特に、復旧によって想定されるモデルに特性測定のフィードバックを組み込む場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f1761-183">This allows us to change the recovery function that is used in correcting errors without changing the definition of the code itself; this ability is in particular useful when incorporating feedback from characterization measurements into the model assumed by recovery.</span></span>

<span data-ttu-id="f1761-184">この方法でコードを定義すると、操作を使用して <xref:microsoft.quantum.errorcorrection.recover> エラーから回復できます。</span><span class="sxs-lookup"><span data-stu-id="f1761-184">Once a code is defined in this way, we can use the <xref:microsoft.quantum.errorcorrection.recover> operation to recover from errors:</span></span>

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

<span data-ttu-id="f1761-185">この詳細については、「 [ビットフリップコードサンプル](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1761-185">We explore this in more detail in the [bit flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code).</span></span>

<span data-ttu-id="f1761-186">この例では、ビットフリップコード以外に、 Q# [5 qubit の完全なコード](https://arxiv.org/abs/quant-ph/9602019)と7つの [qubit コード](https://arxiv.org/abs/quant-ph/9705052)を実装しています。どちらも任意のシングル qubit エラーを修正できます。</span><span class="sxs-lookup"><span data-stu-id="f1761-186">Aside from the bit-flip code, the Q# canon is provided with implementations of the [five-qubit perfect code](https://arxiv.org/abs/quant-ph/9602019), and the [seven-qubit code](https://arxiv.org/abs/quant-ph/9705052), both of which can correct an arbitrary single-qubit error.</span></span>
