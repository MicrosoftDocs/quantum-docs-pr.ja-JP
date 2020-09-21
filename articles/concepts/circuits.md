---
<span data-ttu-id="f2374-101">タイトル: クォンタム回線の説明: 量子回線図を使用して、単純で複雑なクォンタム操作を視覚的に表現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2374-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="f2374-102">author: QuantumWriter uid: benbra: v-ms. date: 12/11/2017 ms. topic: article no loc (場所の記事):</span><span class="sxs-lookup"><span data-stu-id="f2374-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="f2374-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="f2374-103">"Q#"</span></span>
- <span data-ttu-id="f2374-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="f2374-104">"$$v"</span></span>
- <span data-ttu-id="f2374-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="f2374-105">"$$"</span></span>
- <span data-ttu-id="f2374-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="f2374-106">"$$"</span></span>
- <span data-ttu-id="f2374-107">"$"</span><span class="sxs-lookup"><span data-stu-id="f2374-107">"$"</span></span>
- <span data-ttu-id="f2374-108">"$"</span><span class="sxs-lookup"><span data-stu-id="f2374-108">"$"</span></span>
- <span data-ttu-id="f2374-109">"$"</span><span class="sxs-lookup"><span data-stu-id="f2374-109">"$"</span></span>
- <span data-ttu-id="f2374-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="f2374-110">"$$"</span></span>
- <span data-ttu-id="f2374-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="f2374-111">"\cdots"</span></span>
- <span data-ttu-id="f2374-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="f2374-112">"bmatrix"</span></span>
- <span data-ttu-id="f2374-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="f2374-113">"\ddots"</span></span>
- <span data-ttu-id="f2374-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="f2374-114">"\equiv"</span></span>
- <span data-ttu-id="f2374-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="f2374-115">"\sum"</span></span>
- <span data-ttu-id="f2374-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="f2374-116">"\begin"</span></span>
- <span data-ttu-id="f2374-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="f2374-117">"\end"</span></span>
- <span data-ttu-id="f2374-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="f2374-118">"\sqrt"</span></span>
- <span data-ttu-id="f2374-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="f2374-119">"\otimes"</span></span>
- <span data-ttu-id="f2374-120">"{"</span><span class="sxs-lookup"><span data-stu-id="f2374-120">"{"</span></span>
- <span data-ttu-id="f2374-121">"}"</span><span class="sxs-lookup"><span data-stu-id="f2374-121">"}"</span></span>
- <span data-ttu-id="f2374-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="f2374-122">"\text"</span></span>
- <span data-ttu-id="f2374-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="f2374-123">"\phi"</span></span>
- <span data-ttu-id="f2374-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="f2374-124">"\kappa"</span></span>
- <span data-ttu-id="f2374-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="f2374-125">"\psi"</span></span>
- <span data-ttu-id="f2374-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="f2374-126">"\alpha"</span></span>
- <span data-ttu-id="f2374-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="f2374-127">"\beta"</span></span>
- <span data-ttu-id="f2374-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="f2374-128">"\gamma"</span></span>
- <span data-ttu-id="f2374-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="f2374-129">"\delta"</span></span>
- <span data-ttu-id="f2374-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="f2374-130">"\omega"</span></span>
- <span data-ttu-id="f2374-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="f2374-131">"\bra"</span></span>
- <span data-ttu-id="f2374-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="f2374-132">"\ket"</span></span>
- <span data-ttu-id="f2374-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="f2374-133">"\boldone"</span></span>
- <span data-ttu-id="f2374-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="f2374-134">"\\\\"</span></span>
- <span data-ttu-id="f2374-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="f2374-135">"\\"</span></span>
- <span data-ttu-id="f2374-136">"="</span><span class="sxs-lookup"><span data-stu-id="f2374-136">"="</span></span>
- <span data-ttu-id="f2374-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="f2374-137">"\frac"</span></span>
- <span data-ttu-id="f2374-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="f2374-138">"\text"</span></span>
- <span data-ttu-id="f2374-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="f2374-139">"\mapsto"</span></span>
- <span data-ttu-id="f2374-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="f2374-140">"\dagger"</span></span>
- <span data-ttu-id="f2374-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="f2374-141">"\to"</span></span>
- <span data-ttu-id="f2374-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="f2374-142">"\begin{cases}"</span></span>
- <span data-ttu-id="f2374-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="f2374-143">"\end{cases}"</span></span>
- <span data-ttu-id="f2374-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="f2374-144">"\operatorname"</span></span>
- <span data-ttu-id="f2374-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="f2374-145">"\braket"</span></span>
- <span data-ttu-id="f2374-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="f2374-146">"\id"</span></span>
- <span data-ttu-id="f2374-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="f2374-147">"\expect"</span></span>
- <span data-ttu-id="f2374-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="f2374-148">"\defeq"</span></span>
- <span data-ttu-id="f2374-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="f2374-149">"\variance"</span></span>
- <span data-ttu-id="f2374-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="f2374-150">"\dd"</span></span>
- <span data-ttu-id="f2374-151">"&"</span><span class="sxs-lookup"><span data-stu-id="f2374-151">"&"</span></span>
- <span data-ttu-id="f2374-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="f2374-152">"\begin{align}"</span></span>
- <span data-ttu-id="f2374-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="f2374-153">"\end{align}"</span></span>
- <span data-ttu-id="f2374-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="f2374-154">"\Lambda"</span></span>
- <span data-ttu-id="f2374-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="f2374-155">"\lambda"</span></span>
- <span data-ttu-id="f2374-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="f2374-156">"\Omega"</span></span>
- <span data-ttu-id="f2374-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="f2374-157">"\mathrm"</span></span>
- <span data-ttu-id="f2374-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="f2374-158">"\left"</span></span>
- <span data-ttu-id="f2374-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="f2374-159">"\right"</span></span>
- <span data-ttu-id="f2374-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="f2374-160">"\qquad"</span></span>
- <span data-ttu-id="f2374-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="f2374-161">"\times"</span></span>
- <span data-ttu-id="f2374-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="f2374-162">"\big"</span></span>
- <span data-ttu-id="f2374-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="f2374-163">"\langle"</span></span>
- <span data-ttu-id="f2374-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="f2374-164">"\rangle"</span></span>
- <span data-ttu-id="f2374-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="f2374-165">"\bigg"</span></span>
- <span data-ttu-id="f2374-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="f2374-166">"\Big"</span></span>
- <span data-ttu-id="f2374-167">"|"</span><span class="sxs-lookup"><span data-stu-id="f2374-167">"|"</span></span>
- <span data-ttu-id="f2374-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="f2374-168">"\mathbb"</span></span>
- <span data-ttu-id="f2374-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="f2374-169">"\vec"</span></span>
- <span data-ttu-id="f2374-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="f2374-170">"\in"</span></span>
- <span data-ttu-id="f2374-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="f2374-171">"\texttt"</span></span>
- <span data-ttu-id="f2374-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="f2374-172">"\ne"</span></span>
- <span data-ttu-id="f2374-173">"<"</span><span class="sxs-lookup"><span data-stu-id="f2374-173">"<"</span></span>
- <span data-ttu-id="f2374-174">">"</span><span class="sxs-lookup"><span data-stu-id="f2374-174">">"</span></span>
- <span data-ttu-id="f2374-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="f2374-175">"\leq"</span></span>
- <span data-ttu-id="f2374-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="f2374-176">"\geq"</span></span>
- <span data-ttu-id="f2374-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="f2374-177">"~~"</span></span>
- <span data-ttu-id="f2374-178">"~"</span><span class="sxs-lookup"><span data-stu-id="f2374-178">"~"</span></span>
- <span data-ttu-id="f2374-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="f2374-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="f2374-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="f2374-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="f2374-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="f2374-181">"\_"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="f2374-182">クォンタム回線</span><span class="sxs-lookup"><span data-stu-id="f2374-182">Quantum Circuits</span></span>
<span data-ttu-id="f2374-183">この場合、1分間の変換では、 $ \text { cnot } _ { 01 } (H \otimes 1) と $ なります。</span><span class="sxs-lookup"><span data-stu-id="f2374-183">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="f2374-184">このゲートシーケンスは、下回っありの2つのビット状態を作成するので、クォンタムコンピューティングにとって基本的な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f2374-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="f2374-185">$$\mathrm{Cnot } _ { 01 } (H \otimes 1) \ket { 00 } = \frac { 1 } { \sqrt { 2 } } \left ( \ket { 00 }  +  \ket { 11 } \right )、$$</span><span class="sxs-lookup"><span data-stu-id="f2374-185">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="f2374-186">このような複雑さを持つ操作は、クォンタムアルゴリズムとクォンタムエラー修正で広く普及しています。そのため、 *量子回線図*と呼ばれるシンプルな方法で視覚化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2374-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="f2374-187">この下回っありのクォンタム状態を準備するためのサーキット図は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f2374-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="f2374-188"><!--- ![](.\media\1.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-188"><!--- ![](.\media\1.svg) ---></span></span>
<span data-ttu-id="f2374-189"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-189"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-190">![下回っありの2つの状態のサーキット図](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-190">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="f2374-191">クォンタム回路図の表記規則</span><span class="sxs-lookup"><span data-stu-id="f2374-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="f2374-192">このクォンタム操作のビジュアル言語は、クォンタム回線を表現するための規則を理解した後に、同等のマトリックスを書き出すよりも簡単に消化できます。</span><span class="sxs-lookup"><span data-stu-id="f2374-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="f2374-193">以下の規則を確認します。</span><span class="sxs-lookup"><span data-stu-id="f2374-193">We review these conventions below.</span></span>

<span data-ttu-id="f2374-194">回路図では、各実線は qubit レジスタを表しています。</span><span class="sxs-lookup"><span data-stu-id="f2374-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="f2374-195">慣例として、一番上の行は qubit レジスタ0で、 $ $ 余りには順番にラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="f2374-195">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="f2374-196">上の例の回線は、2つの qubits (または1つの qubits で構成される2つのレジスタ) で動作しているように表されています。</span><span class="sxs-lookup"><span data-stu-id="f2374-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="f2374-197">1つ以上の qubit レジスタに作用するゲートは、ボックスとして示されます。</span><span class="sxs-lookup"><span data-stu-id="f2374-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="f2374-198">たとえば、シンボルは</span><span class="sxs-lookup"><span data-stu-id="f2374-198">For example, the symbol</span></span>

<span data-ttu-id="f2374-199"><!--- ![](.\media\2.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-199"><!--- ![](.\media\2.svg) ---></span></span>
<span data-ttu-id="f2374-200"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-200"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-201">![シングル qubit レジスタで動作する Hadamard 操作のシンボル](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-201">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="f2374-202">は、シングル qubit レジスタに対して動作する [Hadamard](xref:microsoft.quantum.intrinsic.h) 操作です。</span><span class="sxs-lookup"><span data-stu-id="f2374-202">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="f2374-203">クォンタムゲートは、ゲートが最初に qubits に適用されたときの左端のゲートと共に、時系列順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="f2374-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="f2374-204">つまり、回線をクォンタム状態のままにしている場合、ワイヤは図の各ゲートを通じて、左から右にクォンタムの状態を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="f2374-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="f2374-205">つまり、</span><span class="sxs-lookup"><span data-stu-id="f2374-205">That is to say</span></span> 

<span data-ttu-id="f2374-206"><!--- ![](.\media\3.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-206"><!--- ![](.\media\3.svg) ---></span></span>
<span data-ttu-id="f2374-207"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-207"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-208">![左から右に適用されているクォンタムゲートの図](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-208">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="f2374-209">は、ユニタリ行列 $ cba $ です。</span><span class="sxs-lookup"><span data-stu-id="f2374-209">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="f2374-210">行列乗算は反対の規則に従います。最初に右端の行列が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2374-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="f2374-211">ただし、量子回線図では、最初に一番左のゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2374-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="f2374-212">この違いによって混乱が生じる可能性があるため、線形代数の図と量子回線の図の大きな違いに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="f2374-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="f2374-213">クォンタム回線の入力と出力</span><span class="sxs-lookup"><span data-stu-id="f2374-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="f2374-214">前に示したすべての例では、クォンタムゲートから送信されたワイヤの数とまったく同じ数 (qubits) の入力がクォンタムゲートに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="f2374-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="f2374-215">最初は、クォンタム回線が一般に入力よりも多くの出力を持つことができると考えられるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f2374-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="f2374-216">ただし、これは不可能です。これは、すべてのクォンタム操作、測定値の保存は、すべての処理が行われるためです。</span><span class="sxs-lookup"><span data-stu-id="f2374-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="f2374-217">同じ数の出力が入力として含まれていなかった場合は、元に戻すことはできず、そのため、不一致になります。</span><span class="sxs-lookup"><span data-stu-id="f2374-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="f2374-218">このため、サーキット図に描画されるすべてのボックスには、それを終了するときとまったく同じ数のワイヤを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2374-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="f2374-219">マルチ qubit 回路図は、単 qubit と同様の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="f2374-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="f2374-220">明確な例として、2つの qubit のユニタリ演算 $ B $ を $ (H S \otimes X) に定義し、 $ 回路を同等のものとして表現することができます。</span><span class="sxs-lookup"><span data-stu-id="f2374-220">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<span data-ttu-id="f2374-221"><!--- ![](.\media\4.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-221"><!--- ![](.\media\4.svg) ---></span></span>
<span data-ttu-id="f2374-222"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-222"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-223">![2つの qubit のユニタリ操作のサーキットダイアグラム](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-223">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="f2374-224">また、 $ $ 回線が使用されているコンテキストに応じて、2 1-qubit レジスタではなく、単一の2つの qubit レジスタに対するアクションを持つ B を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2374-224">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="f2374-225">このような抽象回路図の中で最も役に立つのは、複雑なクォンタムアルゴリズムを高いレベルで記述し、基本ゲートにコンパイルする必要がない場合などです。</span><span class="sxs-lookup"><span data-stu-id="f2374-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="f2374-226">これは、アルゴリズム内の各サブルーチンがどのように機能するかについてすべての詳細を理解しなくても、大規模なクォンタムアルゴリズムのデータフローに関する直感を取得できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f2374-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="f2374-227">制御ゲート</span><span class="sxs-lookup"><span data-stu-id="f2374-227">Controlled gates</span></span>
<span data-ttu-id="f2374-228">マルチ qubit クォンタム回路図に組み込まれているもう1つのコンストラクトは制御です。</span><span class="sxs-lookup"><span data-stu-id="f2374-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="f2374-229">$ \Lambda $ 1 つの qubit の値が g のアプリケーションを制御する、量子片制御ゲート (g) のアクションは $ 、 $ 次の製品の状態入力 $ \Lambda (g) ( \alpha \ket { 0 }  +  \beta \ket { 1 } ) \ket { \psi } = \alpha \ket { 0 } \ket { \psi }  +  \beta \ket { 1 } G \ket { \psi } $ の例を見ることで理解できます。つまり、制御されたゲートは、 $ $ $ \psi $ コントロール qubit が値1を受け取る場合にのみ、を含むレジスタに G を適用し $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="f2374-229">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$. That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="f2374-230">一般に、このような制御された操作を回路図に記述します。</span><span class="sxs-lookup"><span data-stu-id="f2374-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="f2374-231"><!--- ![](.\media\5.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-231"><!--- ![](.\media\5.svg) ---></span></span>
<span data-ttu-id="f2374-232"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-232"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-233">![単一制御ゲートのサーキットダイアグラム](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-233">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="f2374-234">ここで、黒い円はゲートが制御されるクォンタムビットを表し、垂直方向のワイヤは、コントロール qubit が値1を受け取るときに適用されるユニタリを表し $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="f2374-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="f2374-235">$G = X $ と g Z では、 $ = $ ゲートの制御されたバージョンを記述するために、次の表記法を使用します (制御された x ゲートが[ $ cnot $ ゲート](xref:microsoft.quantum.intrinsic.cnot)であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="f2374-235">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<span data-ttu-id="f2374-236"><!--- ![](.\media\6.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-236"><!--- ![](.\media\6.svg) ---></span></span>
<span data-ttu-id="f2374-237"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-237"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-238">![特別なケースの制御ゲートの回路図](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-238">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="f2374-239">Q# 操作の制御されたバージョンを自動的に生成するメソッドを提供します。これにより、プログラマはこれらの操作を手動でコーディングする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2374-239">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="f2374-240">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f2374-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="f2374-241">測定演算子</span><span class="sxs-lookup"><span data-stu-id="f2374-241">Measurement operator</span></span>
<span data-ttu-id="f2374-242">回路図で視覚化する残りの操作は、測定値です。</span><span class="sxs-lookup"><span data-stu-id="f2374-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="f2374-243">測定は、qubit レジスタを受け取り、それを測定し、その結果を古典的な情報として出力します。</span><span class="sxs-lookup"><span data-stu-id="f2374-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="f2374-244">測定値はメーター記号で示され、常に入力として qubit レジスタ (実線で示されます) を受け取り、古典的な情報を出力します (2 本の線で示されます)。</span><span class="sxs-lookup"><span data-stu-id="f2374-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="f2374-245">具体的には、このようなサブサーキットは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f2374-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="f2374-246"><!--- ![](.\media\7.svg) ----></span><span class="sxs-lookup"><span data-stu-id="f2374-246"><!--- ![](.\media\7.svg) ----></span></span>
<span data-ttu-id="f2374-247"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-247"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-248">![測定演算を表すシンボル](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-248">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="f2374-249">Q# この目的のために [メジャー演算子](xref:microsoft.quantum.intrinsic.measure) を実装します。</span><span class="sxs-lookup"><span data-stu-id="f2374-249">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="f2374-250">詳細については、 [測定に関するセクション](xref:microsoft.quantum.libraries.standard.prelude#measurements) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2374-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="f2374-251">同様に、サブサーキット</span><span class="sxs-lookup"><span data-stu-id="f2374-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="f2374-252"><!--- ![](.\media\8.svg) ---></span><span class="sxs-lookup"><span data-stu-id="f2374-252"><!--- ![](.\media\8.svg) ---></span></span>
<span data-ttu-id="f2374-253"><これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--></span><span class="sxs-lookup"><span data-stu-id="f2374-253"><!-- Can't find a way to easily center this... probably an extension needed:  --></span></span>
<span data-ttu-id="f2374-254">![制御された操作を表す回路図](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-254">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="f2374-255">クラシックデプロイ制御ゲートを提供します $ $ 。 G は、古典的な制御ビットが値1であることを条件として適用され $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="f2374-255">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="f2374-256">受付回路の図</span><span class="sxs-lookup"><span data-stu-id="f2374-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="f2374-257">クォンタムは、これらのコンポーネントを示す最良のクォンタムアルゴリズムであると考えられます。</span><span class="sxs-lookup"><span data-stu-id="f2374-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="f2374-258">対応する [クォンタム kata](xref:microsoft.quantum.overview.katas) クォンタムを使用したハンズオンについては、結び付き使用と測定を使用して、quantum コンピューター内 (または quantum ネットワーク内の離れたコンピューター間) でデータを移動する方法について学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f2374-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="f2374-259">興味深いことに、実際には、qubit の値が何であるかを把握していなくても、特定の qubit の値を1つの qubit から別の値に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="f2374-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="f2374-260">これは、プロトコルが量子力学法に従って動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="f2374-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="f2374-261">次に、クォンタムの例を示します。また、クォンタム回線の読み取り方法を示すために、回路の注釈付きバージョンも提供します。</span><span class="sxs-lookup"><span data-stu-id="f2374-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="f2374-262"><!--- ![](.\media\tp2.svg) { 幅 = 50%} ---></span><span class="sxs-lookup"><span data-stu-id="f2374-262"><!--- ![](.\media\tp2.svg){ width=50% } ---></span></span>
<span data-ttu-id="f2374-263">![Quantum の受付回線](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="f2374-263">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
