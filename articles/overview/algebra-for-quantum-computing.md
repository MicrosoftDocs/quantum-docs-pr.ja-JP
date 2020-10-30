---
title: 量子コンピューティングの線形代数
description: 量子コンピューティングを理解するために必要な線形代数の基本概念について説明します
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3e6700acc09adf9e2e771f6289c73ad51aa2cb90
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692248"
---
# <a name="linear-algebra-for-quantum-computing"></a>量子コンピューティングの線形代数

線形代数は、量子コンピューティングの数式記法です。 量子プログラムの実装や記述にその知識は必要ありませんが、量子ビットの状態や量子演算を記述するため、および量子コンピューターが一連の命令に応じて実行する処理を予測するために広く使用されています。

[量子物理学の基本概念](xref:microsoft.quantum.overview.understanding)をよくわかっていることが量子コンピューティングの理解に役立つ可能性があるのと同様に、線形代数の基礎知識が、量子アルゴリズムの仕組みを理解するうえで役立つと考えられます。 少なくとも、 **ベクトル** と **行列乗算** について理解しておくことをお勧めします。 これらの代数の概念についての知識を新たにする必要がある場合は、次のチュートリアルに基本的な説明があります。

- [線形代数に関する Jupyter Notebook のチュートリアル](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [複雑な算術演算に関する Jupyter Notebook のチュートリアル](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [量子計算の線形代数](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [線形代数の基礎](https://www.math.ubc.ca/~carrell/NB.pdf)
- [量子計算の概要](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>量子コンピューティングのベクトルと行列

トピック「[量子コンピューティングについて](xref:microsoft.quantum.overview.understanding)」では、量子ビットは 1 か 0 の状態または重ね合わせ状態、もしくはこの両方の状態になることができると説明しました。 線形代数を使用すると、量子ビットの状態はベクトルとして記述され、1 列 **行列** $\begin{bmatrix} a \\\\  b \end{bmatrix}$ で表されます。 これは、 **量子状態ベクトル** とも呼ばれ、$|a|^2 + |b|^2 = 1$ の要件を満たす必要があります。  

行列の要素は、量子ビットがどちらかの方向に収縮する確率を表しています。$|a|^2$ は 0 に収縮する確率、$|b|^2$ は 1 に収縮する確率です。 次の行列はすべて、有効な量子状態ベクトルを表しています。

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}、\begin{bmatrix} 0 \\\\  1 \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}、\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}、\text{ および }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}$$

[量子コンピューターと量子シミュレーター](xref:microsoft.quantum.overview.simulators)では、量子演算を使用して量子ビットの状態を変更することも説明しました。  量子演算は行列で表すこともできます。 量子演算が量子ビットに適用される場合、それらを表す 2 つの行列が乗算され、結果として得られる答えは演算後の量子ビットの新しい状態を表します。  

次に、行列乗算で表される 2 つの一般的な量子演算を示します。


[`X` 演算](xref:Microsoft.Quantum.Intrinsic.X)は次のパウリ行列 $X$ で表されます。

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix}$$
    
これは、たとえば次のように、量子ビットの状態を 0 から 1 (またはその逆) に反転するために使用されます。

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}$$

['H' 演算](xref:Microsoft.Quantum.Intrinsic.H)は、次のようにアダマール変換 $H$ で表されます。

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}$$

 この場合、次に示すように、量子ビットが、どちらの方向にも同等の確率で収縮される重ね合わせ状態になります。

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}$$

量子演算を表す行列には 1 つの要件があります。 **ユニタリ** 行列でなければならないということです。 行列がユニタリとなるのは、行列の **逆** が行列の **共役転置** と等しい場合です。

## <a name="representing-two-qubit-states"></a>2 つの量子ビットの状態の表現

上記の例では、1 つの量子ビットの状態が 1 列行列 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ を使用して記述され、量子ビットに対する演算の適用は 2 つの行列を乗算して記述されました。 しかし、量子コンピューターでは複数の量子ビットが使用されるため、2 つのビットの結合された状態はどのように記述するのでしょうか。 

各量子ビットはベクトル空間であるため、単なる乗算はできないことに注意してください。 代わりに、 **テンソル積** を使用します。これは、個々のベクトル空間から新しいベクトル空間を作成する関連演算であり、$\otimes$ 記号で表されます。 たとえば、2 つの量子ビットの状態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ と $\begin{bmatrix} c \\\\  d \end{bmatrix}$ のテンソル積を計算します。

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix} $$

結果は 4 次元行列になり、各要素は確率を表します。 たとえば、$ac$ は 0 と 0 に収縮する 2 つの量子ビットの確率であり、$ad$ は 0 と 1 の確率、というようになります。 

1 つの量子ビットの状態 $\begin{bmatrix} a \\\\  b \end{bmatrix}$ が量子状態を表すために要件 $|a|^2 + |b|^2 = 1$ を満たさなければならないのと同様に、2 つの量子状態 $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ は要件 $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$ を満たす必要があります。

## <a name="summary"></a>まとめ

線形代数は、量子コンピューティングと量子物理学を記述するための標準の数式記法です。 Microsoft Quantum 開発キットに含まれている[ライブラリ](xref:microsoft.quantum.libraries)を利用すると、基になる数学についての知識がなくても高度な量子アルゴリズムを実行できますが、基本を理解しておくことで素早くスタートを切ることができ、確固とした基盤を築くのに役立ちます。

## <a name="next-steps"></a>次のステップ

[QDK をインストールする](xref:microsoft.quantum.install)
