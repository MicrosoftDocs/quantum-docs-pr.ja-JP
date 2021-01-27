---
<span data-ttu-id="762c4-101">title: 高度なマトリックスの概念説明: クォンタムアルゴリズムの記述とシミュレーションに使用される基本的なツールである固有ベクトル、eigenvalues、および matrix 指数について説明します。</span><span class="sxs-lookup"><span data-stu-id="762c4-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="762c4-102">author: QuantumWriter uid: benbra: 12/11/2017 ミリ秒。日付: ミリ秒。トピック: 概念に関係ありません (& a):</span><span class="sxs-lookup"><span data-stu-id="762c4-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="762c4-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="762c4-103">"Q#"</span></span>
- <span data-ttu-id="762c4-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="762c4-104">"$$v"</span></span>
- <span data-ttu-id="762c4-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="762c4-105">"$$"</span></span>
- <span data-ttu-id="762c4-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="762c4-106">"$$"</span></span>
- <span data-ttu-id="762c4-107">"$"</span><span class="sxs-lookup"><span data-stu-id="762c4-107">"$"</span></span>
- <span data-ttu-id="762c4-108">"$"</span><span class="sxs-lookup"><span data-stu-id="762c4-108">"$"</span></span>
- <span data-ttu-id="762c4-109">"$"</span><span class="sxs-lookup"><span data-stu-id="762c4-109">"$"</span></span>
- <span data-ttu-id="762c4-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="762c4-110">"$$"</span></span>
- <span data-ttu-id="762c4-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="762c4-111">"$$$"</span></span>
- <span data-ttu-id="762c4-112">"$$$"</span><span class="sxs-lookup"><span data-stu-id="762c4-112">"$$$"</span></span>
- <span data-ttu-id="762c4-113">"$$$"</span><span class="sxs-lookup"><span data-stu-id="762c4-113">"$$$"</span></span>
- <span data-ttu-id="762c4-114">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="762c4-114">"\cdots"</span></span>
- <span data-ttu-id="762c4-115">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="762c4-115">"bmatrix"</span></span>
- <span data-ttu-id="762c4-116">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="762c4-116">"\ddots"</span></span>
- <span data-ttu-id="762c4-117">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="762c4-117">"\equiv"</span></span>
- <span data-ttu-id="762c4-118">"\sum"</span><span class="sxs-lookup"><span data-stu-id="762c4-118">"\sum"</span></span>
- <span data-ttu-id="762c4-119">"\begin"</span><span class="sxs-lookup"><span data-stu-id="762c4-119">"\begin"</span></span>
- <span data-ttu-id="762c4-120">"\end"</span><span class="sxs-lookup"><span data-stu-id="762c4-120">"\end"</span></span>
- <span data-ttu-id="762c4-121">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="762c4-121">"\sqrt"</span></span>
- <span data-ttu-id="762c4-122">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="762c4-122">"\otimes"</span></span>
- <span data-ttu-id="762c4-123">"{"</span><span class="sxs-lookup"><span data-stu-id="762c4-123">"{"</span></span>
- <span data-ttu-id="762c4-124">"}"</span><span class="sxs-lookup"><span data-stu-id="762c4-124">"}"</span></span>
- <span data-ttu-id="762c4-125">"\text"</span><span class="sxs-lookup"><span data-stu-id="762c4-125">"\text"</span></span>
- <span data-ttu-id="762c4-126">"\phi"</span><span class="sxs-lookup"><span data-stu-id="762c4-126">"\phi"</span></span>
- <span data-ttu-id="762c4-127">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="762c4-127">"\kappa"</span></span>
- <span data-ttu-id="762c4-128">"\psi"</span><span class="sxs-lookup"><span data-stu-id="762c4-128">"\psi"</span></span>
- <span data-ttu-id="762c4-129">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="762c4-129">"\alpha"</span></span>
- <span data-ttu-id="762c4-130">"\beta"</span><span class="sxs-lookup"><span data-stu-id="762c4-130">"\beta"</span></span>
- <span data-ttu-id="762c4-131">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="762c4-131">"\gamma"</span></span>
- <span data-ttu-id="762c4-132">"\delta"</span><span class="sxs-lookup"><span data-stu-id="762c4-132">"\delta"</span></span>
- <span data-ttu-id="762c4-133">"\omega"</span><span class="sxs-lookup"><span data-stu-id="762c4-133">"\omega"</span></span>
- <span data-ttu-id="762c4-134">"\bra"</span><span class="sxs-lookup"><span data-stu-id="762c4-134">"\bra"</span></span>
- <span data-ttu-id="762c4-135">"\ket"</span><span class="sxs-lookup"><span data-stu-id="762c4-135">"\ket"</span></span>
- <span data-ttu-id="762c4-136">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="762c4-136">"\boldone"</span></span>
- <span data-ttu-id="762c4-137">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="762c4-137">"\\\\"</span></span>
- <span data-ttu-id="762c4-138">"\\"</span><span class="sxs-lookup"><span data-stu-id="762c4-138">"\\"</span></span>
- <span data-ttu-id="762c4-139">"="</span><span class="sxs-lookup"><span data-stu-id="762c4-139">"="</span></span>
- <span data-ttu-id="762c4-140">"\frac"</span><span class="sxs-lookup"><span data-stu-id="762c4-140">"\frac"</span></span>
- <span data-ttu-id="762c4-141">"\text"</span><span class="sxs-lookup"><span data-stu-id="762c4-141">"\text"</span></span>
- <span data-ttu-id="762c4-142">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="762c4-142">"\mapsto"</span></span>
- <span data-ttu-id="762c4-143">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="762c4-143">"\dagger"</span></span>
- <span data-ttu-id="762c4-144">"\to"</span><span class="sxs-lookup"><span data-stu-id="762c4-144">"\to"</span></span>
- <span data-ttu-id="762c4-145">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="762c4-145">"\begin{cases}"</span></span>
- <span data-ttu-id="762c4-146">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="762c4-146">"\end{cases}"</span></span>
- <span data-ttu-id="762c4-147">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="762c4-147">"\operatorname"</span></span>
- <span data-ttu-id="762c4-148">"\braket"</span><span class="sxs-lookup"><span data-stu-id="762c4-148">"\braket"</span></span>
- <span data-ttu-id="762c4-149">"\id"</span><span class="sxs-lookup"><span data-stu-id="762c4-149">"\id"</span></span>
- <span data-ttu-id="762c4-150">"\expect"</span><span class="sxs-lookup"><span data-stu-id="762c4-150">"\expect"</span></span>
- <span data-ttu-id="762c4-151">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="762c4-151">"\defeq"</span></span>
- <span data-ttu-id="762c4-152">"\variance"</span><span class="sxs-lookup"><span data-stu-id="762c4-152">"\variance"</span></span>
- <span data-ttu-id="762c4-153">"\dd"</span><span class="sxs-lookup"><span data-stu-id="762c4-153">"\dd"</span></span>
- <span data-ttu-id="762c4-154">"&"</span><span class="sxs-lookup"><span data-stu-id="762c4-154">"&"</span></span>
- <span data-ttu-id="762c4-155">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="762c4-155">"\begin{align}"</span></span>
- <span data-ttu-id="762c4-156">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="762c4-156">"\end{align}"</span></span>
- <span data-ttu-id="762c4-157">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="762c4-157">"\Lambda"</span></span>
- <span data-ttu-id="762c4-158">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="762c4-158">"\lambda"</span></span>
- <span data-ttu-id="762c4-159">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="762c4-159">"\Omega"</span></span>
- <span data-ttu-id="762c4-160">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="762c4-160">"\mathrm"</span></span>
- <span data-ttu-id="762c4-161">"\left"</span><span class="sxs-lookup"><span data-stu-id="762c4-161">"\left"</span></span>
- <span data-ttu-id="762c4-162">"\right"</span><span class="sxs-lookup"><span data-stu-id="762c4-162">"\right"</span></span>
- <span data-ttu-id="762c4-163">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="762c4-163">"\qquad"</span></span>
- <span data-ttu-id="762c4-164">"\times"</span><span class="sxs-lookup"><span data-stu-id="762c4-164">"\times"</span></span>
- <span data-ttu-id="762c4-165">"\big"</span><span class="sxs-lookup"><span data-stu-id="762c4-165">"\big"</span></span>
- <span data-ttu-id="762c4-166">"\langle"</span><span class="sxs-lookup"><span data-stu-id="762c4-166">"\langle"</span></span>
- <span data-ttu-id="762c4-167">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="762c4-167">"\rangle"</span></span>
- <span data-ttu-id="762c4-168">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="762c4-168">"\bigg"</span></span>
- <span data-ttu-id="762c4-169">"\Big"</span><span class="sxs-lookup"><span data-stu-id="762c4-169">"\Big"</span></span>
- <span data-ttu-id="762c4-170">"|"</span><span class="sxs-lookup"><span data-stu-id="762c4-170">"|"</span></span>
- <span data-ttu-id="762c4-171">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="762c4-171">"\mathbb"</span></span>
- <span data-ttu-id="762c4-172">"\vec"</span><span class="sxs-lookup"><span data-stu-id="762c4-172">"\vec"</span></span>
- <span data-ttu-id="762c4-173">"\in"</span><span class="sxs-lookup"><span data-stu-id="762c4-173">"\in"</span></span>
- <span data-ttu-id="762c4-174">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="762c4-174">"\texttt"</span></span>
- <span data-ttu-id="762c4-175">"\ne"</span><span class="sxs-lookup"><span data-stu-id="762c4-175">"\ne"</span></span>
- <span data-ttu-id="762c4-176">"<"</span><span class="sxs-lookup"><span data-stu-id="762c4-176">"<"</span></span>
- <span data-ttu-id="762c4-177">">"</span><span class="sxs-lookup"><span data-stu-id="762c4-177">">"</span></span>
- <span data-ttu-id="762c4-178">"\leq"</span><span class="sxs-lookup"><span data-stu-id="762c4-178">"\leq"</span></span>
- <span data-ttu-id="762c4-179">"\geq"</span><span class="sxs-lookup"><span data-stu-id="762c4-179">"\geq"</span></span>
- <span data-ttu-id="762c4-180">"~~"</span><span class="sxs-lookup"><span data-stu-id="762c4-180">"~~"</span></span>
- <span data-ttu-id="762c4-181">"~"</span><span class="sxs-lookup"><span data-stu-id="762c4-181">"~"</span></span>
- <span data-ttu-id="762c4-182">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="762c4-182">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="762c4-183">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="762c4-183">"\end{bmatrix}"</span></span>
- <span data-ttu-id="762c4-184">"\_"</span><span class="sxs-lookup"><span data-stu-id="762c4-184">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="762c4-185">高度なマトリックスの概念</span><span class="sxs-lookup"><span data-stu-id="762c4-185">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="762c4-186">マトリックスの操作を [*Eigenvalues、固有ベクトル*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) 、 [*指数*](https://en.wikipedia.org/wiki/Matrix_exponential) に拡張しました。これにより、クォンタムアルゴリズムの記述と実装に必要なツールの基本的なセットが形成されます。</span><span class="sxs-lookup"><span data-stu-id="762c4-186">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="762c4-187">Eigenvalues と固有ベクトル</span><span class="sxs-lookup"><span data-stu-id="762c4-187">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="762c4-188">$M を $ 正方形行列にし、 $ v は $ すべてゼロベクトルではないベクター (つまり、すべてのエントリが0に等しいベクトル) に $ し $ ます。</span><span class="sxs-lookup"><span data-stu-id="762c4-188">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="762c4-189">$ $ たとえば、 [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)があると $ $ $ します。この場合、 = 数 c の Mv cv が発生 $ $ $ します。</span><span class="sxs-lookup"><span data-stu-id="762c4-189">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="762c4-190">$C $ は eigenvector v に対応する [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)であると言い $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="762c4-190">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="762c4-191">一般に、マトリックス $ M は $ ベクターを他のベクターに変換することがありますが、eigenvector は特殊なものです。これは、数値で乗算される点を除いて、変更されていないためです。</span><span class="sxs-lookup"><span data-stu-id="762c4-191">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="762c4-192">$V $ が eigenvalue c の eigenvector である場合 $ $ 、 $ $ $ 同じ eigenvalue を持つ av は eigenvector (0 以外の a の場合) でも $ あることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="762c4-192">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="762c4-193">たとえば、id 行列の場合、すべての vector $ v $ は eigenvalue 1 の eigenvector $ に $ なります。</span><span class="sxs-lookup"><span data-stu-id="762c4-193">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="762c4-194">もう1つの例と[](https://en.wikipedia.org/wiki/Diagonal_matrix)して、対角線 $ $ に0以外のエントリのみを持つ対角線行列 D を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="762c4-194">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="762c4-195">d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & d_3 \end{bmatrix} です。</span><span class="sxs-lookup"><span data-stu-id="762c4-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="762c4-196">ベクター</span><span class="sxs-lookup"><span data-stu-id="762c4-196">The vectors</span></span>

<span data-ttu-id="762c4-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} 、 \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="762c4-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="762c4-198">このマトリックスの固有ベクトルは  $ $ 、それぞれ d_1、 $ d_2 $ 、および $ d_3 $ です。</span><span class="sxs-lookup"><span data-stu-id="762c4-198">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="762c4-199">$D_1 $ 、 $ d_2 $ 、 $ d_3 が個別の数値の場合 $ 、これらのベクター (およびそのマルチプル) はマトリックス d の唯一の固有ベクトルです $ $ 。一般に、対角線マトリックスの場合は、固有値と固有ベクトルを簡単に読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="762c4-199">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="762c4-200">固有値は、対角線に表示されるすべての数値であり、それぞれの固有ベクトルは1つのエントリが1で、 $ $ 残りのエントリが0に等しい単位ベクターです $ $ 。</span><span class="sxs-lookup"><span data-stu-id="762c4-200">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="762c4-201">上の例では、D の固有ベクトル $ が $ 3 次元ベクトルのベースになっていることに注意して $ $ ください。</span><span class="sxs-lookup"><span data-stu-id="762c4-201">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="762c4-202">ベースはベクターのセットであり、ベクターを線形の組み合わせとして書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="762c4-202">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="762c4-203">より明示的、 $ v_1 $ 、 $ v_2 $ 、および v_3 は、 $ $ $ $ $ = $ 何らかの数値 $ v_1 $ 、 $ a_2 $ 、および v_2 $ $ に対して v a_1 a_3 + v_3 a_1 + a_2 a_3 として記述することができます。</span><span class="sxs-lookup"><span data-stu-id="762c4-203">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="762c4-204">Hermitian matrix (自己 adjoint とも呼ばれます) は複雑な四角形行列で、独自の複素共役転置と同じであることに注意してください。さらに、ユニタリ行列は、その逆が adjoint または複雑な共役転置と等しい複合正方形行列です。</span><span class="sxs-lookup"><span data-stu-id="762c4-204">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="762c4-205">基本的には、Hermitian およびユニタリ行列は、クォンタムコンピューティングで検出された唯一のマトリックスで、次をアサートする、 [*スペクトル定理*](https://en.wikipedia.org/wiki/Spectral_theorem)と呼ばれる一般的な結果があります。 Hermitian またはマトリックス m の場合は、 $ $ 1 つの $ $ $ = \dagger $ 対角線のマトリックス d に $ 対し $ て m u ^ D u が使用されます。さらに、D の対角線のエントリは $ $ M の固有値になり $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="762c4-205">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="762c4-206">固有ベクトルの固有値とを計算する方法は既にわかって $ $ います D。この定理を使用して、 $ v $ が $ $ eigenvalue c の eigenvector ( $ $ つまり、Dv cv) である場合、 $ = $ $ U ^ \dagger v は $ $ $ eigenvalue c の eigenvector になり $ $ ます。</span><span class="sxs-lookup"><span data-stu-id="762c4-206">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="762c4-207">これは、</span><span class="sxs-lookup"><span data-stu-id="762c4-207">This is because</span></span>

<span data-ttu-id="762c4-208">$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v$$</span><span class="sxs-lookup"><span data-stu-id="762c4-208">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="762c4-209">マトリックス指数</span><span class="sxs-lookup"><span data-stu-id="762c4-209">Matrix Exponentials</span></span>
<span data-ttu-id="762c4-210">指数関数と完全に同じように [*行列指数*](https://en.wikipedia.org/wiki/Matrix_exponential) を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="762c4-210">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="762c4-211">マトリックス a の行列指数は $ 、 $ として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="762c4-211">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="762c4-212">e ^ A = \boldone + a + \frac { a ^ 2 } { 2! } + \frac {^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="762c4-212">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="762c4-213">このことが重要なのは、クォンタムの機械的な時間の進化は、 $ { } $ Hermitian matrix B の e ^ iB 形式 $ のユニタリ行列によって記述されるためです $ 。 このため、matrix 指数の実行はクォンタムコンピューティングの基本的な部分であり、そのため、 Q# これらの操作を記述するための組み込みルーチンが用意されています。</span><span class="sxs-lookup"><span data-stu-id="762c4-213">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="762c4-214">従来のコンピューターで行列指数を計算するには、多くの方法がありますが、通常は数値の近い数値でしかしが発生します。</span><span class="sxs-lookup"><span data-stu-id="762c4-214">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="762c4-215">「 [*Cleve Moler とチャールズ Van ローン」を参照してください。"Nineteen あいまいにより、マトリックスの指数を計算することができます。"関連する課題の詳細については、「SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="762c4-215">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="762c4-216">マトリックスの指数を計算する方法を理解する最も簡単な方法は、そのマトリックスの固有値と固有ベクトルを使用することです。</span><span class="sxs-lookup"><span data-stu-id="762c4-216">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="762c4-217">具体的には、前に説明したスペクトル定理では、すべての Hermitian または行列に対して、1つのユニタリ行列が存在し、その中に " $ $ $ $ $ $ u ^ D u" などの対角線行列 $ = \dagger $ があることが示されています。 Unitarity ティのプロパティにより、 $ ^ 2 = u ^ \dagger d ^ 2 u $ と同様に、任意の power $ p $ $ a ^ p = U ^ \dagger d ^ p u $ が使用されています。 これを演算子指数の演算子定義に置き換えると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="762c4-217">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="762c4-218">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right )U = u ^ \dagger \begin{bmatrix} \ exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \ exp (D_ { 22 } ) 0 \ (vドット \)-vドット & \cdots & \\\\ & & \ddots & \\\\ 0 & 0 & \cdots & \ exp (D_ { NN } ) \end{bmatrix} U。$$</span><span class="sxs-lookup"><span data-stu-id="762c4-218">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="762c4-219">つまり、マトリックス A の eigenbasis に変換する場合、行列 $ 指数を $ 計算することは、マトリックスの eigenbasis の通常の指数を計算することと同じです。</span><span class="sxs-lookup"><span data-stu-id="762c4-219">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="762c4-220">クォンタムコンピューティングにおける多くの操作には、matrix 指数の実行が含まれています。そのため、マトリックスの eigenbasis に変換することにより、演算子指数が頻繁に表示されるようになり、このガイドの後半で説明する Trotter – Suzuki-スタイルのクォンタムシミュレーションメソッドなど、多くのクォンタムアルゴリズムが基礎となります。</span><span class="sxs-lookup"><span data-stu-id="762c4-220">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="762c4-221">B がユニタリと Hermitian の両方である場合は、もう1つの便利なプロパティがあり $ $ ます。つまり、 $ b = b ^ { -1 b ^、 } = \dagger $ $ b ^ 2 = \boldone $ のようになります。</span><span class="sxs-lookup"><span data-stu-id="762c4-221">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="762c4-222">上記の行列指数の展開にこのルールを適用することにより、と B の用語をグループ化することで $ \boldone $ $ $ 、任意の実数 $ x の id について確認できます $ 。</span><span class="sxs-lookup"><span data-stu-id="762c4-222">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="762c4-223">$$e ^ { ibx } = \boldone \ cos (x) + ibx sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="762c4-223">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="762c4-224">収容.</span><span class="sxs-lookup"><span data-stu-id="762c4-224">holds.</span></span> <span data-ttu-id="762c4-225">この方法は特に便利です。 b の次元が指数関数的に大きい場合でも、b $ $ $ が Hermitian である場合でも、マトリックス指数のアクションに関する理由があるためです $ 。</span><span class="sxs-lookup"><span data-stu-id="762c4-225">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
