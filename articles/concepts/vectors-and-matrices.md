---
<span data-ttu-id="6b43a-101">title: 量子コンピューティングのベクトルとマトリックスの説明: ベクターとマトリックスを操作する方法の基本について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b43a-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="6b43a-102">author: QuantumWriter uid: microsoft.... author: nawiebe@microsoft.com ms. date: 12/11/2017 ms. topic: article no loc:</span><span class="sxs-lookup"><span data-stu-id="6b43a-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="6b43a-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="6b43a-103">"$$"</span></span>
- <span data-ttu-id="6b43a-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="6b43a-104">"$$"</span></span>
- <span data-ttu-id="6b43a-105">"$"</span><span class="sxs-lookup"><span data-stu-id="6b43a-105">"$"</span></span>
- <span data-ttu-id="6b43a-106">"$"</span><span class="sxs-lookup"><span data-stu-id="6b43a-106">"$"</span></span>
- <span data-ttu-id="6b43a-107">"$"</span><span class="sxs-lookup"><span data-stu-id="6b43a-107">"$"</span></span>
- <span data-ttu-id="6b43a-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="6b43a-108">"$$"</span></span>
- <span data-ttu-id="6b43a-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="6b43a-109">"\cdots"</span></span>
- <span data-ttu-id="6b43a-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="6b43a-110">"bmatrix"</span></span>
- <span data-ttu-id="6b43a-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="6b43a-111">"\ddots"</span></span>
- <span data-ttu-id="6b43a-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="6b43a-112">"\equiv"</span></span>
- <span data-ttu-id="6b43a-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="6b43a-113">"\sum"</span></span>
- <span data-ttu-id="6b43a-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="6b43a-114">"\begin"</span></span>
- <span data-ttu-id="6b43a-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="6b43a-115">"\end"</span></span>
- <span data-ttu-id="6b43a-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="6b43a-116">"\sqrt"</span></span>
- <span data-ttu-id="6b43a-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="6b43a-117">"\otimes"</span></span>
- <span data-ttu-id="6b43a-118">"{"</span><span class="sxs-lookup"><span data-stu-id="6b43a-118">"{"</span></span>
- <span data-ttu-id="6b43a-119">"}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-119">"}"</span></span>
- <span data-ttu-id="6b43a-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="6b43a-120">"\text"</span></span>
- <span data-ttu-id="6b43a-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="6b43a-121">"\phi"</span></span>
- <span data-ttu-id="6b43a-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="6b43a-122">"\kappa"</span></span>
- <span data-ttu-id="6b43a-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="6b43a-123">"\psi"</span></span>
- <span data-ttu-id="6b43a-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="6b43a-124">"\alpha"</span></span>
- <span data-ttu-id="6b43a-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="6b43a-125">"\beta"</span></span>
- <span data-ttu-id="6b43a-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="6b43a-126">"\gamma"</span></span>
- <span data-ttu-id="6b43a-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="6b43a-127">"\delta"</span></span>
- <span data-ttu-id="6b43a-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="6b43a-128">"\omega"</span></span>
- <span data-ttu-id="6b43a-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="6b43a-129">"\bra"</span></span>
- <span data-ttu-id="6b43a-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="6b43a-130">"\ket"</span></span>
- <span data-ttu-id="6b43a-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="6b43a-131">"\boldone"</span></span>
- <span data-ttu-id="6b43a-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="6b43a-132">"\\\\"</span></span>
- <span data-ttu-id="6b43a-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="6b43a-133">"\\"</span></span>
- <span data-ttu-id="6b43a-134">"="</span><span class="sxs-lookup"><span data-stu-id="6b43a-134">"="</span></span>
- <span data-ttu-id="6b43a-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="6b43a-135">"\frac"</span></span>
- <span data-ttu-id="6b43a-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="6b43a-136">"\text"</span></span>
- <span data-ttu-id="6b43a-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="6b43a-137">"\mapsto"</span></span>
- <span data-ttu-id="6b43a-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="6b43a-138">"\dagger"</span></span>
- <span data-ttu-id="6b43a-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="6b43a-139">"\to"</span></span>
- <span data-ttu-id="6b43a-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-140">"\begin{cases}"</span></span>
- <span data-ttu-id="6b43a-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-141">"\end{cases}"</span></span>
- <span data-ttu-id="6b43a-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="6b43a-142">"\operatorname"</span></span>
- <span data-ttu-id="6b43a-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="6b43a-143">"\braket"</span></span>
- <span data-ttu-id="6b43a-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="6b43a-144">"\id"</span></span>
- <span data-ttu-id="6b43a-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="6b43a-145">"\expect"</span></span>
- <span data-ttu-id="6b43a-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="6b43a-146">"\defeq"</span></span>
- <span data-ttu-id="6b43a-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="6b43a-147">"\variance"</span></span>
- <span data-ttu-id="6b43a-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="6b43a-148">"\dd"</span></span>
- <span data-ttu-id="6b43a-149">"&"</span><span class="sxs-lookup"><span data-stu-id="6b43a-149">"&"</span></span>
- <span data-ttu-id="6b43a-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-150">"\begin{align}"</span></span>
- <span data-ttu-id="6b43a-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-151">"\end{align}"</span></span>
- <span data-ttu-id="6b43a-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="6b43a-152">"\Lambda"</span></span>
- <span data-ttu-id="6b43a-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="6b43a-153">"\lambda"</span></span>
- <span data-ttu-id="6b43a-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="6b43a-154">"\Omega"</span></span>
- <span data-ttu-id="6b43a-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="6b43a-155">"\mathrm"</span></span>
- <span data-ttu-id="6b43a-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="6b43a-156">"\left"</span></span>
- <span data-ttu-id="6b43a-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="6b43a-157">"\right"</span></span>
- <span data-ttu-id="6b43a-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="6b43a-158">"\qquad"</span></span>
- <span data-ttu-id="6b43a-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="6b43a-159">"\times"</span></span>
- <span data-ttu-id="6b43a-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="6b43a-160">"\big"</span></span>
- <span data-ttu-id="6b43a-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="6b43a-161">"\langle"</span></span>
- <span data-ttu-id="6b43a-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="6b43a-162">"\rangle"</span></span>
- <span data-ttu-id="6b43a-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="6b43a-163">"\bigg"</span></span>
- <span data-ttu-id="6b43a-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="6b43a-164">"\Big"</span></span>
- <span data-ttu-id="6b43a-165">"|"</span><span class="sxs-lookup"><span data-stu-id="6b43a-165">"|"</span></span>
- <span data-ttu-id="6b43a-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="6b43a-166">"\mathbb"</span></span>
- <span data-ttu-id="6b43a-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="6b43a-167">"\vec"</span></span>
- <span data-ttu-id="6b43a-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="6b43a-168">"\in"</span></span>
- <span data-ttu-id="6b43a-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="6b43a-169">"\texttt"</span></span>
- <span data-ttu-id="6b43a-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="6b43a-170">"\ne"</span></span>
- <span data-ttu-id="6b43a-171">"<"</span><span class="sxs-lookup"><span data-stu-id="6b43a-171">"<"</span></span>
- <span data-ttu-id="6b43a-172">">"</span><span class="sxs-lookup"><span data-stu-id="6b43a-172">">"</span></span>
- <span data-ttu-id="6b43a-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="6b43a-173">"\leq"</span></span>
- <span data-ttu-id="6b43a-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="6b43a-174">"\geq"</span></span>
- <span data-ttu-id="6b43a-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="6b43a-175">"~~"</span></span>
- <span data-ttu-id="6b43a-176">"~"</span><span class="sxs-lookup"><span data-stu-id="6b43a-176">"~"</span></span>
- <span data-ttu-id="6b43a-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="6b43a-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6b43a-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="6b43a-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="6b43a-179">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="6b43a-180">ベクターと行列</span><span class="sxs-lookup"><span data-stu-id="6b43a-180">Vectors and Matrices</span></span>

<span data-ttu-id="6b43a-181">ベクターとマトリックスについては、クォンタムコンピューティングを理解するために重要な知識があります。</span><span class="sxs-lookup"><span data-stu-id="6b43a-181">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="6b43a-182">次の簡単な概要を説明します。また、読者には、 *Strang、G. (1993) などの線形代数の標準参照を読むことをお勧めします。線形代数 (Vol. 3) の概要。Wellesley、MA: Wellesley を押す*か、[線形代数](http://joshua.smcvt.edu/linearalgebra/)などのオンライン参照をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b43a-182">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="6b43a-183">次元 (またはサイズ) n の列ベクター (または単なる[*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ は、 $ $ $ 列として配置された n 個の $ 複素数 $ (v_1、v_2、\ lドット、v_n) のコレクションです $ 。</span><span class="sxs-lookup"><span data-stu-id="6b43a-183">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

$$<span data-ttu-id="6b43a-184">画像=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-184">v =\begin{bmatrix}</span></span>
<span data-ttu-id="6b43a-185">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-185">v_1\\\\</span></span>
<span data-ttu-id="6b43a-186">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-186">v_2\\\\</span></span>
<span data-ttu-id="6b43a-187">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-187">\vdots\\\\</span></span>
<span data-ttu-id="6b43a-188">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="6b43a-188">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="6b43a-189">Vector v の標準 $ $ は $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ として定義されています。</span><span class="sxs-lookup"><span data-stu-id="6b43a-189">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="6b43a-190">ベクターは、基準が1である場合は単位基準 (または[*単位ベクトル*](https://en.wikipedia.org/wiki/Unit_vector)と呼ばれます) と呼ばれ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-190">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="6b43a-191">[*ベクター v の adjoint*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ は、 $ $ v ^ \dagger $ として定義されています。は、 $ \* $ 複雑な共役を示す次の行ベクトルとして定義されています。</span><span class="sxs-lookup"><span data-stu-id="6b43a-191">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

$$<span data-ttu-id="6b43a-192">\begin{bmatrix}v_1 \\\\ \ vドット \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="6b43a-192">\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="6b43a-193">2つのベクトルを乗算する最も一般的な方法は、[*内部製品*](https://en.wikipedia.org/wiki/Inner_product_space)(ドット積とも呼ばれます) を使用することです。</span><span class="sxs-lookup"><span data-stu-id="6b43a-193">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="6b43a-194">内側の製品は、あるベクターの射影を別のベクターに提供し、1つのベクターを他のより単純なベクターの合計として表現する方法を説明するうえで非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="6b43a-194">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="6b43a-195">U と v の間の内部積 $ $ $ $ ( $ \left \langle u, v) \right \rangle $ は、として定義されます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-195">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
\langle<span data-ttu-id="6b43a-196">u、v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n</span><span class="sxs-lookup"><span data-stu-id="6b43a-196"> u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="6b43a-197">この表記法では、ベクター v の標準を $ $ v として記述することもでき $ \sqrt { \langle \rangle } $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-197">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="6b43a-198">ベクターと数値 c を乗算し $ $ て、エントリに c を乗算した新しいベクターを作成することができ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-198">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="6b43a-199">また、2つのベクター $ u $ と v を追加して、 $ $ エントリが u と v のエントリの合計である新しいベクターを作成することもでき $ $ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-199">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="6b43a-200">これらの操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b43a-200">These operations are depicted below:</span></span>

$$<span data-ttu-id="6b43a-201">\mathrm{If } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-201">\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="6b43a-202">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-202">u_1\\\\</span></span>
<span data-ttu-id="6b43a-203">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-203">u_2\\\\</span></span>
<span data-ttu-id="6b43a-204">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-204">\vdots\\\\</span></span>
<span data-ttu-id="6b43a-205">u_n \end{bmatrix} ~ \mathrm { と}~</span><span class="sxs-lookup"><span data-stu-id="6b43a-205">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="6b43a-206">画像=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-206">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="6b43a-207">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-207">v_1\\\\</span></span>
    <span data-ttu-id="6b43a-208">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-208">v_2\\\\</span></span>
    <span data-ttu-id="6b43a-209">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-209">\vdots\\\\</span></span>
    <span data-ttu-id="6b43a-210">v_n \end{bmatrix} 、 ~ \mathrm {}~</span><span class="sxs-lookup"><span data-stu-id="6b43a-210">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="6b43a-211">au + bv=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-211">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="6b43a-212">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-212">au_1+bv_1\\\\</span></span>
<span data-ttu-id="6b43a-213">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-213">au_2+bv_2\\\\</span></span>
<span data-ttu-id="6b43a-214">\ vドット\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-214">\vdots\\\\</span></span>
<span data-ttu-id="6b43a-215">au_n + bv_n \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="6b43a-215">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="6b43a-216">サイズ m n の[*マトリックス*](https://en.wikipedia.org/wiki/Matrix_(mathematics))は、 $ \times $ $ $ $ $ $ $ 次に示すように、m 行と n 列に配置された、全数の複素数のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="6b43a-216">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

$$<span data-ttu-id="6b43a-217">M=</span><span class="sxs-lookup"><span data-stu-id="6b43a-217">M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="6b43a-218">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-218">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="6b43a-219">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-219">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="6b43a-220">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { があります}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-220">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
\end{bmatrix}<span data-ttu-id="6b43a-221">.$$</span><span class="sxs-lookup"><span data-stu-id="6b43a-221">.$$</span></span>

<span data-ttu-id="6b43a-222">ディメンション n のベクトルは、 $ $ サイズ n 1 のマトリックスであることに注意して $ \times $ ください。</span><span class="sxs-lookup"><span data-stu-id="6b43a-222">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="6b43a-223">ベクターの場合と同様に、マトリックスと数値 c を乗算して、すべてのエントリに c を乗算した $ $ 新しい行列を取得できます $ $ 。また、同じサイズの2つのマトリックスを追加して、2つの行列の各エントリの合計であるエントリを持つ新しいマトリックスを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-223">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="6b43a-224">マトリックス乗算とその他の製品</span><span class="sxs-lookup"><span data-stu-id="6b43a-224">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="6b43a-225">また、次元 m n の2つ $ の行列 m $ $ \times $ と $ $ 次元 n p の n を乗算し $ \times $ て、 $ 次のように dimension m p の新しいマトリックス p を取得する $ $ \times $ こともできます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-225">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="6b43a-226">M_ { 11 } ~~ M_ { 12 } ~~ \cdots ~~ M_ { 1n}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-226">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="6b43a-227">M_ { 21 } ~~ M_ { 22 } ~~ \cdots ~~ M_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-227">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="6b43a-228">M_ { m1 } ~~ M_ { m2 } ~~ \cdots ~~ M_ { があります}</span><span class="sxs-lookup"><span data-stu-id="6b43a-228">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="6b43a-229">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-229">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="6b43a-230">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-230">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="6b43a-231">N_ { n1 } ~~ N_ { n2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="6b43a-231">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="6b43a-232">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-232">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="6b43a-233">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-233">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="6b43a-234">P_ { m1 } ~~ P_ { m2 } ~~ \cdots ~~ P_ { mp}</span><span class="sxs-lookup"><span data-stu-id="6b43a-234">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="6b43a-235">P のエントリは $ $ $ P_ { ik } = \sum _j M_ { ij } N_ { jk } $ です。</span><span class="sxs-lookup"><span data-stu-id="6b43a-235">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="6b43a-236">たとえば、P_ 11 のエントリは、 $ { } $ $ $ N の最初の列を含む M の最初の行の内部積です $ $ 。ベクターは単にマトリックスの特殊なケースであるため、この定義はマトリックスベクトル乗算まで拡張されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b43a-236">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="6b43a-237">考慮するすべてのマトリックスは、行と列の数が等しいか、またはベクター (1 つの列にのみ対応する) である、正方形のマトリックス $ $ です。</span><span class="sxs-lookup"><span data-stu-id="6b43a-237">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="6b43a-238">1つの特殊な正方形[*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix)の行列は、次のように、 $ \boldone $ すべての対角線の要素が1に等しく、 $ $ 残りの要素が0に等しい $ $ id 行列です。</span><span class="sxs-lookup"><span data-stu-id="6b43a-238">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="6b43a-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-239">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="6b43a-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-240">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
~~<span data-ttu-id="6b43a-241"> \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-241"> \ddots\\\\</span></span>
<span data-ttu-id="6b43a-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} 。$$</span><span class="sxs-lookup"><span data-stu-id="6b43a-242">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="6b43a-243">B 行列 a の $ $ 場合は、"a" という行列 $ があるとし $ [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) $ = = \boldone $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-243">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="6b43a-244">マトリックスの逆のは存在しない必要がありますが、存在する場合は一意であり、これは $ ^-1 を意味し { } $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-244">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="6b43a-245">任意のマトリックス $ m の場合 $ 、m の adjoint または共役転置は $ $ マトリックス $ N であり、 $ $ N_ { ij } = M_ { ji に } ^ \* $ なります。</span><span class="sxs-lookup"><span data-stu-id="6b43a-245">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="6b43a-246">M の adjoint $ $ は、通常 m ^ と示されてい $ \dagger $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-246">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="6b43a-247">マトリックス $ u $ は[*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) $ 、UU ^ u \dagger = ^ \dagger u = \boldone $ または同等の $ u ^ { -1 } = u ^ \dagger $ と同等のものです。</span><span class="sxs-lookup"><span data-stu-id="6b43a-247">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="6b43a-248">たとえば、最も重要なのは、ベクトルの基準を維持することです。</span><span class="sxs-lookup"><span data-stu-id="6b43a-248">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="6b43a-249">これは、</span><span class="sxs-lookup"><span data-stu-id="6b43a-249">This happens because</span></span> 

$$<span data-ttu-id="6b43a-250">\langlev、v2.0、v、 \rangle = \dagger = ^ \dagger u ^ { -1 } U v = ^ \dagger u ^ \dagger u v u v = \langle 、u v \rangle$$</span><span class="sxs-lookup"><span data-stu-id="6b43a-250">\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="6b43a-251">マトリックス $ m $ は、m m ^ の場合は[*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix)と言い $ = \dagger $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-251">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="6b43a-252">最後に、サイズが m n の2つのマトリックス m の Kronecker[*製品 (また*](https://en.wikipedia.org/wiki/Tensor_product)は nq $ $ $ \times $ $ $ $ p q) は \times 、 $ $ サイズ mp の大きなマトリックス p m n で、次のように = \otimes $ $ \times $ M と n から取得され $ $ $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-252">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="6b43a-253">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="6b43a-253">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="6b43a-254">M_ { 11 } ~~ \cdots ~~ M_ { 1n }\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-254">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="6b43a-255">M_ { m1 } ~~ \cdots ~~ M_ { 中  }</span><span class="sxs-lookup"><span data-stu-id="6b43a-255">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="6b43a-256">N_ { 11 } ~~ \cdots ~~ N_ { 1q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-256">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="6b43a-257">N_ { p1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="6b43a-257">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="6b43a-258">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="6b43a-258">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="6b43a-259">M_ { 1n } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1n } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-259">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="6b43a-260">M_ { m1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="6b43a-260">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="6b43a-261">M_ { } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1q } \\\\ \ddots \\\\ N_ { p1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-261">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    \end{bmatrix}<span data-ttu-id="6b43a-262">.</span><span class="sxs-lookup"><span data-stu-id="6b43a-262">.</span></span>
\end{align}

<span data-ttu-id="6b43a-263">次に例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="6b43a-263">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="6b43a-264">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="6b43a-264">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="6b43a-265">a \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-265">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        \\\\<span data-ttu-id="6b43a-266">[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-266">[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    =<span data-ttu-id="6b43a-267">\begin{bmatrix}c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-267"> \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="6b43a-268">および</span><span class="sxs-lookup"><span data-stu-id="6b43a-268">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="6b43a-269">a \ b \\\\ c \ d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-269">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="6b43a-270">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-270">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="6b43a-271">ある\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-271">a\begin{bmatrix}</span></span>
    <span data-ttu-id="6b43a-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-272">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="6b43a-273">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-273">b\begin{bmatrix}</span></span>
    <span data-ttu-id="6b43a-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \\\\<span data-ttu-id="6b43a-275">[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-275">[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="6b43a-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="6b43a-277">a\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-277">d\begin{bmatrix}</span></span>
    <span data-ttu-id="6b43a-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="6b43a-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="6b43a-279">ae \ af \ bf\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-279">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="6b43a-280">ag \ ah \ bg \ bh\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-280">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="6b43a-281">ce \ cf \ de \ df\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-281">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="6b43a-282">cg \ ch \ dg \ dh \end{bmatrix} 。</span><span class="sxs-lookup"><span data-stu-id="6b43a-282">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="6b43a-283">数値表記と製品を囲む最後の便利な規則として、ベクター $ v またはマトリックス m の場合は、 $ $ $ $ { \otimes } $ $ { \otimes } $ $ n フォールドの繰り返しが繰り返されてい $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b43a-283">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="6b43a-284">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b43a-284">For example:</span></span>

\begin{align}
&<span data-ttu-id="6b43a-285">\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 1 } = \begin{bmatrix} \\\\ 0 \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ 0 0 0 \\\\ \\\\ \end{bmatrix} 、 \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} 、\\\\</span><span class="sxs-lookup"><span data-stu-id="6b43a-285">\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  &<span data-ttu-id="6b43a-286">\begin{bmatrix}0 1 1 1 0 1 0 1 1 0 & \\\\ & \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & \\\\ & \end{bmatrix} 、 \qquad \begin{bmatrix} 0 & 1 1 0 \\\\ & 2 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} 0 & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 1 0 0 1 0 = 1 0 0 を0にします。</span><span class="sxs-lookup"><span data-stu-id="6b43a-286">\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
