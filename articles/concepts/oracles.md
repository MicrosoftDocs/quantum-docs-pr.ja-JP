---
<span data-ttu-id="d82ea-101">title: クォンタム oracles の説明: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d82ea-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="d82ea-102">執筆者: cgranade uid: oracles: chgranad ms. date: 07/11/2018 ms. topic: article no loc (次の説明を参照):</span><span class="sxs-lookup"><span data-stu-id="d82ea-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="d82ea-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="d82ea-103">"Q#"</span></span>
- <span data-ttu-id="d82ea-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="d82ea-104">"$$v"</span></span>
- <span data-ttu-id="d82ea-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="d82ea-105">"$$"</span></span>
- <span data-ttu-id="d82ea-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="d82ea-106">"$$"</span></span>
- <span data-ttu-id="d82ea-107">"$"</span><span class="sxs-lookup"><span data-stu-id="d82ea-107">"$"</span></span>
- <span data-ttu-id="d82ea-108">"$"</span><span class="sxs-lookup"><span data-stu-id="d82ea-108">"$"</span></span>
- <span data-ttu-id="d82ea-109">"$"</span><span class="sxs-lookup"><span data-stu-id="d82ea-109">"$"</span></span>
- <span data-ttu-id="d82ea-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="d82ea-110">"$$"</span></span>
- <span data-ttu-id="d82ea-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="d82ea-111">"\cdots"</span></span>
- <span data-ttu-id="d82ea-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="d82ea-112">"bmatrix"</span></span>
- <span data-ttu-id="d82ea-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="d82ea-113">"\ddots"</span></span>
- <span data-ttu-id="d82ea-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="d82ea-114">"\equiv"</span></span>
- <span data-ttu-id="d82ea-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="d82ea-115">"\sum"</span></span>
- <span data-ttu-id="d82ea-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="d82ea-116">"\begin"</span></span>
- <span data-ttu-id="d82ea-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="d82ea-117">"\end"</span></span>
- <span data-ttu-id="d82ea-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="d82ea-118">"\sqrt"</span></span>
- <span data-ttu-id="d82ea-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="d82ea-119">"\otimes"</span></span>
- <span data-ttu-id="d82ea-120">"{"</span><span class="sxs-lookup"><span data-stu-id="d82ea-120">"{"</span></span>
- <span data-ttu-id="d82ea-121">"}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-121">"}"</span></span>
- <span data-ttu-id="d82ea-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="d82ea-122">"\text"</span></span>
- <span data-ttu-id="d82ea-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="d82ea-123">"\phi"</span></span>
- <span data-ttu-id="d82ea-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="d82ea-124">"\kappa"</span></span>
- <span data-ttu-id="d82ea-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="d82ea-125">"\psi"</span></span>
- <span data-ttu-id="d82ea-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="d82ea-126">"\alpha"</span></span>
- <span data-ttu-id="d82ea-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="d82ea-127">"\beta"</span></span>
- <span data-ttu-id="d82ea-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="d82ea-128">"\gamma"</span></span>
- <span data-ttu-id="d82ea-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="d82ea-129">"\delta"</span></span>
- <span data-ttu-id="d82ea-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="d82ea-130">"\omega"</span></span>
- <span data-ttu-id="d82ea-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="d82ea-131">"\bra"</span></span>
- <span data-ttu-id="d82ea-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="d82ea-132">"\ket"</span></span>
- <span data-ttu-id="d82ea-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="d82ea-133">"\boldone"</span></span>
- <span data-ttu-id="d82ea-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="d82ea-134">"\\\\"</span></span>
- <span data-ttu-id="d82ea-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="d82ea-135">"\\"</span></span>
- <span data-ttu-id="d82ea-136">"="</span><span class="sxs-lookup"><span data-stu-id="d82ea-136">"="</span></span>
- <span data-ttu-id="d82ea-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="d82ea-137">"\frac"</span></span>
- <span data-ttu-id="d82ea-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="d82ea-138">"\text"</span></span>
- <span data-ttu-id="d82ea-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="d82ea-139">"\mapsto"</span></span>
- <span data-ttu-id="d82ea-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="d82ea-140">"\dagger"</span></span>
- <span data-ttu-id="d82ea-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="d82ea-141">"\to"</span></span>
- <span data-ttu-id="d82ea-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-142">"\begin{cases}"</span></span>
- <span data-ttu-id="d82ea-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-143">"\end{cases}"</span></span>
- <span data-ttu-id="d82ea-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="d82ea-144">"\operatorname"</span></span>
- <span data-ttu-id="d82ea-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="d82ea-145">"\braket"</span></span>
- <span data-ttu-id="d82ea-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="d82ea-146">"\id"</span></span>
- <span data-ttu-id="d82ea-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="d82ea-147">"\expect"</span></span>
- <span data-ttu-id="d82ea-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="d82ea-148">"\defeq"</span></span>
- <span data-ttu-id="d82ea-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="d82ea-149">"\variance"</span></span>
- <span data-ttu-id="d82ea-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="d82ea-150">"\dd"</span></span>
- <span data-ttu-id="d82ea-151">"&"</span><span class="sxs-lookup"><span data-stu-id="d82ea-151">"&"</span></span>
- <span data-ttu-id="d82ea-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-152">"\begin{align}"</span></span>
- <span data-ttu-id="d82ea-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-153">"\end{align}"</span></span>
- <span data-ttu-id="d82ea-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="d82ea-154">"\Lambda"</span></span>
- <span data-ttu-id="d82ea-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="d82ea-155">"\lambda"</span></span>
- <span data-ttu-id="d82ea-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="d82ea-156">"\Omega"</span></span>
- <span data-ttu-id="d82ea-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="d82ea-157">"\mathrm"</span></span>
- <span data-ttu-id="d82ea-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="d82ea-158">"\left"</span></span>
- <span data-ttu-id="d82ea-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="d82ea-159">"\right"</span></span>
- <span data-ttu-id="d82ea-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="d82ea-160">"\qquad"</span></span>
- <span data-ttu-id="d82ea-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="d82ea-161">"\times"</span></span>
- <span data-ttu-id="d82ea-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="d82ea-162">"\big"</span></span>
- <span data-ttu-id="d82ea-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="d82ea-163">"\langle"</span></span>
- <span data-ttu-id="d82ea-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="d82ea-164">"\rangle"</span></span>
- <span data-ttu-id="d82ea-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="d82ea-165">"\bigg"</span></span>
- <span data-ttu-id="d82ea-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="d82ea-166">"\Big"</span></span>
- <span data-ttu-id="d82ea-167">"|"</span><span class="sxs-lookup"><span data-stu-id="d82ea-167">"|"</span></span>
- <span data-ttu-id="d82ea-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="d82ea-168">"\mathbb"</span></span>
- <span data-ttu-id="d82ea-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="d82ea-169">"\vec"</span></span>
- <span data-ttu-id="d82ea-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="d82ea-170">"\in"</span></span>
- <span data-ttu-id="d82ea-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="d82ea-171">"\texttt"</span></span>
- <span data-ttu-id="d82ea-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="d82ea-172">"\ne"</span></span>
- <span data-ttu-id="d82ea-173">"<"</span><span class="sxs-lookup"><span data-stu-id="d82ea-173">"<"</span></span>
- <span data-ttu-id="d82ea-174">">"</span><span class="sxs-lookup"><span data-stu-id="d82ea-174">">"</span></span>
- <span data-ttu-id="d82ea-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="d82ea-175">"\leq"</span></span>
- <span data-ttu-id="d82ea-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="d82ea-176">"\geq"</span></span>
- <span data-ttu-id="d82ea-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="d82ea-177">"~~"</span></span>
- <span data-ttu-id="d82ea-178">"~"</span><span class="sxs-lookup"><span data-stu-id="d82ea-178">"~"</span></span>
- <span data-ttu-id="d82ea-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="d82ea-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="d82ea-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="d82ea-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="d82ea-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="d82ea-182">Quantum Oracles</span><span class="sxs-lookup"><span data-stu-id="d82ea-182">Quantum Oracles</span></span>

<span data-ttu-id="d82ea-183">Oracle $ O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。</span><span class="sxs-lookup"><span data-stu-id="d82ea-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="d82ea-184">多くの場合、このような操作は従来の関数 $ f: \\ { 0、1 ^ n 0、1 ^ m を使用して定義されます \\ } \to \\ { \\ } $ 。これは $ n $ ビットのバイナリ入力を受け取り、 $ m ビットのバイナリ出力を生成し $ ます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="d82ea-185">これを行うには、特定のバイナリ入力 $ x = (x_ { 0 } 、x_ { 1 } 、\ ドット、x_ { n-1) } $ を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d82ea-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="d82ea-186">Qubit 状態には $ \ket { \vec { } } = \ket { 、x x_ { 0 } } \otimes \ket { x_ { 1 x_ } } \otimes \cdots \otimes \ket { { n-1 } } $ というラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="d82ea-187">最初に o x f (x) を定義しようとし $ $ てい $ \ket { } = \ket { } $ ますが、これにはいくつかの問題があります。</span><span class="sxs-lookup"><span data-stu-id="d82ea-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="d82ea-188">まず、 $ f の $ 場合、入力と出力のサイズが異なり $ ます (n \ne m $ )。 O を適用すると $ レジスタの $ qubits の数が変わることがあります。</span><span class="sxs-lookup"><span data-stu-id="d82ea-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="d82ea-189">2つ目は、n m の場合でも、関数が反転できるになら $ = $ ない可能性があります。 $ f (x) = f (y) がある $ $ x y の場合 \ne $ 、 $ o \ket { x } = o \ket { y で } $ は $ o ^ \dagger o \ket { x } \ne o ^ o \dagger \ket { y } $ 。</span><span class="sxs-lookup"><span data-stu-id="d82ea-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="d82ea-190">つまり、adjoint 操作 O ^ を作成することはできません $ \dagger $ 。また、oracles には adjoint が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d82ea-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="d82ea-191">計算ベースの状態に影響を与える oracle の定義</span><span class="sxs-lookup"><span data-stu-id="d82ea-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="d82ea-192">これらの問題の両方に対処するには、 $ 回答を保持する2番目の m qubits のレジスタを導入し $ ます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="d82ea-193">次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $ x \in \\ { 0、1 \\ } ^ n、 $ および $ y \in \\ { 0、1 \\ } ^ m $</span><span class="sxs-lookup"><span data-stu-id="d82ea-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="d82ea-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \ oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="d82ea-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="d82ea-195">ここで $ o = ^ は \dagger $ 構築によって、以前の問題を解決しました。</span><span class="sxs-lookup"><span data-stu-id="d82ea-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="d82ea-196">>O ^ 2 であることを確認するには、 $ = { \dagger } $ $ o ^ 2 が a a = \boldone $ 、b $ = $ $ \in \: :: no-loc ({)::: 0、1 \: :: no loc (})::: $ のいずれかであることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d82ea-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="d82ea-197">>結果として、 $ O \ket { x y と f } \ket { (x) } = \ket { x } \ket { y/oplus f (x) & oplus f (x) } = \ket { x } \ket { y } $ です。</span><span class="sxs-lookup"><span data-stu-id="d82ea-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="d82ea-198">重要な点として、各計算基準の状態 x y に対して oracle を定義することで、 $ \ket { } \ket { } $ O が $ 他の状態にどのように作用するかも定義し $ ます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="d82ea-199">これは、すべてのクォンタム操作と同様に、処理が実行されている $ 状態で線形であるという事実からすぐに続き $ ます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="d82ea-200">たとえば、 $ h \ket { 0 } = \ket { + } $ と $ h \ket { 1 } = \ket { - } $ で定義されている Hadamard 操作を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="d82ea-201">H がどのように動作するかを知りたい場合は、 $ $ h を $ \ket { + } $ $ $ 線形にすることができます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="d82ea-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + H \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="d82ea-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="d82ea-203">&= \frac{1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 1 }  -  \ket { } ) = \ket { 0 } 。</span><span class="sxs-lookup"><span data-stu-id="d82ea-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="d82ea-204">Oracle O を定義する場合は $ $ 、 $ \ket { \psi } $ $ n + m $ qubits の任意の状態を次のように記述できると同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="d82ea-205">\ket{\psi}& = \sum_ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x、y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="d82ea-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="d82ea-206">ここで $ \alpha : \\ { 0、1 \\ } ^ n \times \\ { 0、1 \\ } ^ m \to \mathbb { C は } $ 、状態の係数を表し $ \ket { \psi } $ ます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="d82ea-207">したがって</span><span class="sxs-lookup"><span data-stu-id="d82ea-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="d82ea-208">O \ket { \psi } & = o \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & 、 = 1 ^ n、y 0、1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="d82ea-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="d82ea-209">&= \sum _ { x \in \\ { 0、1 \\ } ^ n、y \in \\ { 0、1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y/oplus f (x) } 。</span><span class="sxs-lookup"><span data-stu-id="d82ea-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="d82ea-210">フェーズ oracles</span><span class="sxs-lookup"><span data-stu-id="d82ea-210">Phase oracles</span></span>
<span data-ttu-id="d82ea-211">または、 $ $ $ $ O への入力に基づいて_フェーズ_を適用して、f を oracle O にエンコード $ することもでき $ ます。たとえば、次のような O を定義する場合があります。 $ $$$</span><span class="sxs-lookup"><span data-stu-id="d82ea-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="d82ea-212">O \ket { x } = (-1) ^ { f (x) } \ket { x }</span><span class="sxs-lookup"><span data-stu-id="d82ea-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="d82ea-213">フェーズ oracle が最初に計算ベースの状態 x でレジスタに対して動作する場合 $ \ket { } $ 、このフェーズはグローバルフェーズであるため、監視できません。</span><span class="sxs-lookup"><span data-stu-id="d82ea-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="d82ea-214">ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="d82ea-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="d82ea-215">たとえば、 $ $ 1 つの-qubit 関数 f の場合、oracle の O_f フェーズを考えてみましょう $ $ 。</span><span class="sxs-lookup"><span data-stu-id="d82ea-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="d82ea-216">そうしたら $$</span><span class="sxs-lookup"><span data-stu-id="d82ea-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="d82ea-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="d82ea-217">O_f \ket{+}</span></span>
        <span data-ttu-id="d82ea-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="d82ea-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="d82ea-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="d82ea-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="d82ea-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="d82ea-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="d82ea-221">&=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } 。</span><span class="sxs-lookup"><span data-stu-id="d82ea-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="d82ea-222">一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="d82ea-222">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="d82ea-223">Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="d82ea-223">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="d82ea-224">たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm) は2番目の方法で実装された oracle に依存しています。</span><span class="sxs-lookup"><span data-stu-id="d82ea-224">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="d82ea-225">詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d82ea-225">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
