---
<span data-ttu-id="eef4e-101">タイトル: クォンタム回線の説明: 量子回線図を使用して、単純で複雑なクォンタム操作を視覚的に表現する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-101">title: Quantum circuits description: Learn how to visually represent simple and complex quantum operations with quantum circuit diagrams.</span></span>
<span data-ttu-id="eef4e-102">author: QuantumWriter uid: benbra: v-ms. date: 12/11/2017 ms. topic: article no loc (場所の記事):</span><span class="sxs-lookup"><span data-stu-id="eef4e-102">author: QuantumWriter uid: microsoft.quantum.concepts.circuits ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="eef4e-103">":::no-loc(Q#):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-103">":::no-loc(Q#):::"</span></span>
- <span data-ttu-id="eef4e-104">":::no-loc($$v):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-104">":::no-loc($$v):::"</span></span>
- <span data-ttu-id="eef4e-105">":::no-loc($$):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-105">":::no-loc($$):::"</span></span>
- <span data-ttu-id="eef4e-106">":::no-loc($$):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-106">":::no-loc($$):::"</span></span>
- <span data-ttu-id="eef4e-107">":::no-loc($):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-107">":::no-loc($):::"</span></span>
- <span data-ttu-id="eef4e-108">":::no-loc($):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-108">":::no-loc($):::"</span></span>
- <span data-ttu-id="eef4e-109">":::no-loc($):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-109">":::no-loc($):::"</span></span>
- <span data-ttu-id="eef4e-110">":::no-loc($$):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-110">":::no-loc($$):::"</span></span>
- <span data-ttu-id="eef4e-111">":::no-loc(\cdots):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-111">":::no-loc(\cdots):::"</span></span>
- <span data-ttu-id="eef4e-112">":::no-loc(bmatrix):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-112">":::no-loc(bmatrix):::"</span></span>
- <span data-ttu-id="eef4e-113">":::no-loc(\ddots):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-113">":::no-loc(\ddots):::"</span></span>
- <span data-ttu-id="eef4e-114">":::no-loc(\equiv):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-114">":::no-loc(\equiv):::"</span></span>
- <span data-ttu-id="eef4e-115">":::no-loc(\sum):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-115">":::no-loc(\sum):::"</span></span>
- <span data-ttu-id="eef4e-116">":::no-loc(\begin):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-116">":::no-loc(\begin):::"</span></span>
- <span data-ttu-id="eef4e-117">":::no-loc(\end):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-117">":::no-loc(\end):::"</span></span>
- <span data-ttu-id="eef4e-118">":::no-loc(\sqrt):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-118">":::no-loc(\sqrt):::"</span></span>
- <span data-ttu-id="eef4e-119">":::no-loc(\otimes):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-119">":::no-loc(\otimes):::"</span></span>
- <span data-ttu-id="eef4e-120">":::no-loc({):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-120">":::no-loc({):::"</span></span>
- <span data-ttu-id="eef4e-121">":::no-loc(}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-121">":::no-loc(}):::"</span></span>
- <span data-ttu-id="eef4e-122">":::no-loc(\text):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-122">":::no-loc(\text):::"</span></span>
- <span data-ttu-id="eef4e-123">":::no-loc(\phi):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-123">":::no-loc(\phi):::"</span></span>
- <span data-ttu-id="eef4e-124">":::no-loc(\kappa):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-124">":::no-loc(\kappa):::"</span></span>
- <span data-ttu-id="eef4e-125">":::no-loc(\psi):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-125">":::no-loc(\psi):::"</span></span>
- <span data-ttu-id="eef4e-126">":::no-loc(\alpha):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-126">":::no-loc(\alpha):::"</span></span>
- <span data-ttu-id="eef4e-127">":::no-loc(\beta):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-127">":::no-loc(\beta):::"</span></span>
- <span data-ttu-id="eef4e-128">":::no-loc(\gamma):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-128">":::no-loc(\gamma):::"</span></span>
- <span data-ttu-id="eef4e-129">":::no-loc(\delta):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-129">":::no-loc(\delta):::"</span></span>
- <span data-ttu-id="eef4e-130">":::no-loc(\omega):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-130">":::no-loc(\omega):::"</span></span>
- <span data-ttu-id="eef4e-131">":::no-loc(\bra):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-131">":::no-loc(\bra):::"</span></span>
- <span data-ttu-id="eef4e-132">":::no-loc(\ket):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-132">":::no-loc(\ket):::"</span></span>
- <span data-ttu-id="eef4e-133">":::no-loc(\boldone):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-133">":::no-loc(\boldone):::"</span></span>
- <span data-ttu-id="eef4e-134">":::no-loc(\\\\):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-134">":::no-loc(\\\\):::"</span></span>
- <span data-ttu-id="eef4e-135">":::no-loc(\\):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-135">":::no-loc(\\):::"</span></span>
- <span data-ttu-id="eef4e-136">":::no-loc(=):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-136">":::no-loc(=):::"</span></span>
- <span data-ttu-id="eef4e-137">":::no-loc(\frac):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-137">":::no-loc(\frac):::"</span></span>
- <span data-ttu-id="eef4e-138">":::no-loc(\text):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-138">":::no-loc(\text):::"</span></span>
- <span data-ttu-id="eef4e-139">":::no-loc(\mapsto):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-139">":::no-loc(\mapsto):::"</span></span>
- <span data-ttu-id="eef4e-140">":::no-loc(\dagger):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-140">":::no-loc(\dagger):::"</span></span>
- <span data-ttu-id="eef4e-141">":::no-loc(\to):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-141">":::no-loc(\to):::"</span></span>
- <span data-ttu-id="eef4e-142">":::no-loc(\begin{cases}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-142">":::no-loc(\begin{cases}):::"</span></span>
- <span data-ttu-id="eef4e-143">":::no-loc(\end{cases}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-143">":::no-loc(\end{cases}):::"</span></span>
- <span data-ttu-id="eef4e-144">":::no-loc(\operatorname):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-144">":::no-loc(\operatorname):::"</span></span>
- <span data-ttu-id="eef4e-145">":::no-loc(\braket):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-145">":::no-loc(\braket):::"</span></span>
- <span data-ttu-id="eef4e-146">":::no-loc(\id):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-146">":::no-loc(\id):::"</span></span>
- <span data-ttu-id="eef4e-147">":::no-loc(\expect):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-147">":::no-loc(\expect):::"</span></span>
- <span data-ttu-id="eef4e-148">":::no-loc(\defeq):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-148">":::no-loc(\defeq):::"</span></span>
- <span data-ttu-id="eef4e-149">":::no-loc(\variance):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-149">":::no-loc(\variance):::"</span></span>
- <span data-ttu-id="eef4e-150">":::no-loc(\dd):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-150">":::no-loc(\dd):::"</span></span>
- <span data-ttu-id="eef4e-151">":::no-loc(&):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-151">":::no-loc(&):::"</span></span>
- <span data-ttu-id="eef4e-152">":::no-loc(\begin{align}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-152">":::no-loc(\begin{align}):::"</span></span>
- <span data-ttu-id="eef4e-153">":::no-loc(\end{align}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-153">":::no-loc(\end{align}):::"</span></span>
- <span data-ttu-id="eef4e-154">":::no-loc(\Lambda):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-154">":::no-loc(\Lambda):::"</span></span>
- <span data-ttu-id="eef4e-155">":::no-loc(\lambda):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-155">":::no-loc(\lambda):::"</span></span>
- <span data-ttu-id="eef4e-156">":::no-loc(\Omega):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-156">":::no-loc(\Omega):::"</span></span>
- <span data-ttu-id="eef4e-157">":::no-loc(\mathrm):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-157">":::no-loc(\mathrm):::"</span></span>
- <span data-ttu-id="eef4e-158">":::no-loc(\left):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-158">":::no-loc(\left):::"</span></span>
- <span data-ttu-id="eef4e-159">":::no-loc(\right):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-159">":::no-loc(\right):::"</span></span>
- <span data-ttu-id="eef4e-160">":::no-loc(\qquad):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-160">":::no-loc(\qquad):::"</span></span>
- <span data-ttu-id="eef4e-161">":::no-loc(\times):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-161">":::no-loc(\times):::"</span></span>
- <span data-ttu-id="eef4e-162">":::no-loc(\big):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-162">":::no-loc(\big):::"</span></span>
- <span data-ttu-id="eef4e-163">":::no-loc(\langle):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-163">":::no-loc(\langle):::"</span></span>
- <span data-ttu-id="eef4e-164">":::no-loc(\rangle):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-164">":::no-loc(\rangle):::"</span></span>
- <span data-ttu-id="eef4e-165">":::no-loc(\bigg):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-165">":::no-loc(\bigg):::"</span></span>
- <span data-ttu-id="eef4e-166">":::no-loc(\Big):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-166">":::no-loc(\Big):::"</span></span>
- <span data-ttu-id="eef4e-167">":::no-loc(|):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-167">":::no-loc(|):::"</span></span>
- <span data-ttu-id="eef4e-168">":::no-loc(\mathbb):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-168">":::no-loc(\mathbb):::"</span></span>
- <span data-ttu-id="eef4e-169">":::no-loc(\vec):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-169">":::no-loc(\vec):::"</span></span>
- <span data-ttu-id="eef4e-170">":::no-loc(\in):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-170">":::no-loc(\in):::"</span></span>
- <span data-ttu-id="eef4e-171">":::no-loc(\texttt):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-171">":::no-loc(\texttt):::"</span></span>
- <span data-ttu-id="eef4e-172">":::no-loc(\ne):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-172">":::no-loc(\ne):::"</span></span>
- <span data-ttu-id="eef4e-173">":::no-loc(<):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-173">":::no-loc(<):::"</span></span>
- <span data-ttu-id="eef4e-174">":::no-loc(>):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-174">":::no-loc(>):::"</span></span>
- <span data-ttu-id="eef4e-175">":::no-loc(\leq):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-175">":::no-loc(\leq):::"</span></span>
- <span data-ttu-id="eef4e-176">":::no-loc(\geq):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-176">":::no-loc(\geq):::"</span></span>
- <span data-ttu-id="eef4e-177">":::no-loc(~~):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-177">":::no-loc(~~):::"</span></span>
- <span data-ttu-id="eef4e-178">":::no-loc(~):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-178">":::no-loc(~):::"</span></span>
- <span data-ttu-id="eef4e-179">":::no-loc(\begin{bmatrix}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-179">":::no-loc(\begin{bmatrix}):::"</span></span>
- <span data-ttu-id="eef4e-180">":::no-loc(\end{bmatrix}):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-180">":::no-loc(\end{bmatrix}):::"</span></span>
- <span data-ttu-id="eef4e-181">":::no-loc(\_):::"</span><span class="sxs-lookup"><span data-stu-id="eef4e-181">":::no-loc(\_):::"</span></span>

---

# <a name="quantum-circuits"></a><span data-ttu-id="eef4e-182">クォンタム回線</span><span class="sxs-lookup"><span data-stu-id="eef4e-182">Quantum Circuits</span></span>
<span data-ttu-id="eef4e-183">この場合、1分間の変換では、 :::no-loc($)::: :::no-loc(\text)::: :::no-loc({)::: cnot :::no-loc(})::: _ :::no-loc({)::: 01 :::no-loc(})::: (H :::no-loc(\otimes)::: 1) と :::no-loc($)::: なります。</span><span class="sxs-lookup"><span data-stu-id="eef4e-183">Consider for a moment the unitary transformation :::no-loc($)::::::no-loc(\text)::::::no-loc({)::: CNOT:::no-loc(}):::_:::no-loc({):::01:::no-loc(}):::(H:::no-loc(\otimes)::: 1):::no-loc($):::.</span></span>
<span data-ttu-id="eef4e-184">このゲートシーケンスは、下回っありの2つのビット状態を作成するので、クォンタムコンピューティングにとって基本的な意味を持ちます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-184">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="eef4e-185">:::no-loc($$)::::::no-loc(\mathrm)::::::no-loc({):::Cnot :::no-loc(})::: _ :::no-loc({)::: 01 :::no-loc(})::: (H :::no-loc(\otimes)::: 1) :::no-loc(\ket)::: :::no-loc({)::: 00 :::no-loc(})::: :::no-loc(=)::: :::no-loc(\frac)::: :::no-loc({)::: 1 :::no-loc(})::: :::no-loc({)::: :::no-loc(\sqrt)::: :::no-loc({)::: 2 :::no-loc(})::: :::no-loc(})::: :::no-loc(\left)::: ( :::no-loc(\ket)::: :::no-loc({)::: 00 :::no-loc(}):::  +  :::no-loc(\ket)::: :::no-loc({)::: 11 :::no-loc(})::: :::no-loc(\right)::: )、:::no-loc($$):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-185">:::no-loc($$)::::::no-loc(\mathrm)::::::no-loc({):::CNOT:::no-loc(}):::_:::no-loc({):::01:::no-loc(}):::(H:::no-loc(\otimes)::: 1):::no-loc(\ket)::::::no-loc({):::00:::no-loc(})::: :::no-loc(=)::: :::no-loc(\frac)::::::no-loc({):::1:::no-loc(})::::::no-loc({)::::::no-loc(\sqrt)::::::no-loc({):::2:::no-loc(})::::::no-loc(})::: :::no-loc(\left):::(:::no-loc(\ket)::::::no-loc({):::00:::no-loc(})::: + :::no-loc(\ket)::::::no-loc({):::11:::no-loc(})::: :::no-loc(\right):::),:::no-loc($$):::</span></span>

<span data-ttu-id="eef4e-186">このような複雑さを持つ操作は、クォンタムアルゴリズムとクォンタムエラー修正で広く普及しています。そのため、 *量子回線図* と呼ばれるシンプルな方法で視覚化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-186">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram* .</span></span>
<span data-ttu-id="eef4e-187">この下回っありのクォンタム状態を準備するためのサーキット図は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="eef4e-187">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<span data-ttu-id="eef4e-188">:::no-loc(<):::!--- ![](.\media\1.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-188">:::no-loc(<):::!--- ![](.\media\1.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-189">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-189">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-190">![下回っありの2つの状態のサーキット図](:::no-loc(~):::/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-190">![Circuit diagram for a maximally entangled two-qubit state](:::no-loc(~):::/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="eef4e-191">クォンタム回路図の表記規則</span><span class="sxs-lookup"><span data-stu-id="eef4e-191">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="eef4e-192">このクォンタム操作のビジュアル言語は、クォンタム回線を表現するための規則を理解した後に、同等のマトリックスを書き出すよりも簡単に消化できます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-192">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="eef4e-193">以下の規則を確認します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-193">We review these conventions below.</span></span>

<span data-ttu-id="eef4e-194">回路図では、各実線は qubit レジスタを表しています。</span><span class="sxs-lookup"><span data-stu-id="eef4e-194">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="eef4e-195">慣例として、一番上の行は qubit レジスタ0で、 :::no-loc($)::: :::no-loc($)::: 余りには順番にラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-195">By convention, the top line is qubit register :::no-loc($):::0:::no-loc($)::: and the remainder are labeled sequentially.</span></span> <span data-ttu-id="eef4e-196">上の例の回線は、2つの qubits (または1つの qubits で構成される2つのレジスタ) で動作しているように表されています。</span><span class="sxs-lookup"><span data-stu-id="eef4e-196">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="eef4e-197">1つ以上の qubit レジスタに作用するゲートは、ボックスとして示されます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-197">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="eef4e-198">たとえば、シンボルは</span><span class="sxs-lookup"><span data-stu-id="eef4e-198">For example, the symbol</span></span>

<span data-ttu-id="eef4e-199">:::no-loc(<):::!--- ![](.\media\2.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-199">:::no-loc(<):::!--- ![](.\media\2.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-200">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-200">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-201">![シングル qubit レジスタで動作する Hadamard 操作のシンボル](:::no-loc(~):::/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-201">![Symbol for a Hadamard operation acting on a single-qubit register](:::no-loc(~):::/media/2.svg)</span></span>

<span data-ttu-id="eef4e-202">は、シングル qubit レジスタに対して動作する [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) 操作です。</span><span class="sxs-lookup"><span data-stu-id="eef4e-202">is a [Hadamard](xref:Microsoft.Quantum.Intrinsic.H) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="eef4e-203">クォンタムゲートは、ゲートが最初に qubits に適用されたときの左端のゲートと共に、時系列順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-203">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="eef4e-204">つまり、回線をクォンタム状態のままにしている場合、ワイヤは図の各ゲートを通じて、左から右にクォンタムの状態を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-204">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="eef4e-205">つまり、</span><span class="sxs-lookup"><span data-stu-id="eef4e-205">That is to say</span></span> 

<span data-ttu-id="eef4e-206">:::no-loc(<):::!--- ![](.\media\3.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-206">:::no-loc(<):::!--- ![](.\media\3.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-207">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-207">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-208">![左から右に適用されているクォンタムゲートの図](:::no-loc(~):::/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-208">![Diagram of quantum gates being applied left-to-right](:::no-loc(~):::/media/3.svg)</span></span>

<span data-ttu-id="eef4e-209">は、ユニタリ行列 :::no-loc($)::: cba :::no-loc($)::: です。</span><span class="sxs-lookup"><span data-stu-id="eef4e-209">is the unitary matrix :::no-loc($):::CBA:::no-loc($):::.</span></span>
<span data-ttu-id="eef4e-210">行列乗算は反対の規則に従います。最初に右端の行列が適用されます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-210">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="eef4e-211">ただし、量子回線図では、最初に一番左のゲートが適用されます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-211">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="eef4e-212">この違いによって混乱が生じる可能性があるため、線形代数の図と量子回線の図の大きな違いに注意することが重要です。</span><span class="sxs-lookup"><span data-stu-id="eef4e-212">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="eef4e-213">クォンタム回線の入力と出力</span><span class="sxs-lookup"><span data-stu-id="eef4e-213">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="eef4e-214">前に示したすべての例では、クォンタムゲートから送信されたワイヤの数とまったく同じ数 (qubits) の入力がクォンタムゲートに含まれていました。</span><span class="sxs-lookup"><span data-stu-id="eef4e-214">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="eef4e-215">最初は、クォンタム回線が一般に入力よりも多くの出力を持つことができると考えられるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="eef4e-215">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="eef4e-216">ただし、これは不可能です。これは、すべてのクォンタム操作、測定値の保存は、すべての処理が行われるためです。</span><span class="sxs-lookup"><span data-stu-id="eef4e-216">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="eef4e-217">同じ数の出力が入力として含まれていなかった場合は、元に戻すことはできず、そのため、不一致になります。</span><span class="sxs-lookup"><span data-stu-id="eef4e-217">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="eef4e-218">このため、サーキット図に描画されるすべてのボックスには、それを終了するときとまったく同じ数のワイヤを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eef4e-218">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="eef4e-219">マルチ qubit 回路図は、単 qubit と同様の規則に従います。</span><span class="sxs-lookup"><span data-stu-id="eef4e-219">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="eef4e-220">明確な例として、2つの qubit のユニタリ演算 :::no-loc($)::: B :::no-loc($)::: を :::no-loc($)::: (H S :::no-loc(\otimes)::: X) に定義し、 :::no-loc($)::: 回路を同等のものとして表現することができます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-220">As a clarifying example, we can define a two-qubit unitary operation :::no-loc($):::B:::no-loc($)::: to be :::no-loc($):::(H S:::no-loc(\otimes)::: X):::no-loc($)::: and express the circuit equivalently as</span></span>

<span data-ttu-id="eef4e-221">:::no-loc(<):::!--- ![](.\media\4.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-221">:::no-loc(<):::!--- ![](.\media\4.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-222">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-222">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-223">![2つの qubit のユニタリ操作のサーキットダイアグラム](:::no-loc(~):::/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-223">![Circuit diagram of a two-qubit unitary operation](:::no-loc(~):::/media/4.svg)</span></span>

<span data-ttu-id="eef4e-224">また、 :::no-loc($)::: :::no-loc($)::: 回線が使用されているコンテキストに応じて、2 1-qubit レジスタではなく、単一の2つの qubit レジスタに対するアクションを持つ B を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-224">We can also view :::no-loc($):::B:::no-loc($)::: as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="eef4e-225">このような抽象回路図の中で最も役に立つのは、複雑なクォンタムアルゴリズムを高いレベルで記述し、基本ゲートにコンパイルする必要がない場合などです。</span><span class="sxs-lookup"><span data-stu-id="eef4e-225">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="eef4e-226">これは、アルゴリズム内の各サブルーチンがどのように機能するかについてすべての詳細を理解しなくても、大規模なクォンタムアルゴリズムのデータフローに関する直感を取得できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-226">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="eef4e-227">制御ゲート</span><span class="sxs-lookup"><span data-stu-id="eef4e-227">Controlled gates</span></span>
<span data-ttu-id="eef4e-228">マルチ qubit クォンタム回路図に組み込まれているもう1つのコンストラクトは制御です。</span><span class="sxs-lookup"><span data-stu-id="eef4e-228">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="eef4e-229">:::no-loc($)::: :::no-loc(\Lambda)::: :::no-loc($)::: 1 つの qubit の値が g のアプリケーションを制御する、量子片制御ゲート (g) のアクションは :::no-loc($)::: 、 :::no-loc($)::: 次の製品の状態入力 :::no-loc($)::: :::no-loc(\Lambda)::: (g) ( :::no-loc(\alpha)::: :::no-loc(\ket)::: :::no-loc({)::: 0 :::no-loc(}):::  +  :::no-loc(\beta)::: :::no-loc(\ket)::: :::no-loc({)::: 1 :::no-loc(})::: ) :::no-loc(\ket)::: :::no-loc({)::: :::no-loc(\psi)::: :::no-loc(})::: :::no-loc(=)::: :::no-loc(\alpha)::: :::no-loc(\ket)::: :::no-loc({)::: 0 :::no-loc(})::: :::no-loc(\ket)::: :::no-loc({)::: :::no-loc(\psi)::: :::no-loc(}):::  +  :::no-loc(\beta)::: :::no-loc(\ket)::: :::no-loc({)::: 1 :::no-loc(})::: G :::no-loc(\ket)::: :::no-loc({)::: :::no-loc(\psi)::: :::no-loc(})::: :::no-loc($)::: の例を見ることで理解できます。つまり、制御されたゲートは、 :::no-loc($)::: :::no-loc($)::: :::no-loc($)::: :::no-loc(\psi)::: :::no-loc($)::: コントロール qubit が値1を受け取る場合にのみ、を含むレジスタに G を適用し :::no-loc($)::: :::no-loc($)::: ます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-229">The action of a quantum singly controlled gate, denoted :::no-loc($)::::::no-loc(\Lambda):::(G):::no-loc($):::, where a single qubit's value controls the application of :::no-loc($):::G:::no-loc($):::, can be understood by looking at the following example of a product state input :::no-loc($)::::::no-loc(\Lambda):::(G) (:::no-loc(\alpha)::: :::no-loc(\ket)::::::no-loc({):::0:::no-loc(})::: + :::no-loc(\beta)::: :::no-loc(\ket)::::::no-loc({):::1:::no-loc(}):::) :::no-loc(\ket)::::::no-loc({)::::::no-loc(\psi)::::::no-loc(})::: :::no-loc(=)::: :::no-loc(\alpha)::: :::no-loc(\ket)::::::no-loc({):::0:::no-loc(})::: :::no-loc(\ket)::::::no-loc({)::::::no-loc(\psi)::::::no-loc(})::: + :::no-loc(\beta)::: :::no-loc(\ket)::::::no-loc({):::1:::no-loc(})::: G:::no-loc(\ket)::::::no-loc({)::::::no-loc(\psi)::::::no-loc(})::::::no-loc($):::. That is to say, the controlled gate applies :::no-loc($):::G:::no-loc($)::: to the register containing :::no-loc($)::::::no-loc(\psi)::::::no-loc($)::: if and only if the control qubit takes the value :::no-loc($):::1:::no-loc($):::.</span></span>
<span data-ttu-id="eef4e-230">一般に、このような制御された操作を回路図に記述します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-230">In general, we describe such controlled operations in circuit diagrams as</span></span>

<span data-ttu-id="eef4e-231">:::no-loc(<):::!--- ![](.\media\5.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-231">:::no-loc(<):::!--- ![](.\media\5.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-232">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-232">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-233">![単一制御ゲートのサーキットダイアグラム](:::no-loc(~):::/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-233">![Circuit diagram of a singly controlled gate](:::no-loc(~):::/media/5.svg)</span></span>

<span data-ttu-id="eef4e-234">ここで、黒い円はゲートが制御されるクォンタムビットを表し、垂直方向のワイヤは、コントロール qubit が値1を受け取るときに適用されるユニタリを表し :::no-loc($)::: :::no-loc($)::: ます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-234">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value :::no-loc($):::1:::no-loc($):::.</span></span>
<span data-ttu-id="eef4e-235">:::no-loc($):::G :::no-loc(=)::: X :::no-loc($)::: と g Z では、 :::no-loc($)::: :::no-loc(=)::: :::no-loc($)::: ゲートの制御されたバージョンを記述するために、次の表記法を使用します (制御された x ゲートが[ :::no-loc($)::: cnot :::no-loc($)::: ゲート](xref:Microsoft.Quantum.Intrinsic.CNOT)であることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="eef4e-235">For the special cases where :::no-loc($):::G:::no-loc(=):::X:::no-loc($)::: and :::no-loc($):::G:::no-loc(=):::Z:::no-loc($)::: we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [:::no-loc($):::CNOT:::no-loc($)::: gate](xref:Microsoft.Quantum.Intrinsic.CNOT)):</span></span>

<span data-ttu-id="eef4e-236">:::no-loc(<):::!--- ![](.\media\6.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-236">:::no-loc(<):::!--- ![](.\media\6.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-237">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-237">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-238">![特別なケースの制御ゲートの回路図](:::no-loc(~):::/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-238">![Circuit diagram for special cases of controlled gates](:::no-loc(~):::/media/6.svg)</span></span>

<span data-ttu-id="eef4e-239">:::no-loc(Q#)::: 操作の制御されたバージョンを自動的に生成するメソッドを提供します。これにより、プログラマはこれらの操作を手動でコーディングする必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="eef4e-239">:::no-loc(Q#)::: provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="eef4e-240">この例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-240">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl :::no-loc({)::: // Auto-generate the controlled specialization of the operation
    H(qubit);
:::no-loc(}):::
```

## <a name="measurement-operator"></a><span data-ttu-id="eef4e-241">測定演算子</span><span class="sxs-lookup"><span data-stu-id="eef4e-241">Measurement operator</span></span>
<span data-ttu-id="eef4e-242">回路図で視覚化する残りの操作は、測定値です。</span><span class="sxs-lookup"><span data-stu-id="eef4e-242">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="eef4e-243">測定は、qubit レジスタを受け取り、それを測定し、その結果を古典的な情報として出力します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-243">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="eef4e-244">測定値はメーター記号で示され、常に入力として qubit レジスタ (実線で示されます) を受け取り、古典的な情報を出力します (2 本の線で示されます)。</span><span class="sxs-lookup"><span data-stu-id="eef4e-244">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="eef4e-245">具体的には、このようなサブサーキットは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eef4e-245">Specifically, such a subcircuit looks like:</span></span>

<span data-ttu-id="eef4e-246">:::no-loc(<):::!--- ![](.\media\7.svg) ----:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-246">:::no-loc(<):::!--- ![](.\media\7.svg) ----:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-247">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-247">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-248">![測定演算を表すシンボル](:::no-loc(~):::/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-248">![Symbol representing a measurement operation](:::no-loc(~):::/media/7.svg)</span></span>

<span data-ttu-id="eef4e-249">:::no-loc(Q#)::: この目的のために [メジャー演算子](xref:Microsoft.Quantum.Intrinsic.Measure) を実装します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-249">:::no-loc(Q#)::: implements a [Measure operator](xref:Microsoft.Quantum.Intrinsic.Measure) for this purpose.</span></span>
<span data-ttu-id="eef4e-250">詳細については、 [測定に関するセクション](xref:microsoft.quantum.libraries.standard.prelude#measurements) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eef4e-250">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="eef4e-251">同様に、サブサーキット</span><span class="sxs-lookup"><span data-stu-id="eef4e-251">Similarly, the subcircuit</span></span>

<span data-ttu-id="eef4e-252">:::no-loc(<):::!--- ![](.\media\8.svg) ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-252">:::no-loc(<):::!--- ![](.\media\8.svg) ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-253">:::no-loc(<):::これを簡単に中央揃えする方法が見つからない!--拡張機能が必要な場合があります。--:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-253">:::no-loc(<):::!-- Can't find a way to easily center this... probably an extension needed:  --:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-254">![制御された操作を表す回路図](:::no-loc(~):::/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-254">![Circuit diagram representing a controlled operation](:::no-loc(~):::/media/8.svg)</span></span>

<span data-ttu-id="eef4e-255">クラシックデプロイ制御ゲートを提供します :::no-loc($)::: :::no-loc($)::: 。 G は、古典的な制御ビットが値1であることを条件として適用され :::no-loc($)::: :::no-loc($)::: ます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-255">gives a classically controlled gate, where :::no-loc($):::G:::no-loc($)::: is applied conditioned on the classical control bit being value :::no-loc($):::1:::no-loc($):::.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="eef4e-256">受付回路の図</span><span class="sxs-lookup"><span data-stu-id="eef4e-256">Teleportation circuit diagram</span></span>
<span data-ttu-id="eef4e-257">クォンタムは、これらのコンポーネントを示す最良のクォンタムアルゴリズムであると考えられます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-257">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="eef4e-258">対応する [クォンタム kata](xref:microsoft.quantum.overview.katas) クォンタムを使用したハンズオンについては、結び付き使用と測定を使用して、quantum コンピューター内 (または quantum ネットワーク内の離れたコンピューター間) でデータを移動する方法について学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-258">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="eef4e-259">興味深いことに、実際には、qubit の値が何であるかを把握していなくても、特定の qubit の値を1つの qubit から別の値に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="eef4e-259">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="eef4e-260">これは、プロトコルが量子力学法に従って動作するために必要です。</span><span class="sxs-lookup"><span data-stu-id="eef4e-260">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="eef4e-261">次に、クォンタムの例を示します。また、クォンタム回線の読み取り方法を示すために、回路の注釈付きバージョンも提供します。</span><span class="sxs-lookup"><span data-stu-id="eef4e-261">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<span data-ttu-id="eef4e-262">:::no-loc(<):::!--- ![](.\media\tp2.svg) :::no-loc({)::: 幅 :::no-loc(=)::: 50%:::no-loc(})::: ---:::no-loc(>):::</span><span class="sxs-lookup"><span data-stu-id="eef4e-262">:::no-loc(<):::!--- ![](.\media\tp2.svg):::no-loc({)::: width:::no-loc(=):::50% :::no-loc(})::: ---:::no-loc(>):::</span></span>
<span data-ttu-id="eef4e-263">![Quantum の受付回線](:::no-loc(~):::/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="eef4e-263">![Quantum teleportation circuit](:::no-loc(~):::/media/tp2.svg)</span></span>
