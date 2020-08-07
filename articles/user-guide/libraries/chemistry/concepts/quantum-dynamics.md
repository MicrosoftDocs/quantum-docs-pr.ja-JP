---
title: クォンタム Dynamics
description: Quantum dynamics とクラシック dynamics の類似点と相違点について説明します。
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: e63ec497f2a7747e172d5fbdc249fe4064c482b6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869496"
---
# <a name="quantum-dynamics"></a>クォンタム Dynamics

多くの場合、量子力学は、クォンタムの初期状態 $ \ket{\psi (0)} $ が時間の経過と共にどのように変化するかを理解することを目指しています (Dirac 表記の詳細については、「クォンタムコンピューティングに関する[概念ドキュメント](xref:microsoft.quantum.concepts.dirac)」を参照してください)。
具体的には、この初期状態では、クォンタム状態、進化時間、およびクォンタム dynamical システムの仕様により、クォンタム状態 $ \ket{\psi (t)} $ が検索されます。
量子力学の説明に進む前に、前の手順を実行して古典的な dynamics について考えることをお勧めします。これは、量子力学が従来の dynamics とどのように異なるのかについての洞察を提供するためです。

クラシック dynamics では、ここでは、$F (x, t) = ma = m& frac {\ dd ^ 2} {\ dd t ^ 2} {x} (t) $ に従ってパーティクルの位置が変化することを示します。ここで、$F (x, t) $ は force、$m $ は質量、$a $ は加速します。
次に、初期位置 $x (0) $、進化時間 $t $、およびパーティクルに作用するフォースの説明を指定した後、$x (t) $ のニュートンの式で指定された差分式を解決して、$x (t) $ を検索できます。
この方法で強制を指定することは、少しの問題です。
そのため、システムのエネルギーに関しては、その力が、$-\ partial_x V (x, t) = m \frac{\dd ^ 2} {\ dd t ^ 2} {x} (t) $ という意味で表現されることがよくあります。
このため、パーティクルの場合、システムのダイナミクスは、潜在的エネルギー関数、パーティクル質量、および進化時間によってのみ指定されます。

多くの場合、より幅広い言語が、$F = ma $ を超える古典的なダイナミクスに導入されています。
定式化の1つは、Hamiltonian 力学です。
Hamiltonian 力学では、システムの総エネルギーおよび (一般化された) 位置と momenta は、任意のクラシックオブジェクトの動きを示すために必要なすべての情報を提供します。
具体的には、$f (x, p, t) $ は、システムの $ と momenta $p $ $x の一般化された位置のいくつかの関数であり、$H (x, p, t) $ を Hamiltonian 関数にします。
たとえば、$f (x, p, t) = x (t) $ および $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $ を取得した場合、上記の例の Newtonian dynamics が復旧されます。
一般性では、\begin{align} \frac{d}{dt} f &= \ partial_t f-(\ partial_x H \ partial_p f + \ partial_p H \ partial_x f) \\ \\ & \ defeq \ partial_t f + \\ {f, h \\ } です。
ここ $ \\ {f, H \\ } $ は、\end{align} を定義するときに中心的な役割を果たすことがあるため、随所は[ポアソンかっこ](https://en.wikipedia.org/wiki/Poisson_bracket)と呼ばれ、クラシック dynamics ではが表示されます。

クォンタム dynamics は、まったく同じ言語で記述できます。
Hamiltonian (または総エネルギー) によって、すべての閉鎖された量子システムの力学が完全に指定されます。
ただし、2つの理論の間には大きな違いがいくつかあります。
古典機構では $x $ と $p $ は数字だけであり、量子力学ではありません。
実際には、commute のようなものではありません。 \n e px $ $xp ます。

これらの非通勤オブジェクトを記述するための適切な数学的概念は演算子です。これは $x $ と $p $ が、マトリックスの概念と一致する個別の値セットだけを受け取ることができる場合に使用します。
したがって、わかりやすくするために、quantum システムは有限で、[ベクターとマトリックス](xref:microsoft.quantum.concepts.vectors)を使用して記述できると想定しています。
さらに、これらのマトリックスを Hermitian する必要があります (つまり、マトリックスの共役転置が元のマトリックスと同じであることを意味します)。
これにより、マトリックスの固有値が実際の値であることが保証されます。架空の数値が返されないというような数量を測定する場合に、この条件が適用されることを保証します。

クォンタムの位置と勢いのアナログを演算子で置き換える必要があるのと同様に、Hamiltonian 関数は演算子でも同様に置き換える必要があります。
たとえば、フリースペースのパーティクルの場合、$H (x, p) = p ^ 2/2m $ を使用します。量子力学では、Hamiltonian operator $ \hat{H} $ は $ \hat{H} = \hat{p} ^ 2/2m $ で、$ \hat{p} $ は勢い演算子です。
この観点からは、クラシックから quantum dynamics に移行するときに、通常の dynamics で使用される変数を演算子で置き換えるだけで済みます。
通常の古典 Hamiltonian を quantum 言語に変換することによって Hamiltonian 演算子を構築した後、任意のクォンタムの機械的な数量 (つまり、クォンタム機械的演算子) のダイナミクスを、\begin{align} \frac{d}{dt} \hat{f} = \ partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} で表すことができます。ここで、$ [f, H] = fH-Hf $ は commutator と呼ば
この式は、前に示した古典式とよく似ています。これは、ポワソンかっこ $ \\ {f, H \\ } $ が $f $ と $H $ の間の commutator に置き換えられる点です。
このプロセスを使用して、古典的な Hamiltonian を取得し、それを使用して quantum Hamiltonian を見つけることが、クォンタムの用語では正規の量子化と呼ばれています。

最も関心があるのは $ $f 演算子  これに対する答えは、解決する必要がある問題によって異なります。
多くの場合、最も役に立つ数量は、クォンタム状態オペレーターです。これは、前述の概念説明のドキュメントで説明したように、dynamics について学習するすべてのものを抽出するために使用できます。
この操作を行った後 (また、一方が純粋な状態の場合の結果を簡単にするため)、クォンタム状態の Schrödinger 式は \begin{align} i \ partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)} となります。
\end{align}

この式は、前述のほど直感的ではないかもしれませんが、おそらく、クォンタムまたはクラシックコンピューターでクォンタム dynamics をシミュレートする方法を理解するための最も単純な式です。
これは、差分式のソリューションを次の形式で表すことができるためです ($t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)} で Hamiltonian が定数である場合に使用します。
\end{align} ここ $e ^ {-iHt} $ は、ユニタリ行列です。
これは、quantum コンピューターはどのような場合でも、実行できるように設計できるクォンタム回線が存在することを意味します。
この操作では、クォンタムの時間を進化させる操作を実装するために、クォンタムの回線を検索します $e ^ {-iHt} $ は、クォンタムのシミュレーションと呼ばれることがよくあります。また、特に dynamical クォンタムのシミュレーションでもあります。
