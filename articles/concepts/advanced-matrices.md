---
<span data-ttu-id="6d3cf-101">title: 高度なマトリックスの概念説明: クォンタムアルゴリズムの記述とシミュレーションに使用される基本的なツールである固有ベクトル、eigenvalues、および matrix 指数について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="6d3cf-102">author: QuantumWriter uid: microsoft. quantum................: nawiebe@microsoft.com ms. date: 12/11/2017 ms. topic: article no loc:</span><span class="sxs-lookup"><span data-stu-id="6d3cf-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="6d3cf-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-103">"$$"</span></span>
- <span data-ttu-id="6d3cf-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-104">"$$"</span></span>
- <span data-ttu-id="6d3cf-105">"$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-105">"$"</span></span>
- <span data-ttu-id="6d3cf-106">"$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-106">"$"</span></span>
- <span data-ttu-id="6d3cf-107">"$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-107">"$"</span></span>
- <span data-ttu-id="6d3cf-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-108">"$$"</span></span>
- <span data-ttu-id="6d3cf-109">"$$$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-109">"$$$"</span></span>
- <span data-ttu-id="6d3cf-110">"$$$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-110">"$$$"</span></span>
- <span data-ttu-id="6d3cf-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-111">"$$$"</span></span>
- <span data-ttu-id="6d3cf-112">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-112">"\cdots"</span></span>
- <span data-ttu-id="6d3cf-113">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-113">"bmatrix"</span></span>
- <span data-ttu-id="6d3cf-114">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-114">"\ddots"</span></span>
- <span data-ttu-id="6d3cf-115">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-115">"\equiv"</span></span>
- <span data-ttu-id="6d3cf-116">"\sum"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-116">"\sum"</span></span>
- <span data-ttu-id="6d3cf-117">"\begin"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-117">"\begin"</span></span>
- <span data-ttu-id="6d3cf-118">"\end"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-118">"\end"</span></span>
- <span data-ttu-id="6d3cf-119">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-119">"\sqrt"</span></span>
- <span data-ttu-id="6d3cf-120">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-120">"\otimes"</span></span>
- <span data-ttu-id="6d3cf-121">"{"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-121">"{"</span></span>
- <span data-ttu-id="6d3cf-122">"}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-122">"}"</span></span>
- <span data-ttu-id="6d3cf-123">"\text"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-123">"\text"</span></span>
- <span data-ttu-id="6d3cf-124">"\phi"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-124">"\phi"</span></span>
- <span data-ttu-id="6d3cf-125">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-125">"\kappa"</span></span>
- <span data-ttu-id="6d3cf-126">"\psi"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-126">"\psi"</span></span>
- <span data-ttu-id="6d3cf-127">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-127">"\alpha"</span></span>
- <span data-ttu-id="6d3cf-128">"\beta"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-128">"\beta"</span></span>
- <span data-ttu-id="6d3cf-129">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-129">"\gamma"</span></span>
- <span data-ttu-id="6d3cf-130">"\delta"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-130">"\delta"</span></span>
- <span data-ttu-id="6d3cf-131">"\omega"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-131">"\omega"</span></span>
- <span data-ttu-id="6d3cf-132">"\bra"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-132">"\bra"</span></span>
- <span data-ttu-id="6d3cf-133">"\ket"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-133">"\ket"</span></span>
- <span data-ttu-id="6d3cf-134">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-134">"\boldone"</span></span>
- <span data-ttu-id="6d3cf-135">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-135">"\\\\"</span></span>
- <span data-ttu-id="6d3cf-136">"\\"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-136">"\\"</span></span>
- <span data-ttu-id="6d3cf-137">"="</span><span class="sxs-lookup"><span data-stu-id="6d3cf-137">"="</span></span>
- <span data-ttu-id="6d3cf-138">"\frac"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-138">"\frac"</span></span>
- <span data-ttu-id="6d3cf-139">"\text"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-139">"\text"</span></span>
- <span data-ttu-id="6d3cf-140">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-140">"\mapsto"</span></span>
- <span data-ttu-id="6d3cf-141">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-141">"\dagger"</span></span>
- <span data-ttu-id="6d3cf-142">"\to"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-142">"\to"</span></span>
- <span data-ttu-id="6d3cf-143">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-143">"\begin{cases}"</span></span>
- <span data-ttu-id="6d3cf-144">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-144">"\end{cases}"</span></span>
- <span data-ttu-id="6d3cf-145">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-145">"\operatorname"</span></span>
- <span data-ttu-id="6d3cf-146">"\braket"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-146">"\braket"</span></span>
- <span data-ttu-id="6d3cf-147">"\id"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-147">"\id"</span></span>
- <span data-ttu-id="6d3cf-148">"\expect"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-148">"\expect"</span></span>
- <span data-ttu-id="6d3cf-149">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-149">"\defeq"</span></span>
- <span data-ttu-id="6d3cf-150">"\variance"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-150">"\variance"</span></span>
- <span data-ttu-id="6d3cf-151">"\dd"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-151">"\dd"</span></span>
- <span data-ttu-id="6d3cf-152">"&"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-152">"&"</span></span>
- <span data-ttu-id="6d3cf-153">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-153">"\begin{align}"</span></span>
- <span data-ttu-id="6d3cf-154">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-154">"\end{align}"</span></span>
- <span data-ttu-id="6d3cf-155">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-155">"\Lambda"</span></span>
- <span data-ttu-id="6d3cf-156">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-156">"\lambda"</span></span>
- <span data-ttu-id="6d3cf-157">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-157">"\Omega"</span></span>
- <span data-ttu-id="6d3cf-158">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-158">"\mathrm"</span></span>
- <span data-ttu-id="6d3cf-159">"\left"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-159">"\left"</span></span>
- <span data-ttu-id="6d3cf-160">"\right"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-160">"\right"</span></span>
- <span data-ttu-id="6d3cf-161">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-161">"\qquad"</span></span>
- <span data-ttu-id="6d3cf-162">"\times"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-162">"\times"</span></span>
- <span data-ttu-id="6d3cf-163">"\big"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-163">"\big"</span></span>
- <span data-ttu-id="6d3cf-164">"\langle"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-164">"\langle"</span></span>
- <span data-ttu-id="6d3cf-165">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-165">"\rangle"</span></span>
- <span data-ttu-id="6d3cf-166">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-166">"\bigg"</span></span>
- <span data-ttu-id="6d3cf-167">"\Big"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-167">"\Big"</span></span>
- <span data-ttu-id="6d3cf-168">"|"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-168">"|"</span></span>
- <span data-ttu-id="6d3cf-169">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-169">"\mathbb"</span></span>
- <span data-ttu-id="6d3cf-170">"\vec"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-170">"\vec"</span></span>
- <span data-ttu-id="6d3cf-171">"\in"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-171">"\in"</span></span>
- <span data-ttu-id="6d3cf-172">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-172">"\texttt"</span></span>
- <span data-ttu-id="6d3cf-173">"\ne"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-173">"\ne"</span></span>
- <span data-ttu-id="6d3cf-174">"<"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-174">"<"</span></span>
- <span data-ttu-id="6d3cf-175">">"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-175">">"</span></span>
- <span data-ttu-id="6d3cf-176">"\leq"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-176">"\leq"</span></span>
- <span data-ttu-id="6d3cf-177">"\geq"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-177">"\geq"</span></span>
- <span data-ttu-id="6d3cf-178">"~~"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-178">"~~"</span></span>
- <span data-ttu-id="6d3cf-179">"~"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-179">"~"</span></span>
- <span data-ttu-id="6d3cf-180">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-180">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="6d3cf-181">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-181">"\end{bmatrix}"</span></span>
- <span data-ttu-id="6d3cf-182">"\_"</span><span class="sxs-lookup"><span data-stu-id="6d3cf-182">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="6d3cf-183">高度なマトリックスの概念</span><span class="sxs-lookup"><span data-stu-id="6d3cf-183">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="6d3cf-184">マトリックスの操作を[*Eigenvalues、固有ベクトル*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)、[*指数*](https://en.wikipedia.org/wiki/Matrix_exponential)に拡張しました。これにより、クォンタムアルゴリズムの記述と実装に必要なツールの基本的なセットが形成されます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-184">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="6d3cf-185">Eigenvalues と固有ベクトル</span><span class="sxs-lookup"><span data-stu-id="6d3cf-185">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="6d3cf-186">$M を $ 正方形行列にし、 $ v は $ すべてゼロベクトルではないベクター (つまり、すべてのエントリが0に等しいベクトル) に $ し $ ます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-186">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="6d3cf-187">$ $ たとえば、 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)があると $ $ $ します。この場合、 = 数 c の Mv cv が発生 $ $ $ します。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-187">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="6d3cf-188">$C $ は eigenvector v に対応する[*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)であると言い $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-188">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="6d3cf-189">一般に、マトリックス $ M は $ ベクターを他のベクターに変換することがありますが、eigenvector は特殊なものです。これは、数値で乗算される点を除いて、変更されていないためです。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-189">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="6d3cf-190">$V $ が eigenvalue c の eigenvector である場合 $ $ 、 $ $ $ 同じ eigenvalue を持つ av は eigenvector (0 以外の a の場合) でも $ あることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-190">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="6d3cf-191">たとえば、id 行列の場合、すべての vector $ v $ は eigenvalue 1 の eigenvector $ に $ なります。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-191">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="6d3cf-192">もう1つの例と[*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix)して、対角線 $ $ に0以外のエントリのみを持つ対角線行列 D を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-192">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="6d3cf-193">d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & d_3 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-193">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="6d3cf-194">ベクター</span><span class="sxs-lookup"><span data-stu-id="6d3cf-194">The vectors</span></span>

$$<span data-ttu-id="6d3cf-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="6d3cf-195">\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="6d3cf-196">このマトリックスの固有ベクトルは $ $ 、それぞれ d_1、 $ d_2 $ 、および $ d_3 $ です。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-196">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="6d3cf-197">$D_1 $ 、 $ d_2 $ 、 $ d_3 が個別の数値の場合 $ 、これらのベクター (およびそのマルチプル) はマトリックス d の唯一の固有ベクトルです $ $ 。一般に、対角線マトリックスの場合は、固有値と固有ベクトルを簡単に読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-197">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="6d3cf-198">固有値は、対角線に表示されるすべての数値であり、それぞれの固有ベクトルは1つのエントリが1で、 $ $ 残りのエントリが0に等しい単位ベクターです $ $ 。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-198">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="6d3cf-199">上の例では、D の固有ベクトル $ が $ 3 次元ベクトルのベースになっていることに注意して $ $ ください。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-199">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="6d3cf-200">ベースはベクターのセットであり、ベクターを線形の組み合わせとして書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-200">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="6d3cf-201">より明示的、 $ v_1 $ 、 $ v_2 $ 、および v_3 は、 $ $ $ $ $ = $ 何らかの数値 $ v_1 $ 、 $ a_2 $ 、および v_2 $ $ に対して v a_1 a_3 + v_3 a_1 + a_2 a_3 として記述することができます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-201">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="6d3cf-202">Hermitian matrix (自己 adjoint とも呼ばれます) は複雑な四角形行列で、独自の複素共役転置と同じであることに注意してください。さらに、ユニタリ行列は、その逆が adjoint または複雑な共役転置と等しい複合正方形行列です。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-202">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="6d3cf-203">基本的には、Hermitian およびユニタリ行列は、クォンタムコンピューティングで検出された唯一のマトリックスで、次をアサートする、[*スペクトル定理*](https://en.wikipedia.org/wiki/Spectral_theorem)と呼ばれる一般的な結果があります。 Hermitian またはマトリックス m の場合は、 $ $ 1 つの $ $ $ = \dagger $ 対角線のマトリックス d に $ 対し $ て m u ^ D u が使用されます。さらに、D の対角線のエントリは $ $ M の固有値になり $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-203">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="6d3cf-204">固有ベクトルの固有値とを計算する方法は既にわかって $ $ います D。この定理を使用して、 $ v $ が $ $ eigenvalue c の eigenvector ( $ $ つまり、Dv cv) である場合、 $ = $ $ U ^ \dagger v は $ $ $ eigenvalue c の eigenvector になり $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-204">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="6d3cf-205">これは、</span><span class="sxs-lookup"><span data-stu-id="6d3cf-205">This is because</span></span>

$$<span data-ttu-id="6d3cf-206">M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v$$</span><span class="sxs-lookup"><span data-stu-id="6d3cf-206">M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="6d3cf-207">マトリックス指数</span><span class="sxs-lookup"><span data-stu-id="6d3cf-207">Matrix Exponentials</span></span>
<span data-ttu-id="6d3cf-208">指数関数と完全に同じように[*行列指数*](https://en.wikipedia.org/wiki/Matrix_exponential)を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-208">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="6d3cf-209">マトリックス a の行列指数は $ 、 $ として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-209">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="6d3cf-210">e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac {^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="6d3cf-210">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="6d3cf-211">このことが重要なのは、クォンタムの機械的な時間の進化は、 $ { } $ Hermitian matrix B の e ^ iB 形式 $ のユニタリ行列によって記述されるためです $ 。 このため、matrix 指数の実行はクォンタムコンピューティングの基本的な部分であり、そのような Q # はこれらの操作を記述するための組み込みルーチンを提供しています。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-211">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="6d3cf-212">従来のコンピューターで行列指数を計算するには、多くの方法がありますが、通常は数値の近い数値でしかしが発生します。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-212">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="6d3cf-213">「 [*Cleve Moler とチャールズ Van ローン」を参照してください。"Nineteen あいまいにより、マトリックスの指数を計算することができます。"関連する課題の詳細については、「SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-213">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="6d3cf-214">マトリックスの指数を計算する方法を理解する最も簡単な方法は、そのマトリックスの固有値と固有ベクトルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-214">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="6d3cf-215">具体的には、前に説明したスペクトル定理では、すべての Hermitian または行列に対して、1つのユニタリ行列が存在し、その中に " $ $ $ $ $ $ u ^ D u" などの対角線行列 $ = \dagger $ があることが示されています。 Unitarity ティのプロパティにより、 $ ^ 2 = u ^ \dagger d ^ 2 u $ と同様に、任意の power $ p $ $ a ^ p = U ^ \dagger d ^ p u $ が使用されています。 これを演算子指数の演算子定義に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-215">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="6d3cf-216">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right )U = u ^ \dagger \begin{bmatrix} \ exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \ exp (D_ { 22 } ) 0 \ (vドット \)-vドット & \cdots & \\\\ & & \ddots & \\\\ 0 & 0 & \cdots & \ exp (D_ { NN } ) \end{bmatrix} U。$$</span><span class="sxs-lookup"><span data-stu-id="6d3cf-216">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="6d3cf-217">つまり、マトリックス A の eigenbasis に変換する場合、行列 $ 指数を $ 計算することは、マトリックスの eigenbasis の通常の指数を計算することと同じです。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-217">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="6d3cf-218">クォンタムコンピューティングにおける多くの操作には、matrix 指数の実行が含まれています。そのため、マトリックスの eigenbasis に変換することにより、演算子指数が頻繁に表示されるようになり、このガイドの後半で説明する Trotter – Suzuki-スタイルのクォンタムシミュレーションメソッドなど、多くのクォンタムアルゴリズムが基礎となります。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-218">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="6d3cf-219">B がユニタリと Hermitian の両方である場合は、もう1つの便利なプロパティがあり $ $ ます。つまり、 $ b = b ^ { -1 b ^、 } = \dagger $ $ b ^ 2 = \boldone $ のようになります。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-219">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="6d3cf-220">上記の行列指数の展開にこのルールを適用することにより、と B の用語をグループ化することで $ \boldone $ $ $ 、任意の実数 $ x の id について確認できます $ 。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-220">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

$$<span data-ttu-id="6d3cf-221">e ^ { ibx } = \boldone \ cos (x) + ibx sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="6d3cf-221">e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="6d3cf-222">収容.</span><span class="sxs-lookup"><span data-stu-id="6d3cf-222">holds.</span></span> <span data-ttu-id="6d3cf-223">この方法は特に便利です。 b の次元が指数関数的に大きい場合でも、b $ $ $ が Hermitian である場合でも、マトリックス指数のアクションに関する理由があるためです $ 。</span><span class="sxs-lookup"><span data-stu-id="6d3cf-223">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
