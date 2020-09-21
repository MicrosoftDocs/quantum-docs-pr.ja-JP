---
<span data-ttu-id="56ff9-101">title: P# li 測定の説明: 単一および複数のメジャーの測定演算を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="56ff9-102">author: bradben: benbra: ms. date: 12/11/2017 ミリ秒。 topic: article no loc (場所: 記事の内容は含まれません):</span><span class="sxs-lookup"><span data-stu-id="56ff9-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="56ff9-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="56ff9-103">"Q#"</span></span>
- <span data-ttu-id="56ff9-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="56ff9-104">"$$v"</span></span>
- <span data-ttu-id="56ff9-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="56ff9-105">"$$"</span></span>
- <span data-ttu-id="56ff9-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="56ff9-106">"$$"</span></span>
- <span data-ttu-id="56ff9-107">"$"</span><span class="sxs-lookup"><span data-stu-id="56ff9-107">"$"</span></span>
- <span data-ttu-id="56ff9-108">"$"</span><span class="sxs-lookup"><span data-stu-id="56ff9-108">"$"</span></span>
- <span data-ttu-id="56ff9-109">"$"</span><span class="sxs-lookup"><span data-stu-id="56ff9-109">"$"</span></span>
- <span data-ttu-id="56ff9-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="56ff9-110">"$$"</span></span>
- <span data-ttu-id="56ff9-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="56ff9-111">"\cdots"</span></span>
- <span data-ttu-id="56ff9-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="56ff9-112">"bmatrix"</span></span>
- <span data-ttu-id="56ff9-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="56ff9-113">"\ddots"</span></span>
- <span data-ttu-id="56ff9-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="56ff9-114">"\equiv"</span></span>
- <span data-ttu-id="56ff9-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="56ff9-115">"\sum"</span></span>
- <span data-ttu-id="56ff9-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="56ff9-116">"\begin"</span></span>
- <span data-ttu-id="56ff9-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="56ff9-117">"\end"</span></span>
- <span data-ttu-id="56ff9-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="56ff9-118">"\sqrt"</span></span>
- <span data-ttu-id="56ff9-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="56ff9-119">"\otimes"</span></span>
- <span data-ttu-id="56ff9-120">"{"</span><span class="sxs-lookup"><span data-stu-id="56ff9-120">"{"</span></span>
- <span data-ttu-id="56ff9-121">"}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-121">"}"</span></span>
- <span data-ttu-id="56ff9-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="56ff9-122">"\text"</span></span>
- <span data-ttu-id="56ff9-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="56ff9-123">"\phi"</span></span>
- <span data-ttu-id="56ff9-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="56ff9-124">"\kappa"</span></span>
- <span data-ttu-id="56ff9-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="56ff9-125">"\psi"</span></span>
- <span data-ttu-id="56ff9-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="56ff9-126">"\alpha"</span></span>
- <span data-ttu-id="56ff9-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="56ff9-127">"\beta"</span></span>
- <span data-ttu-id="56ff9-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="56ff9-128">"\gamma"</span></span>
- <span data-ttu-id="56ff9-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="56ff9-129">"\delta"</span></span>
- <span data-ttu-id="56ff9-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="56ff9-130">"\omega"</span></span>
- <span data-ttu-id="56ff9-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="56ff9-131">"\bra"</span></span>
- <span data-ttu-id="56ff9-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="56ff9-132">"\ket"</span></span>
- <span data-ttu-id="56ff9-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="56ff9-133">"\boldone"</span></span>
- <span data-ttu-id="56ff9-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="56ff9-134">"\\\\"</span></span>
- <span data-ttu-id="56ff9-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="56ff9-135">"\\"</span></span>
- <span data-ttu-id="56ff9-136">"="</span><span class="sxs-lookup"><span data-stu-id="56ff9-136">"="</span></span>
- <span data-ttu-id="56ff9-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="56ff9-137">"\frac"</span></span>
- <span data-ttu-id="56ff9-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="56ff9-138">"\text"</span></span>
- <span data-ttu-id="56ff9-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="56ff9-139">"\mapsto"</span></span>
- <span data-ttu-id="56ff9-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="56ff9-140">"\dagger"</span></span>
- <span data-ttu-id="56ff9-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="56ff9-141">"\to"</span></span>
- <span data-ttu-id="56ff9-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-142">"\begin{cases}"</span></span>
- <span data-ttu-id="56ff9-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-143">"\end{cases}"</span></span>
- <span data-ttu-id="56ff9-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="56ff9-144">"\operatorname"</span></span>
- <span data-ttu-id="56ff9-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="56ff9-145">"\braket"</span></span>
- <span data-ttu-id="56ff9-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="56ff9-146">"\id"</span></span>
- <span data-ttu-id="56ff9-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="56ff9-147">"\expect"</span></span>
- <span data-ttu-id="56ff9-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="56ff9-148">"\defeq"</span></span>
- <span data-ttu-id="56ff9-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="56ff9-149">"\variance"</span></span>
- <span data-ttu-id="56ff9-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="56ff9-150">"\dd"</span></span>
- <span data-ttu-id="56ff9-151">"&"</span><span class="sxs-lookup"><span data-stu-id="56ff9-151">"&"</span></span>
- <span data-ttu-id="56ff9-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-152">"\begin{align}"</span></span>
- <span data-ttu-id="56ff9-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-153">"\end{align}"</span></span>
- <span data-ttu-id="56ff9-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="56ff9-154">"\Lambda"</span></span>
- <span data-ttu-id="56ff9-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="56ff9-155">"\lambda"</span></span>
- <span data-ttu-id="56ff9-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="56ff9-156">"\Omega"</span></span>
- <span data-ttu-id="56ff9-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="56ff9-157">"\mathrm"</span></span>
- <span data-ttu-id="56ff9-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="56ff9-158">"\left"</span></span>
- <span data-ttu-id="56ff9-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="56ff9-159">"\right"</span></span>
- <span data-ttu-id="56ff9-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="56ff9-160">"\qquad"</span></span>
- <span data-ttu-id="56ff9-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="56ff9-161">"\times"</span></span>
- <span data-ttu-id="56ff9-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="56ff9-162">"\big"</span></span>
- <span data-ttu-id="56ff9-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="56ff9-163">"\langle"</span></span>
- <span data-ttu-id="56ff9-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="56ff9-164">"\rangle"</span></span>
- <span data-ttu-id="56ff9-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="56ff9-165">"\bigg"</span></span>
- <span data-ttu-id="56ff9-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="56ff9-166">"\Big"</span></span>
- <span data-ttu-id="56ff9-167">"|"</span><span class="sxs-lookup"><span data-stu-id="56ff9-167">"|"</span></span>
- <span data-ttu-id="56ff9-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="56ff9-168">"\mathbb"</span></span>
- <span data-ttu-id="56ff9-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="56ff9-169">"\vec"</span></span>
- <span data-ttu-id="56ff9-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="56ff9-170">"\in"</span></span>
- <span data-ttu-id="56ff9-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="56ff9-171">"\texttt"</span></span>
- <span data-ttu-id="56ff9-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="56ff9-172">"\ne"</span></span>
- <span data-ttu-id="56ff9-173">"<"</span><span class="sxs-lookup"><span data-stu-id="56ff9-173">"<"</span></span>
- <span data-ttu-id="56ff9-174">">"</span><span class="sxs-lookup"><span data-stu-id="56ff9-174">">"</span></span>
- <span data-ttu-id="56ff9-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="56ff9-175">"\leq"</span></span>
- <span data-ttu-id="56ff9-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="56ff9-176">"\geq"</span></span>
- <span data-ttu-id="56ff9-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="56ff9-177">"~~"</span></span>
- <span data-ttu-id="56ff9-178">"~"</span><span class="sxs-lookup"><span data-stu-id="56ff9-178">"~"</span></span>
- <span data-ttu-id="56ff9-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="56ff9-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="56ff9-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="56ff9-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="56ff9-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="56ff9-182">P# li 測定</span><span class="sxs-lookup"><span data-stu-id="56ff9-182">Pauli Measurements</span></span>

<span data-ttu-id="56ff9-183">前のディスカッションでは、計算ベースの測定に重点を置いてきました。</span><span class="sxs-lookup"><span data-stu-id="56ff9-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="56ff9-184">実際には、数値表記の観点からは、コンピューティングベースの測定を表すのに便利な、クォンタムコンピューティングで発生する一般的な測定値があります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="56ff9-185">作業を行う際に実行する最も一般的な種類の測定は、通常、測定値として使用されます。この測定では、計算ベースの測定値が Q# 汎用化され、 *Pauli measurements*他のベースや異なる qubits 間のパリティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="56ff9-186">このような場合、一般的には、通常、 $ x、y、z、 $ $ z \otimes z、x \otimes x、x Y \otimes $ などの演算子で、p# li 演算子の測定について説明します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="56ff9-187">> では Q# 、通常、マルチ qubit の演算子は型の配列によって表され `Pauli[]` ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="56ff9-188">> たとえば、X Z Y を表すには、 $ \otimes 配列を使用し \otimes $ `[PauliX, PauliZ, PauliY]` ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="56ff9-189">P# li 演算子の観点から、メジャーについて説明することは、クォンタムエラー修正のサブフィールドで特に一般的です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="56ff9-190">では、同様の規則に従います。ここでは、 Q# この測定の別のビューについて説明します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="56ff9-191">P# li 測定を考える方法の詳細について検討する前に、クォンタムコンピューター内の1つの qubit がクォンタムの状態にどのように測定されるかについて考えることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="56ff9-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="56ff9-192">ここでは、 $ n qubit クォンタム状態になっていると $ します。その後、1つの qubit は、状態がである可能性がある 2 ^ n の可能性の半分を測定し $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="56ff9-193">つまり、測定値は、2つの半分の空白のいずれかにクォンタムの状態を投影します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="56ff9-194">この直感を反映するために、測定について考える方法を一般化できます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="56ff9-195">これらのサブスペースを簡潔に識別するためには、それらを説明するための言語が必要です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="56ff9-196">2つのサブスペースを記述する方法の1つとして、2つの一意の値を持つマトリックスを使用して指定する方法があります。これは、慣例によって午後1時に行われ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="56ff9-197">この方法でサブスペースを記述する簡単な例については、 $ Z $ :</span><span class="sxs-lookup"><span data-stu-id="56ff9-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="56ff9-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="56ff9-199">P# li-z マトリックスの対角線要素を読み取ることで、 $ $ Z に $ $ 2 つの固有ベクトル ( $ \ket { 0 と 1) があり、 } $ $ \ket { } $ 対応する固有値/ $ pm 1 $ があることがわかります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="56ff9-200">したがって、qubit を測定し、 `Zero` (状態0に対応する) を取得すると、 $ \ket { } $ qubit の状態が $ $ Z 演算子の + 1 eigenstate であることがわかり $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="56ff9-201">同様に、を取得した場合は、 `One` qubit の状態が $ z の-1 $ eigenstate であることがわかり $ $ ます。このプロセスは、「P# li Z の測定」として P# li 測定の言語で参照され $ $ ます。これは、計算ベースの測定を実行することとまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="56ff9-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="56ff9-202">$また、 \times $ Z の1つのユニタリ変換である 2 2 つのマトリックス $ も、 $ この条件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="56ff9-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="56ff9-203">つまり、マトリックス a $ = u ^ \dagger Z u を使用することもでき $ ます。ここで、 $ u $ は他の任意の長さ行列で、午後1時の固有ベクトルの測定の2つの結果を定義するマトリックスを提供し $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="56ff9-204">Preferences Li 測定の表記では、 $ X、Y、Z の各測定値を $ 等価の測定値として識別することで、このような値を参照します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="56ff9-205">これらの測定値は、便宜上、次のように提供されます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="56ff9-206">|P# li 測定の  | ユニタリ変換  |</span><span class="sxs-lookup"><span data-stu-id="56ff9-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="56ff9-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="56ff9-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="56ff9-208">|$ $ X |$H               $                    |</span><span class="sxs-lookup"><span data-stu-id="56ff9-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="56ff9-209">|$ $ Y |$HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="56ff9-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="56ff9-210">つまり、この言語を使用すると、"measure $ Y $ " は HS ^ を適用し $ \dagger $ た後、計算単位で測定することと同じです。ここで、は "フェーズゲート" と呼ばれる組み込みのクォンタム操作であり、これは、長さ [`S`](xref:microsoft.quantum.intrinsic.s) 行列によってシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="56ff9-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="56ff9-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="56ff9-212">1 & 0 \\\\ 0 & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="56ff9-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="56ff9-213">これは、 $ \dagger $ $ $ 次の演算がと等価になるように、クォンタムの状態ベクターに HS ^ を適用し、Z を測定 `Measure([PauliY], [q])` することと同じです。</span><span class="sxs-lookup"><span data-stu-id="56ff9-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="56ff9-214">その後、適切な状態が検出されます。これは、クォンタムの状態ベクターに SH を適用する量です $ $ 。上記のスニペットでは、計算ベースに戻る変換は、ブロックを使用することによって自動的に処理され `within … apply` ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="56ff9-215">では、結果と Q# ---して、州---との対話から抽出された古典的な情報は、値 j 0 によって与えられます。これは、測定された `Result` $ \in \\ { \texttt { } \texttt { } \\ } $ $ pauli 演算子の (-1) ^ j eigenspace に結果があるかどうかを示し $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="56ff9-216">複数の qubit 測定値</span><span class="sxs-lookup"><span data-stu-id="56ff9-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="56ff9-217">次に示すように、マルチ qubit の演算子の測定値は同様に定義されています。</span><span class="sxs-lookup"><span data-stu-id="56ff9-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="56ff9-218">Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & -1 0 0 0 0 & \\\\ & & & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1。</span><span class="sxs-lookup"><span data-stu-id="56ff9-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="56ff9-219">したがって、2つの Pauthentication Li z 演算子のすべての製品は、 $ $ $ + 1 と-1 の値で構成される2つのスペースで構成されるマトリックスを形成し $ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="56ff9-220">シングル qubit の場合と同様に、両方とも、アクセス可能なベクター空間の半分が $ + 1 eigspace に所属し、残りの半分が-1 の範囲に属していることを意味し $ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="56ff9-221">一般に、これに従うのは、Pdefinition Li の演算子と id のすべての情報が含まれているので、その製品の定義から簡単に確認でき $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="56ff9-222">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="56ff9-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="56ff9-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="56ff9-224">1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="56ff9-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="56ff9-226">0 &  0 & ~ 1 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="56ff9-227">0 0 0 & & & -1 \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="56ff9-228">前と同様に、このようなマトリックスのすべてのユニタリ変換では、- $ pm 1 eigenvalues によってラベル付けされた2つの半分の空白も記述さ $ れています。</span><span class="sxs-lookup"><span data-stu-id="56ff9-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="56ff9-229">たとえば、 $ \otimes = \otimes z hxh という id の x x h h (z \otimes z) h \otimes h のように $ $ = $ なります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="56ff9-230">1 qubit の場合と同様に、2つの2つのすべての値は、 $ \dagger \otimes \id $ $ 4 4 つの \times $ ユニタリマトリックス $ u の $ u ^ (Z) u として書き込むことができます。次の表に示す変換を列挙します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="56ff9-231">>次の表では、 $ \operatorname { SWAP を使用し } $ てマトリックス > を示しています。$$</span><span class="sxs-lookup"><span data-stu-id="56ff9-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="56ff9-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="56ff9-232">> \begin{align}</span></span>
<span data-ttu-id="56ff9-233">>     \operatorname{スワップ } &=</span><span class="sxs-lookup"><span data-stu-id="56ff9-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="56ff9-234">>     \left( \begin { マトリックス}</span><span class="sxs-lookup"><span data-stu-id="56ff9-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="56ff9-235">>1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="56ff9-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="56ff9-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="56ff9-238">>0 0 0 & & & 1 > \end { マトリックス } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="56ff9-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="56ff9-239">> $$</span><span class="sxs-lookup"><span data-stu-id="56ff9-239">> $$</span></span>
<span data-ttu-id="56ff9-240">> 組み込み操作をシミュレートするために使用され [`SWAP`](xref:microsoft.quantum.intrinsic) ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-240">> used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

<span data-ttu-id="56ff9-241">|P# li 測定の     | ユニタリ変換  |</span><span class="sxs-lookup"><span data-stu-id="56ff9-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="56ff9-242">|$ \otimes \boldone Z $| $\boldone\otimes\boldone$|</span><span class="sxs-lookup"><span data-stu-id="56ff9-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="56ff9-243">|$ \otimes \boldone X $| $\otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="56ff9-244">|$ \otimes \boldone Y $| $HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="56ff9-245">|$\boldone \otimesZ $ | $ \operatorname { スワップ } $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="56ff9-246">|$\boldone \otimesX $ | $ (H \otimes \boldone ) \operatorname { の } スワップ $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="56ff9-247">|$\boldone \otimesY $ | $ (HS ^ \dagger \otimes \boldone ) \operatorname { スワップ } $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="56ff9-248">|$Z \otimesZ $ | $ \operatorname { cnot } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="56ff9-249">|$X \otimesZ $ | $ \operatorname { cnot } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="56ff9-250">|$Y \otimesZ $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="56ff9-251">|$Z \otimesX $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="56ff9-252">|$X \otimesX $ | $ \operatorname { cnot } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="56ff9-253">|$Y \otimesX $ | $ \operatorname { cnot } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="56ff9-254">|$Z \otimesY $ | $ \operatorname { cnot } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="56ff9-255">|$X \otimesY $ | $ \operatorname { cnot } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="56ff9-256">|$Y \otimesY $ | $ \operatorname { cnot } \_ { 10 } (hs ^ \dagger \otimes hs ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="56ff9-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="56ff9-257">ここでは、 [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) 次の理由で操作が表示されます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-257">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="56ff9-258">マトリックスを含まない各 peach の測定値 $ \boldone $ は、 $ \otimes 上記の理由により、ユニタリから z z までと同等です $ 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="56ff9-259">Z z の固有値は、 $ \otimes $ 各計算ベースベクトルを構成する qubits のパリティに依存します。また、制御されていない操作は、このパリティを計算して最初のビットに格納します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="56ff9-260">次に、最初のビットを測定した後、結果として得られる半分の領域の id を回復できます。これは、P# li 演算子の測定に相当します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="56ff9-261">1つ追加の注意事項: $ z \otimes z $ は、 $ z \otimes \mathbb { 1 と 1 z を順番に測定するのと同じ } $ $ \mathbb { } \otimes $ であると想定されますが、この想定は false になります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="56ff9-262">その理由は、z z を測定すると、 $ \otimes $ $ $ これらの演算子の + 1 または-1 のいずれか $ $ の状態になります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="56ff9-263">$Z \otimes \mathbb { 1 } $ と $ \mathbb { 1 z を測定 } \otimes すると $ 、まずクォンタム状態ベクトルが z 1 の半分の領域に投影され、 $ 次に \otimes \mathbb { } $ 1 の半分の領域 $ \mathbb { } \otimes $ に投影されます。計算ベースのベクトルが4つあるため、両方の測定を実行すると、状態が4分の1に減少し、1つの計算ベースのベクトルに縮小されます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="56ff9-264">量子ビット間の相関関係</span><span class="sxs-lookup"><span data-stu-id="56ff9-264">Correlations between qubits</span></span>
<span data-ttu-id="56ff9-265">X x や z z などの P# li マトリックスの保存されていない製品を測定する別の方法として、 $ \otimes これらの $ $ \otimes $ 測定値を使用すると、2つの qubits 間の相関関係に格納されている情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="56ff9-266">$X \otimes \id $ を測定すると、最初の qubit にローカルに格納されている情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="56ff9-267">クォンタムコンピューティングではどちらの種類の測定も同等の価値がありますが、前者はクォンタムコンピューティングの能力を測定します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="56ff9-268">クォンタムコンピューティングでは、学習する情報が1つの qubit に格納されておらず、すべての qubit にローカルに格納されていないことがわかります。したがって、この情報は、結合測定 (z z など) を使用して参照することによってのみ、 $ \otimes マニフェストに $ なります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="56ff9-269">たとえば、エラー修正では、保護しようとしている状態について何も学習していないときに発生したエラーを確認したい場合がよくあります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="56ff9-270">[ビットフリップコードサンプル](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)では、 $ z z や z z などの測定値を使用してこれを行う方法の例を示して \otimes \otimes \id $ $ \id \otimes \otimes $ います。 <--TODO: ビットフリップコードサンプルがオンボードになるとすぐに、これをサンプルブラウザーへのリンクに変更します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="56ff9-271">$X \otimes Y \otimes Z などの任意の演算子 \otimes \boldone $ も測定できます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="56ff9-272">P# li 演算子のすべてのその他の製品には、2つの固有値- $ pm 1 しかあり $ ません。固有値はベクター空間全体の半分のスペースを構成します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="56ff9-273">そのため、これらは上記の要件と一致します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="56ff9-274">では Q# 、このような測定値が $ $ 結果を生成する場合は j が返され $ ます (-1) ^ j $ 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="56ff9-275">の組み込み機能として Pdiagonalizing の測定値を持つこと Q# は役に立ちます。このような演算子を測定するには、制御されていないゲートと基本変換の長いチェーンが必要であり、その操作を、 $ $ Z との積として表現するために必要な U ゲートを記述する必要があり $ $ $ \id $ ます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="56ff9-276">これらの定義済みの測定値のいずれかを実行することを指定できるようにすることで、計算ベースの測定によって必要な情報が得られるように、基になる方法を気にする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="56ff9-277">Q# 必要なすべての基準変換を自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="56ff9-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="56ff9-278">詳細については、「」および「」操作を参照してください [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-278">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="56ff9-279">複製なしの定理</span><span class="sxs-lookup"><span data-stu-id="56ff9-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="56ff9-280">クォンタム情報は強力です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-280">Quantum information is powerful.</span></span>
<span data-ttu-id="56ff9-281">これにより、最もよく知られている古典アルゴリズムよりも指数関数的に数値を指数関数的に処理できるようにすることが可能になります。また、正確にシミュレートするためにクラシックデプロイに必要な、関連する電子システムを効率的にシミュレートできます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="56ff9-282">ただし、クォンタムコンピューティングの能力には制限があります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="56ff9-283">このような制限は、 *複製なしの定理*によって与えられます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="56ff9-284">No 複製定理は、このという名前です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="56ff9-285">クォンタムコンピューターによる汎用クォンタム状態の複製は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="56ff9-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="56ff9-286">定理の証明は、非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="56ff9-287">この記事では、複製なしの定理の完全な証明については少し技術的に説明していますが、追加の補助 qubits を使用しない場合の証拠は、この範囲内にあります (補助 qubits は計算中にスクラッチ領域に使用され、で簡単に使用および管理され Q# ます)。 [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)</span><span class="sxs-lookup"><span data-stu-id="56ff9-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="56ff9-288">このようなクォンタムコンピューターでは、複製操作は、1つのユニタリ行列によって記述される必要があります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="56ff9-289">複製しようとしているクォンタムの状態が破損する可能性があるため、測定は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="56ff9-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="56ff9-290">複製操作をシミュレートするために、次のようなプロパティを持つために使用されている、 $$</span><span class="sxs-lookup"><span data-stu-id="56ff9-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="56ff9-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="56ff9-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="56ff9-292">任意の状態 $ \ket { \psi } $ 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="56ff9-293">マトリックス乗算の直線性プロパティは、2番目のクォンタム状態の場合 $ \ket { \phi } $ 、</span><span class="sxs-lookup"><span data-stu-id="56ff9-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="56ff9-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="56ff9-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="56ff9-295">&= \frac{1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="56ff9-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="56ff9-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="56ff9-297">&= \frac{1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="56ff9-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="56ff9-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="56ff9-298">\right) \\\\</span></span>
    <span data-ttu-id="56ff9-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right )) \right 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="56ff9-300">これにより、複製されていない定理の背後で基本的な直感が得られます。不明なクォンタム状態をコピーするデバイスは、少なくともそのコピーされた状態の中でエラーを誘発する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="56ff9-301">Cloner が入力状態で直線的に動作することを前提として、補助 qubits の追加や測定によって違反が発生する可能性がありますが、このような対話によって、測定統計を通じてシステムに関する情報が漏洩し、そのような場合には正確な複製を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="56ff9-302">複製なしの定理の詳細については、「」 [を](xref:microsoft.quantum.more-information)参照してください。</span><span class="sxs-lookup"><span data-stu-id="56ff9-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="56ff9-303">クォンタムの状態を複製できる場合は、クォンタムの状態についての理解を深めることができるので、定理の複製は、クォンタムの計算にとって重要です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="56ff9-304">実際には、ハイゼンベルグの vaunted の不確定性の原則に違反する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56ff9-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="56ff9-305">または、最適な cloner を使用して、複雑なクォンタム分布から1つのサンプルを取得し、1つのサンプルだけからその分布について学習できる可能性のあるすべてのことを学ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="56ff9-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="56ff9-306">これは、コインと観察ヘッドを反転し、その結果について友人に伝えたときに、そのコインの分布が $ p = 0.512643 \ ldots でベルヌーイでなければならないということです $ 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="56ff9-307">このようなステートメントは非 sensical になります。これは、1つの情報 (ヘッドの結果) は、十分な前の情報を使用せずに、分布をエンコードするために必要な多くの情報を提供できないためです。</span><span class="sxs-lookup"><span data-stu-id="56ff9-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="56ff9-308">同様に、事前の情報がないと、p を知らなくても、このようなコインを完全に複製することはできません $ $ 。</span><span class="sxs-lookup"><span data-stu-id="56ff9-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="56ff9-309">クォンタムコンピューティングでは、情報は無料です。</span><span class="sxs-lookup"><span data-stu-id="56ff9-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="56ff9-310">測定された各 qubit は1ビットの情報を提供し、複製なしの定理は、システムに関する情報とそれに対して発生した問題の基本的なトレードオフを回避するために、攻撃を受ける可能性があるバックドアがないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="56ff9-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
