---
title: 量子オラクル
description: 別のアルゴリズムへの入力として使用される、クォンタム oracles、ブラックボックス操作の操作方法と定義方法について説明します。
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904929"
---
# <a name="quantum-oracles"></a><span data-ttu-id="0c368-103">Quantum Oracles</span><span class="sxs-lookup"><span data-stu-id="0c368-103">Quantum Oracles</span></span>

<span data-ttu-id="0c368-104">Oracle $O $ は、別のアルゴリズムへの入力として使用される "ブラックボックス" 操作です。</span><span class="sxs-lookup"><span data-stu-id="0c368-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="0c368-105">多くの場合、このような操作は従来の関数 $f を使用して定義されています: \\{0, 1\\} ^ n \ \\{0, 1\\} ^ m $ に $n $ bit バイナリ入力を取得し、$m $ bit バイナリ出力を生成します。</span><span class="sxs-lookup"><span data-stu-id="0c368-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="0c368-106">これを行うには、特定のバイナリ入力 $x = (x_{0}、x_{1}、\ ドット、x_ {n-1}) $ を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="0c368-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="0c368-107">Qubit 状態には、$ \ket{\vec{x}} = \ket{x_{0}}/otimes \ket{x_{1}}/otimes/cドット/otimes \ket{x_ {n-1}} $ というラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="0c368-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="0c368-108">最初に $O $ を定義しようとします。これにより、$O \ket{x} = \ket{f (x)} $ になりますが、これにはいくつかの問題があります。</span><span class="sxs-lookup"><span data-stu-id="0c368-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="0c368-109">まず、$ $f には、入力と出力のサイズが異なる場合があります ($n \n e m $)。 $O $ を適用すると、レジスタの qubits の数が変更されます。</span><span class="sxs-lookup"><span data-stu-id="0c368-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="0c368-110">2番目に、$n = m $ の場合でも、関数は反転できるではない可能性があります。たとえば、一部の $x \n e y $ の $f (x) = f (y) $ の場合、$O \ket{x} = O\ket {y} $、$O ^ \ ダガー O\ket {x} \n e O ^、ダガー O\ket {y} $。</span><span class="sxs-lookup"><span data-stu-id="0c368-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="0c368-111">つまり、adjoint 操作 $O ^ oracles $ に作成することはできず、そのためには adjoint が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c368-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="0c368-112">計算ベースの状態に影響を与える oracle の定義</span><span class="sxs-lookup"><span data-stu-id="0c368-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="0c368-113">回答を保持する $m $ qubits の2番目のレジスタを導入することで、両方の問題に対処できます。</span><span class="sxs-lookup"><span data-stu-id="0c368-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="0c368-114">次に、すべての計算ベースの状態に対して、oracle の効果を定義します。すべての $x \ \\{0, 1\\} ^ n $ と $y \ \\{0, 1\\} ^ m $,</span><span class="sxs-lookup"><span data-stu-id="0c368-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="0c368-115">$ $ \begin{align} O (\ket{x}/otimes \ket{y}) = \ket{x} \ otimes \ket{y \ oplus f (x)}。</span><span class="sxs-lookup"><span data-stu-id="0c368-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="0c368-116">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0c368-116">\end{align} $$</span></span>

<span data-ttu-id="0c368-117">ここで $O = O ^ \ ダガー $ を構築によってしました。したがって、上記の問題の両方を解決しました。</span><span class="sxs-lookup"><span data-stu-id="0c368-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="0c368-118">$O = O ^ {-dagger} $ であることを確認するには、$O ^ 2 = \ $a の後に $ {+ b を加え、b = a $ a all $a (b) \{0, 1\}$ であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0c368-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="0c368-119">結果として、$O \ket{x} \ket{y と f (x)} = \ket{x} \ket{y と f (x) \ oplus f (x)} = \ket{x} \ket{y} $ のようになります。</span><span class="sxs-lookup"><span data-stu-id="0c368-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="0c368-120">重要な点として、各計算基準の状態に対して oracle を定義すると、$ \ket{x}\ket{y} $ は、他のすべての状態に対して $ act $O 方法も定義します。</span><span class="sxs-lookup"><span data-stu-id="0c368-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="0c368-121">これは、すべてのクォンタム操作と同様、$ $O 処理される状態で線形であるという事実からすぐに続きます。</span><span class="sxs-lookup"><span data-stu-id="0c368-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="0c368-122">Hadamard 操作を考えてみます。たとえば、$H \ket{0} = \ket{+} $ および $H \ket{1} = \ket{-}$ によって定義されているとします。</span><span class="sxs-lookup"><span data-stu-id="0c368-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="0c368-123">$ \Ket{+} $ に対して $ act を $H 方法を知りたい場合は、$ is linear $H を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0c368-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="0c368-124">$ $ \begin{align} H\ket {+} & = \ frac{1}{\ sqrt{2}} H (\ket{0} + \ket{1}) = \ frac{1}{\ sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \ frac{1}{\ sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}です。</span><span class="sxs-lookup"><span data-stu-id="0c368-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="0c368-125">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0c368-125">\end{align} $$</span></span>

<span data-ttu-id="0c368-126">Oracle $O $ を定義する場合は、次のように、任意の状態 $ \ket{\psi} $ on $n + m $ qubits を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0c368-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="0c368-127">$ $ \begin{align} \ket{\psi} & = \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ alpha (x, y) \ket{x} \ket{y} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0c368-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="0c368-128">$-alpha: \\{0, 1\\} ^ n 回 \\{0, 1\\} ^ m-to \mathbb{C} $ は、状態 $ \ket{\psi} $ の係数を表します。</span><span class="sxs-lookup"><span data-stu-id="0c368-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="0c368-129">したがって</span><span class="sxs-lookup"><span data-stu-id="0c368-129">Thus,</span></span>

<span data-ttu-id="0c368-130">$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ アルファ (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \ \\{0, 1\\} ^ n, y \ \\{0, 1\\} ^ m} \ alpha (x, y) \ket{x} \ket{y/oplus f (x)}。</span><span class="sxs-lookup"><span data-stu-id="0c368-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="0c368-131">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0c368-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="0c368-132">フェーズ oracles</span><span class="sxs-lookup"><span data-stu-id="0c368-132">Phase oracles</span></span>
<span data-ttu-id="0c368-133">または、$O $ への入力に基づいて_フェーズ_を適用して、$f $ を oracle $O $ にエンコードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="0c368-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="0c368-134">たとえば、$ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}. という $O $ を定義する場合があります。</span><span class="sxs-lookup"><span data-stu-id="0c368-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="0c368-135">\end{align} $ $ 計算ベースの状態が "$ \ket{x} $" である場合、このフェーズはグローバルフェーズであるため、監視できません。</span><span class="sxs-lookup"><span data-stu-id="0c368-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="0c368-136">ただし、このような oracle は、法則または制御された操作として適用される場合、非常に強力なリソースになります。</span><span class="sxs-lookup"><span data-stu-id="0c368-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="0c368-137">たとえば、$ という1つの単一の qubit $f 関数に対して _f $ $O フェーズ orcale を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="0c368-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="0c368-138">次に、$ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\ sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})//sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\ sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}。</span><span class="sxs-lookup"><span data-stu-id="0c368-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="0c368-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="0c368-139">\end{align} $$</span></span>

<span data-ttu-id="0c368-140">一般的には、oracles の両方のビューを拡大して、1ビットだけではなく実数を返す古典関数を表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0c368-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="0c368-141">Oracle を実装する最適な方法を選択することは、特定のアルゴリズム内でこの oracle がどのように使用されるかに大きく依存します。</span><span class="sxs-lookup"><span data-stu-id="0c368-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="0c368-142">たとえば、 [Deutsch アルゴリズム](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm)は最初の方法で実装された oracle に依存しますが、 [Grover のアルゴリズム](https://en.wikipedia.org/wiki/Grover's_algorithm)は2番目の方法で実装された oracle に依存しています。</span><span class="sxs-lookup"><span data-stu-id="0c368-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="0c368-143">詳細については、 [Gilyén *et*1711.00465](https://arxiv.org/abs/1711.00465)に関する説明をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0c368-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
