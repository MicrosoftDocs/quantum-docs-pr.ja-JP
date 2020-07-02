---
title: 量子コンピューティングの線形代数
description: 量子コンピューティングを理解するために必要な線形代数の基本概念について説明します
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 4cf6cce870c7661a7fffc21dcb60dd53cf281ddd
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415442"
---
# <a name="linear-algebra-for-quantum-computing"></a><span data-ttu-id="eb0e1-103">量子コンピューティングの線形代数</span><span class="sxs-lookup"><span data-stu-id="eb0e1-103">Linear algebra for quantum computing</span></span>

<span data-ttu-id="eb0e1-104">線形代数は、量子コンピューティングの数式記法です。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-104">Linear algebra is the language of quantum computing.</span></span> <span data-ttu-id="eb0e1-105">量子プログラムの実装や記述にその知識は必要ありませんが、量子ビットの状態や量子演算を記述するため、および量子コンピューターが一連の命令に応じて実行する処理を予測するために広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-105">Although you don’t need to know it to implement or write quantum programs, it is widely used to describe qubit states, quantum operations, and to predict what a quantum computer will do in response to a sequence of instructions.</span></span>

<span data-ttu-id="eb0e1-106">[量子物理学の基本概念](xref:microsoft.quantum.overview.understanding)をよくわかっていることが量子コンピューティングの理解に役立つ可能性があるのと同様に、線形代数の基礎知識が、量子アルゴリズムの仕組みを理解するうえで役立つと考えられます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-106">Just like being familiar with the [basic concepts of quantum physics](xref:microsoft.quantum.overview.understanding) can help you understand quantum computing, knowing some basic linear algebra can help you understand how quantum algorithms work.</span></span> <span data-ttu-id="eb0e1-107">少なくとも、**ベクトル**と**行列乗算**について理解しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-107">At the least, you’ll want to be familiar with **vectors** and **matrix multiplication**.</span></span> <span data-ttu-id="eb0e1-108">これらの代数の概念についての知識を新たにする必要がある場合は、次のチュートリアルに基本的な説明があります。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-108">If you need to refresh your knowledge of these algebra concepts, here are some tutorials that cover the basics:</span></span>

- [<span data-ttu-id="eb0e1-109">線形代数に関する Jupyter Notebook のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="eb0e1-109">Jupyter notebook tutorial on linear algebra</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [<span data-ttu-id="eb0e1-110">複雑な算術演算に関する Jupyter Notebook のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="eb0e1-110">Jupyter notebook tutorial on complex arithmetic</span></span>](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [<span data-ttu-id="eb0e1-111">量子計算の線形代数</span><span class="sxs-lookup"><span data-stu-id="eb0e1-111">Linear Algebra for Quantum Computation</span></span>](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [<span data-ttu-id="eb0e1-112">線形代数の基礎</span><span class="sxs-lookup"><span data-stu-id="eb0e1-112">Fundamentals of Linear Algebra</span></span>](https://www.math.ubc.ca/~carrell/NB.pdf)
- [<span data-ttu-id="eb0e1-113">量子計算の概要</span><span class="sxs-lookup"><span data-stu-id="eb0e1-113">Quantum Computation Primer</span></span>](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a><span data-ttu-id="eb0e1-114">量子コンピューティングのベクトルと行列</span><span class="sxs-lookup"><span data-stu-id="eb0e1-114">Vectors and matrices in quantum computing</span></span>

<span data-ttu-id="eb0e1-115">トピック「[量子コンピューティングについて](xref:microsoft.quantum.overview.understanding)」では、量子ビットは 1 か 0 の状態または重ね合わせ状態、もしくはこの両方の状態になることができると説明しました。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-115">In the topic [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), you saw that a qubit can be in a state of 1 or 0 or a superposition or both.</span></span> <span data-ttu-id="eb0e1-116">線形代数を使用すると、量子ビットの状態はベクトルとして記述され、1 列**行列** $\begin{bmatrix} a \\\\  b \end{bmatrix}$ で表されます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-116">Using linear algebra, the state of a qubit is described as a vector and is represented by a single column **matrix** $\begin{bmatrix} a \\\\  b \end{bmatrix}$.</span></span> <span data-ttu-id="eb0e1-117">これは、**量子状態ベクトル**とも呼ばれ、$|a|^2 + |b|^2 = 1$ の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-117">It is also known as a **quantum state vector** and must meet the requirement that $|a|^2 + |b|^2 = 1$.</span></span>  

<span data-ttu-id="eb0e1-118">行列の要素は、量子ビットがどちらかの方向に収縮する確率を表しています。$|a|^2$ は 0 に収縮する確率、$|b|^2$ は 1 に収縮する確率です。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-118">The elements of the matrix represent the probability of the qubit collapsing one way or the other, with $|a|^2$ being the probability of collapsing to zero, and $|b|^2$ being the probability of collapsing to one.</span></span> <span data-ttu-id="eb0e1-119">次の行列はすべて、有効な量子状態ベクトルを表しています。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-119">The following matrices all represent valid quantum state vectors:</span></span>

<span data-ttu-id="eb0e1-120">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}、\begin{bmatrix} 0 \\\\  1 \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}、\text{ および }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="eb0e1-120">$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$</span></span>

<span data-ttu-id="eb0e1-121">[量子コンピューターと量子シミュレーター](xref:microsoft.quantum.overview.simulators)では、量子演算を使用して量子ビットの状態を変更することも説明しました。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-121">In [Quantum computers and quantum simulators](xref:microsoft.quantum.overview.simulators) you also saw that quantum operations are used to modify the state of a qubit.</span></span>  <span data-ttu-id="eb0e1-122">量子演算は行列で表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-122">Quantum operations can also be represented by a matrix.</span></span> <span data-ttu-id="eb0e1-123">量子演算が量子ビットに適用される場合、それらを表す 2 つの行列が乗算され、結果として得られる答えは演算後の量子ビットの新しい状態を表します。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-123">When a quantum operation is applied to a qubit, the two matrices that represent them are multiplied and the resulting answer represents the new state of the qubit after the operation.</span></span>  

<span data-ttu-id="eb0e1-124">次に、行列乗算で表される 2 つの一般的な量子演算を示します。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-124">Here are two common quantum operations represented with matrix multiplication.</span></span>


<span data-ttu-id="eb0e1-125">[`X` 演算](xref:microsoft.quantum.intrinsic.x)は次のパウリ行列 $X$ で表されます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-125">The [`X` operation](xref:microsoft.quantum.intrinsic.x) is represented by the Pauli matrix $X$,</span></span>

<span data-ttu-id="eb0e1-126">$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="eb0e1-126">$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$</span></span>
    
<span data-ttu-id="eb0e1-127">これは、たとえば次のように、量子ビットの状態を 0 から 1 (またはその逆) に反転するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-127">and is used to flip the state of a qubit from 0 to 1 (or vice-versa), for example</span></span>

<span data-ttu-id="eb0e1-128">$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="eb0e1-128">$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="eb0e1-129">['H' 演算](xref:microsoft.quantum.intrinsic.h)は、次のようにアダマール変換 $H$ で表されます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-129">The ['H' operation](xref:microsoft.quantum.intrinsic.h) is represented by the Hadamard transformation $H$,</span></span>

<span data-ttu-id="eb0e1-130">$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="eb0e1-130">$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$</span></span>

 <span data-ttu-id="eb0e1-131">この場合、次に示すように、量子ビットが、どちらの方向にも同等の確率で収縮される重ね合わせ状態になります。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-131">and puts a qubit into a superposition state where it has an even probability of collapsing either way, as shown here</span></span>

<span data-ttu-id="eb0e1-132">$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}$$</span><span class="sxs-lookup"><span data-stu-id="eb0e1-132">$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$</span></span>

<span data-ttu-id="eb0e1-133">量子演算を表す行列には 1 つの要件があります。**ユニタリ**行列でなければならないということです。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-133">A matrix that represents a quantum operation has one requirement – it must be a **unitary** matrix.</span></span> <span data-ttu-id="eb0e1-134">行列がユニタリとなるのは、行列の**逆**が行列の**共役転置**と等しい場合です。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-134">A matrix is unitary if the **inverse** of the matrix is equal to the **conjugate transpose** of the matrix.</span></span>

## <a name="representing-two-qubit-states"></a><span data-ttu-id="eb0e1-135">2 つの量子ビットの状態の表現</span><span class="sxs-lookup"><span data-stu-id="eb0e1-135">Representing two-qubit states</span></span>

<span data-ttu-id="eb0e1-136">上記の例では、1 つの量子ビットの状態が 1 列行列 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ を使用して記述され、量子ビットに対する演算の適用は 2 つの行列を乗算して記述されました。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-136">In the examples above, the state of one qubit was described using a single column matrix $\begin{bmatrix} a \\\\  b \end{bmatrix}$, and applying an operation to it was described by multiplying the two matrices.</span></span> <span data-ttu-id="eb0e1-137">しかし、量子コンピューターでは複数の量子ビットが使用されるため、2 つのビットの結合された状態はどのように記述するのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-137">However, quantum computers use more than one qubit, so how do you describe the combined state of two qubits?</span></span> 

<span data-ttu-id="eb0e1-138">各量子ビットはベクトル空間であるため、単なる乗算はできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-138">Remember that each qubit is a vector space, so they can't just be multiplied.</span></span> <span data-ttu-id="eb0e1-139">代わりに、**テンソル積**を使用します。これは、個々のベクトル空間から新しいベクトル空間を作成する関連演算であり、$\otimes$ 記号で表されます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-139">Instead, you use a **tensor product**, which is a related operation that creates a new vector space from individual vector spaces, and is represented by the $\otimes$ symbol.</span></span> <span data-ttu-id="eb0e1-140">たとえば、2 つの量子ビットの状態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ と $\begin{bmatrix} c \\\\  d \end{bmatrix}$ のテンソル積を計算します。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-140">For example, the tensor product of two qubit states $\begin{bmatrix} a \\\\  b \end{bmatrix}$ and $\begin{bmatrix} c \\\\  d \end{bmatrix}$ is calculated</span></span>

<span data-ttu-id="eb0e1-141">$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="eb0e1-141">$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}.</span></span> $$

<span data-ttu-id="eb0e1-142">結果は 4 次元行列になり、各要素は確率を表します。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-142">The result is a four-dimensional matrix, with each element representing a probability.</span></span> <span data-ttu-id="eb0e1-143">たとえば、$ac$ は 0 と 0 に収縮する 2 つの量子ビットの確率であり、$ad$ は 0 と 1 の確率、というようになります。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-143">For example, $ac$ is the probability of the two qubits collapsing to 0 and 0, $ad$ is the probability of 0 and 1, and so on.</span></span> 

<span data-ttu-id="eb0e1-144">1 つの量子ビットの状態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ が量子状態を表すために要件 $|a|^2 + |b|^2 = 1$ を満たさなければならないのと同様に、2 つの量子状態 $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ は要件 $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$ を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-144">Just as a single qubit state $\begin{bmatrix} a \\\\  b \end{bmatrix}$ must meet the requirement that $|a|^2 + |b|^2 = 1$ in order to represent a quantum state, a two-qubit state $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ must meet the requirement that $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.</span></span>

## <a name="summary"></a><span data-ttu-id="eb0e1-145">まとめ</span><span class="sxs-lookup"><span data-stu-id="eb0e1-145">Summary</span></span>

<span data-ttu-id="eb0e1-146">線形代数は、量子コンピューティングと量子物理学を記述するための標準の数式記法です。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-146">Linear algebra is the standard language for describing quantum computing and quantum physics.</span></span> <span data-ttu-id="eb0e1-147">Microsoft Quantum 開発キットに含まれている[ライブラリ](xref:microsoft.quantum.libraries)を利用すると、基になる数学についての知識がなくても高度な量子アルゴリズムを実行できますが、基本を理解しておくことで素早くスタートを切ることができ、確固とした基盤を築くのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb0e1-147">Even though the [libraries](xref:microsoft.quantum.libraries) included with the Microsoft Quantum Development Kit will help you run advanced quantum algorithms without diving into the underlying math, understanding the basics will help you get started quickly and provide a solid foundation to build on.</span></span>

## <a name="next-steps"></a><span data-ttu-id="eb0e1-148">次のステップ</span><span class="sxs-lookup"><span data-stu-id="eb0e1-148">Next steps</span></span>

[<span data-ttu-id="eb0e1-149">QDK をインストールする</span><span class="sxs-lookup"><span data-stu-id="eb0e1-149">Install the QDK</span></span>](xref:microsoft.quantum.install)
