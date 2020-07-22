---
<span data-ttu-id="bf417-101">title: クォンタム oracles の説明: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf417-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="bf417-102">執筆者: cgranade uid: oracles: Christopher.Granade@microsoft.com ms. date: 07/11/2018 ms. topic: article no loc (次の説明を参照):</span><span class="sxs-lookup"><span data-stu-id="bf417-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="bf417-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="bf417-103">"$$"</span></span>
- <span data-ttu-id="bf417-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="bf417-104">"$$"</span></span>
- <span data-ttu-id="bf417-105">"$"</span><span class="sxs-lookup"><span data-stu-id="bf417-105">"$"</span></span>
- <span data-ttu-id="bf417-106">"$"</span><span class="sxs-lookup"><span data-stu-id="bf417-106">"$"</span></span>
- <span data-ttu-id="bf417-107">"$"</span><span class="sxs-lookup"><span data-stu-id="bf417-107">"$"</span></span>
- <span data-ttu-id="bf417-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="bf417-108">"$$"</span></span>
- <span data-ttu-id="bf417-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="bf417-109">"\cdots"</span></span>
- <span data-ttu-id="bf417-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="bf417-110">"bmatrix"</span></span>
- <span data-ttu-id="bf417-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="bf417-111">"\ddots"</span></span>
- <span data-ttu-id="bf417-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="bf417-112">"\equiv"</span></span>
- <span data-ttu-id="bf417-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="bf417-113">"\sum"</span></span>
- <span data-ttu-id="bf417-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="bf417-114">"\begin"</span></span>
- <span data-ttu-id="bf417-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="bf417-115">"\end"</span></span>
- <span data-ttu-id="bf417-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="bf417-116">"\sqrt"</span></span>
- <span data-ttu-id="bf417-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="bf417-117">"\otimes"</span></span>
- <span data-ttu-id="bf417-118">"{"</span><span class="sxs-lookup"><span data-stu-id="bf417-118">"{"</span></span>
- <span data-ttu-id="bf417-119">"}"</span><span class="sxs-lookup"><span data-stu-id="bf417-119">"}"</span></span>
- <span data-ttu-id="bf417-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="bf417-120">"\text"</span></span>
- <span data-ttu-id="bf417-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="bf417-121">"\phi"</span></span>
- <span data-ttu-id="bf417-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="bf417-122">"\kappa"</span></span>
- <span data-ttu-id="bf417-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="bf417-123">"\psi"</span></span>
- <span data-ttu-id="bf417-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="bf417-124">"\alpha"</span></span>
- <span data-ttu-id="bf417-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="bf417-125">"\beta"</span></span>
- <span data-ttu-id="bf417-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="bf417-126">"\gamma"</span></span>
- <span data-ttu-id="bf417-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="bf417-127">"\delta"</span></span>
- <span data-ttu-id="bf417-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="bf417-128">"\omega"</span></span>
- <span data-ttu-id="bf417-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="bf417-129">"\bra"</span></span>
- <span data-ttu-id="bf417-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="bf417-130">"\ket"</span></span>
- <span data-ttu-id="bf417-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="bf417-131">"\boldone"</span></span>
- <span data-ttu-id="bf417-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="bf417-132">"\\\\"</span></span>
- <span data-ttu-id="bf417-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="bf417-133">"\\"</span></span>
- <span data-ttu-id="bf417-134">"="</span><span class="sxs-lookup"><span data-stu-id="bf417-134">"="</span></span>
- <span data-ttu-id="bf417-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="bf417-135">"\frac"</span></span>
- <span data-ttu-id="bf417-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="bf417-136">"\text"</span></span>
- <span data-ttu-id="bf417-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="bf417-137">"\mapsto"</span></span>
- <span data-ttu-id="bf417-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="bf417-138">"\dagger"</span></span>
- <span data-ttu-id="bf417-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="bf417-139">"\to"</span></span>
- <span data-ttu-id="bf417-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="bf417-140">"\begin{cases}"</span></span>
- <span data-ttu-id="bf417-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="bf417-141">"\end{cases}"</span></span>
- <span data-ttu-id="bf417-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="bf417-142">"\operatorname"</span></span>
- <span data-ttu-id="bf417-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="bf417-143">"\braket"</span></span>
- <span data-ttu-id="bf417-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="bf417-144">"\id"</span></span>
- <span data-ttu-id="bf417-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="bf417-145">"\expect"</span></span>
- <span data-ttu-id="bf417-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="bf417-146">"\defeq"</span></span>
- <span data-ttu-id="bf417-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="bf417-147">"\variance"</span></span>
- <span data-ttu-id="bf417-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="bf417-148">"\dd"</span></span>
- <span data-ttu-id="bf417-149">"&"</span><span class="sxs-lookup"><span data-stu-id="bf417-149">"&"</span></span>
- <span data-ttu-id="bf417-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="bf417-150">"\begin{align}"</span></span>
- <span data-ttu-id="bf417-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="bf417-151">"\end{align}"</span></span>
- <span data-ttu-id="bf417-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="bf417-152">"\Lambda"</span></span>
- <span data-ttu-id="bf417-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="bf417-153">"\lambda"</span></span>
- <span data-ttu-id="bf417-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="bf417-154">"\Omega"</span></span>
- <span data-ttu-id="bf417-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="bf417-155">"\mathrm"</span></span>
- <span data-ttu-id="bf417-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="bf417-156">"\left"</span></span>
- <span data-ttu-id="bf417-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="bf417-157">"\right"</span></span>
- <span data-ttu-id="bf417-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="bf417-158">"\qquad"</span></span>
- <span data-ttu-id="bf417-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="bf417-159">"\times"</span></span>
- <span data-ttu-id="bf417-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="bf417-160">"\big"</span></span>
- <span data-ttu-id="bf417-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="bf417-161">"\langle"</span></span>
- <span data-ttu-id="bf417-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="bf417-162">"\rangle"</span></span>
- <span data-ttu-id="bf417-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="bf417-163">"\bigg"</span></span>
- <span data-ttu-id="bf417-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="bf417-164">"\Big"</span></span>
- <span data-ttu-id="bf417-165">"|"</span><span class="sxs-lookup"><span data-stu-id="bf417-165">"|"</span></span>
- <span data-ttu-id="bf417-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="bf417-166">"\mathbb"</span></span>
- <span data-ttu-id="bf417-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="bf417-167">"\vec"</span></span>
- <span data-ttu-id="bf417-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="bf417-168">"\in"</span></span>
- <span data-ttu-id="bf417-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="bf417-169">"\texttt"</span></span>
- <span data-ttu-id="bf417-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="bf417-170">"\ne"</span></span>
- <span data-ttu-id="bf417-171">"<"</span><span class="sxs-lookup"><span data-stu-id="bf417-171">"<"</span></span>
- <span data-ttu-id="bf417-172">">"</span><span class="sxs-lookup"><span data-stu-id="bf417-172">">"</span></span>
- <span data-ttu-id="bf417-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="bf417-173">"\leq"</span></span>
- <span data-ttu-id="bf417-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="bf417-174">"\geq"</span></span>
- <span data-ttu-id="bf417-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="bf417-175">"~~"</span></span>
- <span data-ttu-id="bf417-176">"~"</span><span class="sxs-lookup"><span data-stu-id="bf417-176">"~"</span></span>
- <span data-ttu-id="bf417-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="bf417-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="bf417-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="bf417-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="bf417-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="bf417-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="bf417-180">Quantum Oracles</span><span class="sxs-lookup"><span data-stu-id="bf417-180">Quantum Oracles</span></span>

<span data-ttu-id="bf417-181">Oracle $ O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。</span><span class="sxs-lookup"><span data-stu-id="bf417-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="bf417-182">多くの場合、このような操作は従来の関数 $ f: \\ { 0、1 ^ n 0、1 ^ m を使用して定義されます \\ } \to \\ { \\ } $ 。これは $ n $ ビットのバイナリ入力を受け取り、 $ m ビットのバイナリ出力を生成し $ ます。</span><span class="sxs-lookup"><span data-stu-id="bf417-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="bf417-183">これを行うには、特定のバイナリ入力 $ x = (x_ { 0 } 、x_ { 1 } 、\ ドット、x_ { n-1) } $ を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="bf417-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="bf417-184">Qubit 状態には $ \ket { \vec { } } = \ket { 、x x_ { 0 } } \otimes \ket { x_ { 1 x_ } } \otimes \cdots \otimes \ket { { n-1 } } $ というラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="bf417-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="bf417-185">最初に o x f (x) を定義しようとし $ $ てい $ \ket { } = \ket { } $ ますが、これにはいくつかの問題があります。</span><span class="sxs-lookup"><span data-stu-id="bf417-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="bf417-186">まず、 $ f の $ 場合、入力と出力のサイズが異なり $ ます (n \ne m $ )。 O を適用すると $ レジスタの $ qubits の数が変わることがあります。</span><span class="sxs-lookup"><span data-stu-id="bf417-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="bf417-187">2つ目は、n m の場合でも、関数が反転できるになら $ = $ ない可能性があります。 $ f (x) = f (y) がある $ $ x y の場合 \ne $ 、 $ o \ket { x } = o \ket { y で } $ は $ o ^ \dagger o \ket { x } \ne o ^ o \dagger \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="bf417-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="bf417-188">つまり、adjoint 操作 O ^ を作成することはできません $ \dagger $ 。また、oracles には adjoint が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf417-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="bf417-189">計算ベースの状態に影響を与える oracle の定義</span><span class="sxs-lookup"><span data-stu-id="bf417-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="bf417-190">これらの問題の両方に対処するには、 $ 回答を保持する2番目の m qubits のレジスタを導入し $ ます。</span><span class="sxs-lookup"><span data-stu-id="bf417-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="bf417-191">次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $ x \in \\ { 0、1 \\ } ^ n、 $ および $ y \in \\ { 0、1 \\ } ^ m $</span><span class="sxs-lookup"><span data-stu-id="bf417-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="bf417-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \ oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="bf417-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="bf417-193">ここで $ o = ^ は \dagger $ 構築によって、以前の問題を解決しました。</span><span class="sxs-lookup"><span data-stu-id="bf417-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="bf417-194">O ^ 2 があることを確認するには、 $ = { \dagger } $ $ o ^ 2 = \boldone $ $ = $ $ \in \[ が b と b の a a、b!ファンド.NO LOC ({)] 0, 1 \[ !ファンド.なし (})] $ 。</span><span class="sxs-lookup"><span data-stu-id="bf417-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="bf417-195">結果として、 $ O \ket { x y と f } \ket { (x) } = \ket { x } \ket { y/oplus f (x) & oplus f (x) } = \ket { x } \ket { y } $ です。</span><span class="sxs-lookup"><span data-stu-id="bf417-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="bf417-196">重要な点として、各計算基準の状態 x y に対して oracle を定義することで、 $ \ket { } \ket { } $ O が $ 他の状態にどのように作用するかも定義し $ ます。</span><span class="sxs-lookup"><span data-stu-id="bf417-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="bf417-197">これは、すべてのクォンタム操作と同様に、処理が実行されている $ 状態で線形であるという事実からすぐに続き $ ます。</span><span class="sxs-lookup"><span data-stu-id="bf417-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="bf417-198">たとえば、 $ h \ket { 0 } = \ket { + } $ と $ h \ket { 1 } = \ket { - } $ で定義されている Hadamard 操作を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="bf417-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="bf417-199">H がどのように動作するかを知りたい場合は、 $ $ h を $ \ket { + } $ $ $ 線形にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf417-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="bf417-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + H \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="bf417-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="bf417-201">= \frac{1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 1 }  -  \ket { } ) = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="bf417-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="bf417-202">Oracle O を定義する場合は $ $ 、 $ \ket { \psi } $ $ n + m $ qubits の任意の状態を次のように記述できると同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf417-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="bf417-203">{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="bf417-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="bf417-204">ここで $ \alpha : \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C は } $ 、状態の係数を表し $ \ket { \psi } $ ます。</span><span class="sxs-lookup"><span data-stu-id="bf417-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="bf417-205">したがって</span><span class="sxs-lookup"><span data-stu-id="bf417-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="bf417-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="bf417-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="bf417-207">= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y/oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="bf417-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="bf417-208">フェーズ oracles</span><span class="sxs-lookup"><span data-stu-id="bf417-208">Phase oracles</span></span>
<span data-ttu-id="bf417-209">または、 $ $ $ $ O への入力に基づいて_フェーズ_を適用して、f を oracle O にエンコード $ することもでき $ ます。たとえば、次のような O を定義する場合があります。 $ $$$</span><span class="sxs-lookup"><span data-stu-id="bf417-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="bf417-210">O \ket { x } = (-1) ^ { f (x) } \ket { x }</span><span class="sxs-lookup"><span data-stu-id="bf417-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="bf417-211">フェーズ oracle が最初に計算ベースの状態 x でレジスタに対して動作する場合 $ \ket { } $ 、このフェーズはグローバルフェーズであるため、監視できません。</span><span class="sxs-lookup"><span data-stu-id="bf417-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="bf417-212">ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="bf417-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="bf417-213">たとえば、 $ $ 1 つの-qubit 関数 f の場合、oracle の O_f フェーズを考えてみましょう $ $ 。</span><span class="sxs-lookup"><span data-stu-id="bf417-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="bf417-214">そうしたら$$</span><span class="sxs-lookup"><span data-stu-id="bf417-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="bf417-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="bf417-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="bf417-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="bf417-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="bf417-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="bf417-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="bf417-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="bf417-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="bf417-219">=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } 。</span><span class="sxs-lookup"><span data-stu-id="bf417-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="bf417-220">一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf417-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="bf417-221">Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="bf417-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="bf417-222">たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm)は2番目の方法で実装された oracle に依存しています。</span><span class="sxs-lookup"><span data-stu-id="bf417-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="bf417-223">詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf417-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
