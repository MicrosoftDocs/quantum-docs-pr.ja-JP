---
title: 量子オラクル
description: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630315"
---
# <a name="quantum-oracles"></a><span data-ttu-id="6b9cc-103">Quantum Oracles</span><span class="sxs-lookup"><span data-stu-id="6b9cc-103">Quantum Oracles</span></span>

<span data-ttu-id="6b9cc-104">Oracle $O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="6b9cc-105">多くの場合、このような操作は従来の関数 $f を使用して定義されます。 \\ {0, 1 \\ } ^ n \ \\ {0, 1 \\ } ^ m は、 $ $n $ ビットのバイナリ入力を受け取り、$m ビットのバイナリ出力を生成し $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="6b9cc-106">これを行うには、$x = (x_ {0 } , x_ {1 } , \ ドット, x_ {n-1) $ という特定のバイナリ入力を考えてみ } ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="6b9cc-107">Qubit 状態には、$ \ket { \ vec{x } } = \ket{x_ {0 } } \ otimes \ket{x_ {1}/otimes } /cドット/otimes \ket{x_ {n-1 } } $ というラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="6b9cc-108">最初に、 $ $O \ket {x = \ket{f (x)} $ に $O を定義しようとしましたが、これには } いくつかの問題があります。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="6b9cc-109">最初に、$f $ の入力と出力のサイズが異なる場合があります ($n \n e m)。これにより $ $O を適用すると $ レジスタの qubits の数が変更されます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="6b9cc-110">2番目に、$n = m の場合でも、関数が反転できるになら $ ない可能性があります。たとえば、一部の $x \n e y に対して $f (x) = f (y) $ を指定する $ と、$O \ket {x } = O \ket {y } $ は $O ^-ダガー o { \ket x } \n e o ^ & ダガー o \ket {y } $ です。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="6b9cc-111">つまり、oracles に adjoint $O 操作を作成できなくなり $ 、に adjoint が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="6b9cc-112">計算ベースの状態に影響を与える oracle の定義</span><span class="sxs-lookup"><span data-stu-id="6b9cc-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="6b9cc-113">回答を保持する $m qubits の2番目のレジスタを導入することで、両方の問題に対処でき $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="6b9cc-114">次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $x \ \\ {0, 1 \\ } ^ n $ と $y \ \\ {0, 1 \\ } ^ m $ で実行します。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="6b9cc-115">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-115">$$ \begin{align}</span></span>
    <span data-ttu-id="6b9cc-116">O (\ket{x/ } otimes \ket{y } ) = \ket{x } 、otimes \ket{y、oplus f (x)}。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="6b9cc-117">& end{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-117">\end{align}</span></span>
$$

<span data-ttu-id="6b9cc-118">ここでは、$O = O ^ \ $ を構築しています。したがって、以前の問題の両方を解決しました。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="6b9cc-119">$O = O ^ {\ ダガー $ であることを確認するには、 } $O ^ 2 = \ $ $a の後に、 $ すべての $a の b = a ( \{ 0, 1 $) を使用し \} ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="6b9cc-120">結果として、$O \ket{x } \ket{y と f (x)} = \ket{x \ket{y と f ( } x) \ oplus f (x)} = \ket{x \ket{y $ のようになり } } ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="6b9cc-121">重要な点として、各計算基準の状態に対して oracle を定義すると、$ \ket{x } \ket{y } $ は $ 他の状態に対してどのように動作 $O するかも定義します。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="6b9cc-122">これ $ は、すべてのクォンタム操作と同様に、処理が実行されている状態で線形である $O という事実からすぐに続きます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="6b9cc-123">たとえば、$H \ket{0 } = \ket { +} $ および $H \ket{1 } = \ket-} $ によって定義されている Hadamard 操作を考えてみ { ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="6b9cc-124">$H が $ \ket +} $ でどのように動作するかを知りたい場合は、 $ { 線形の $H を使用できます。 $</span><span class="sxs-lookup"><span data-stu-id="6b9cc-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="6b9cc-125">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-125">$$ \begin{align}</span></span>
<span data-ttu-id="6b9cc-126">H \ket { +} & = \frac{1 } {\ sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\ sqrt{2 } } (h \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\ sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 + \ket{1 + \ket{0 } } } } ) = \ket{1 } 。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="6b9cc-127">& end{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-127">\end{align}</span></span>
$$

<span data-ttu-id="6b9cc-128">Oracle $O を定義する場合は、次のように、 $ 任意の状態 $ \ket { \ psi } $ on $n + m $ qubits を書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="6b9cc-129">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-129">$$ \begin{align}</span></span>
<span data-ttu-id="6b9cc-130">\ket { \ psi } & = \ sum_ {x \ in {0, \\ 1 \\ } ^ n, y \ in \\ {0, 1 \\ } ^ m- } alpha (x, y) } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="6b9cc-131">& end{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-131">\end{align}</span></span>
$$

<span data-ttu-id="6b9cc-132">ここで、$-alpha: \\ {0, 1 \\ } ^ n \\ /times {0, 1} ^ \\ \mathbb{C } $ は、状態 $ \ket \ psi $ の係数を表し { } ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="6b9cc-133">したがって</span><span class="sxs-lookup"><span data-stu-id="6b9cc-133">Thus,</span></span>

<span data-ttu-id="6b9cc-134">$ $ & begin{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-134">$$ \begin{align}</span></span>
<span data-ttu-id="6b9cc-135">O \ket { \ psi } & = O \ sum_ {x \ in \\ {0, 1 \\ } ^ n, y \ \\ {0, 1 \\ } ^ m } \ alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \ \\ {0, 1 \\ } ^ n、y \ \\ {0, 1 \\ } ^ m- } alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \ in {0, 1} \\ \\ ^ n, y \ in {0, 1} ^ \\ m/ \\ } alpha (x, y) \ket{x } \ket{y/oplus f (x)}。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="6b9cc-136">& end{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="6b9cc-137">フェーズ oracles</span><span class="sxs-lookup"><span data-stu-id="6b9cc-137">Phase oracles</span></span>
<span data-ttu-id="6b9cc-138">または、 $ $ $O への入力に基づいて_フェーズ_を適用して、$f を oracle $O にエンコードすることもでき $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="6b9cc-139">たとえば、$ $ & $O 定義します。 $}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="6b9cc-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="6b9cc-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="6b9cc-141">& end{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-141">\end{align}</span></span>
<span data-ttu-id="6b9cc-142">$ $ 計算された oracle が、最初にコンピューティングベースの状態 $ \ket{x $ で登録に対して動作する場合 } 、このフェーズはグローバルフェーズであるため、監視できません。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="6b9cc-143">ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="6b9cc-144">たとえば、 $ 1 つの-qubit 関数 $f に対して、フェーズ orcale $O _f を考えてみ $ ます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="6b9cc-145">次に、$ $ > begin{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="6b9cc-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\ sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\ sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\ sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="6b9cc-147">& end{align}</span><span class="sxs-lookup"><span data-stu-id="6b9cc-147">\end{align}</span></span>
$$

<span data-ttu-id="6b9cc-148">一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="6b9cc-149">Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="6b9cc-150">たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm)は2番目の方法で実装された oracle に依存しています。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="6b9cc-151">詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b9cc-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
