---
title: Qubit |Microsoft Docs
description: Qubit
author: QuantumWriter
uid: microsoft.quantum.concepts.qubit
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f29319c3ec19fecc45f5a9f7c16061b9aa9f71ec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183643"
---
# <a name="the-qubit"></a>Qubit

従来のコンピューティングにおける情報の基本的なオブジェクトであるのと同様に、 [*qubits*](https://en.wikipedia.org/wiki/Qubit) (クォンタムビット) は、クォンタムコンピューティングにおける情報の基本的なオブジェクトです。  このような対応を理解するために、1つの qubit という最も単純な例を見てみましょう。

## <a name="representing-a-qubit"></a>Qubit を表す

ビットまたはバイナリ数字は $0 $ または $1 $ のいずれかの値を持つことができますが、qubit は、これらの値、または $0 $ と $1 $ のクォンタム法則のいずれかの値を持つことができます。

1つの qubit の状態は、2次元の列ベクトル (単位基準) によって記述できます。つまり、そのエントリの大きさを示す二乗値は、$1 $ に合計する必要があります。 このベクターは、クォンタム状態ベクターと呼ばれ、1つのビットがバイナリ変数の状態を説明するために必要なすべての情報を保持するのと同じように、1つのビットを表すために必要なすべての情報を保持します。

標準 $1 $ を使用した実数または複素数の2次元列ベクトルは、qubit によって保持されている可能性のあるクォンタム状態を表します。 したがって、$ \begin{bmatrix}-alpha \\\\ \ ベータ \end{bmatrix} $ は、$ | \ alpha | ^ 2 + | \ beta | ^ 2 = $1 を満たす複雑な数値の場合、qubit 状態を表します。 Qubits を表す有効なクォンタム状態ベクトルの例を次に示します。

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}、\begin{bmatrix} 0 \\\\ 1 \end{bmatrix}、\begin{bmatrix}/frac{1}{\ sqrt{2}} \\\\/frac{1}{\ sqrt{2}} \end{bmatrix}、\begin{bmatrix}/frac{1}{\ sqrt{2}} \\\\/frac{-1}{\ sqrt{2}} \end{bmatrix}、\ text{および} \begin{bmatrix}/frac{1}{\ sqrt{2}} \\\\ \frac{i}{\sqrt{2}} \ end{bmatrix}. $ $

クォンタム状態ベクトル $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ および $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ は特別な役割を持ちます。 これらの2つのベクトルは、qubit の状態を表すベクター空間の基礎となります。 これは、すべてのクォンタム状態ベクトルをこれらの基礎ベクトルの合計として書き込むことができることを意味します。 具体的には、vector $ \begin{bmatrix} x \\\\ y \end{bmatrix} $ は $x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ として書き込むことができます。 これらのベクトルの回転は、qubit の完全に有効な基準として機能しますが、そのためには、*コンピューティングベース*を呼び出すことによって、この方法を選択します。

この2つのクォンタム状態は、従来のビットの2つの状態 ($0 $ と $1 $) に対応しています。 標準的な規則は、

$ $ 0 \ http-equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}、\qquad 1 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}、$ $

反対の選択肢も同様に実行できます。 このため、1つの1つの qubit クォンタム状態ベクトルの無限数が不足しています。その他のすべてのクォンタム状態はありません。

## <a name="measuring-a-qubit"></a>Qubit の測定

ここで、qubit を表す方法を理解したところで、[*測定*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics)の概念について説明することによって、これらの状態が表すものの直感を取得できます。 測定は、qubit で "見ている" という非公式の概念に対応しています。これは、クォンタムの状態を、次の2つの従来の状態 ($ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ または $ \begin{bmatrix} 0 \\\\ 1 \ end{) のいずれかに直ちに縮小します。bmatrix} $。 クォンタム状態 vector $ \begin{bmatrix} \ alpha \\\\ \ ベータ \end{bmatrix} $ によって指定された qubit が測定されると、確率が $ |-alpha | ^ 2 $、結果が $1 $、確率が $ | \ beta | ^ 2 $ の結果 $0 $ が得られます。 結果 $0 $ の場合、qubit の新しい状態は $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $;結果 $1 $ の状態は、$ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ です。 正規化条件 $ | \ alpha | ^ 2 + | \ beta | ^ 2 = $1 のため、これらの確率は最大 $1 $ になります。

測定のプロパティは、クォンタム状態ベクターの全体的な符号が無関係であることも意味します。 ベクターを否定することは、$ \ alpha \rightarrow-\ alpha $ と $ \ beta \rightarrow-\ beta $ と同じです。 $0 $ と $1 $ を測定する確率は、用語の大きさの二乗に依存しているため、このような記号を挿入しても確率は変わりません。 このようなフェーズは、一般に[``*グローバルなフェーズ*' '](https://en.wikipedia.org/wiki/Phase_factor)と呼ばれ、より一般的な形式は、$ pm $1 だけではなく、^ {i \phi} $ $e の形式になります。

測定の最後の重要なプロパティは、必ずしもすべてのクォンタム状態ベクトルが破損するとは限りません。 状態が $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ (クラシック状態 $0 $ に対応) の場合、この状態を測定すると、常に $0 $ という結果が生成され、クォンタムの状態は変更されません。 この意味では、従来のビットのみ (つまり、$ \begin{bmatrix}1 \\\\ 0 \end{bmatrix} $ または $ \begin{bmatrix}0 \\\\ 1 \end{bmatrix} $) の場合、測定によってシステムが破壊されることはありません。 これは、従来のコンピューターで実行する場合と同様に、古典的なデータをレプリケートして、quantum のコンピューターで操作できることを意味します。 ただし、両方の状態の情報を一度に保存する機能は、クォンタムデータをむやみにコピーする機能であるクラシックデプロイとその他の robs コンピューターよりも大きくなります。 [](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Bloch 球を使用した Qubits と変換の視覚化

[*Bloch 球*](https://en.wikipedia.org/wiki/Bloch_sphere)表現を使用して、$ 3 $ D で qubits を示すこともできます。  Bloch 球は、シングル qubit のクォンタム状態 (2 次元の複合ベクター) を3次元の実際の値のベクトルとして記述する方法を提供します。  これは、シングル qubit の状態を視覚化して、マルチ qubit の状態を理解するうえで非常に重要な理由 (Bloch 球表現が壊れている場合) を開発できるため、重要です。  Bloch 球は次のように視覚化できます。

<!--- ![](.\media\bloch.svg){ width=50% } --->
![Bloch 球](~/media/concepts_bloch.png)

この図の矢印は、クォンタム状態ベクトルがポイントしている方向を示しています。矢印の各変換は、カーディナル軸の1つについての回転と考えることができます。
クォンタムの計算は、一連の回転として考えていますが、強力な直感であるため、この直感を使用してアルゴリズムを設計および記述するのは困難です。 Q # この問題を解決するには、そのような回転を記述する言語を提供します。

## <a name="single-qubit-operations"></a>シングル Qubit 操作

Quantum コンピューターでは、クォンタム状態ベクターのローテーションをエミュレートできる、一連の汎用クォンタムゲートを適用してデータを処理します。
この universality の概念は、universality の概念に似ています。これは、入力ビットのすべての変換を有限長回線を使用して実行できる場合に、ゲートセットがユニバーサルと見なされる従来の (つまり、古典的な) コンピューティングの概念に似ています。
クォンタムコンピューティングでは、qubit で実行できる有効な変換は、ユニタリの変換と測定です。
クォンタムの変換を反転させる必要があるため、 *adjoint 操作*または複雑な共役転置は、クォンタムの計算に非常に重要です。
Q # は、ゲートシーケンスを自動的に adjoint にコンパイルするメソッドを提供することによってこれを反映しています。これにより、多くの場合、プログラマがコード adjoint を手にする必要がなくなります。 この例を次に示します。

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Adj { // Auto-generate the adjoint of the operation
    H(qubit);
}
```

これは単純な例ですが (<xref:microsoft.quantum.intrinsic.h> 操作は自己完結型であるため)、より複雑な qubit 操作にとって、これがどのように貴重になるかを確認できます。
詳細については、「[操作と関数](xref:microsoft.quantum.techniques.opsandfunctions)」を参照してください。

クラシックコンピューターでは、1つのビットを1ビットにマップする関数は4つだけです。 これに対して、クォンタムコンピューターの1つの qubit には無限の数のユニタリ変換があります。 したがって、[*ゲート*](https://en.wikipedia.org/wiki/Quantum_logic_gate)と呼ばれるプリミティブなクォンタム操作の有限のセットでは、クォンタムコンピューティングで許可されている無限の一連のユニタリ変換を正確にレプリケートできません。 つまり、従来のコンピューティングとは異なり、クォンタムコンピューターでは、限られた数のゲートを使用して、可能なすべてのクォンタムプログラムを正確に実装することはできません。 そのため、コンピューターを使用することは、従来のコンピューターの場合と同じ意味では一般的ではありません。 結果として、一連のゲートがクォンタムコンピューティングのために*汎用*であると言うと、実際には、従来のコンピューティングの場合よりも若干弱いことを意味します。
Universality の場合、クォンタムコンピューターでは、有限の長さのゲートシーケンスを使用して、有限エラー内のすべてのユニタリ行列を*概算*する必要があります。
言い換えると、一連のゲートは、このセットからのゲートの積として、任意のユニタリ変換がほぼ書き込み可能である場合に、ユニバーサルゲートセットになります。 指定されたエラーが発生した場合は、ゲートセットから G_N $ $G _{1}、G_{2}、\ lドット、$ のゲートが存在する必要があります。

$ $ G_N G_ {N-1} \ cドット G_2 G_1。 $ $

マトリックス乗算の規則は、このシーケンスの最初のゲート演算を右から左に乗算することであるため、$G _N $ は実際にはクォンタム状態ベクターに適用される最後のものです。 より具体的に言うと、このようなゲートセットは、すべての誤差許容値 $/イプシロン > 0 $ が $G 存在する場合は、_N \ lドット G_1 $ と $U $ の $G 間の距離が $/イプシロン $ であることを意味します。 理想的には、$ poly $ のこの距離に至るために必要な $-イプシロン $ の $N 値は、$ 1/\ イプシロン $ を使用してをスケーリングする必要があります。

このようなユニバーサルゲートセットは実際にはどのように表示されるのでしょうか。  シングル qubit ゲートに最も単純なこのようなユニバーサルゲートセットは、2つのゲートのみで構成されます。 Hadamard gate $H $、いわゆる $T $-gate ($ \ pi/8 $ gate とも呼ばれます) です。

$ $ H = \ frac{1}{\ sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}、\qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ {i \ pi/4} \end{bmatrix}.
$$

ただし、クォンタムエラーの修正に関連する実際の理由により、より大きなゲートセットを検討する方が便利な場合があります。つまり、$H $ と $T $ を使用して生成できるゲートセットです。
クォンタムゲートは、Clifford ゲートと $T $-gate の2つのカテゴリに分類できます。
このような部分は、多くのクォンタムエラー修正スキームで、いわゆる Clifford ゲートが簡単に実装できるようにするために便利です。これは、操作の観点からはほとんどのリソースを必要とし、fault tolerantly を実装するには qubits が必要であるのに対し、非 Clifford ゲートはフォールトトレランスを必要とする場合、非常にコストがかかります。 [既定で](xref:microsoft.quantum.libraries.standard.prelude)は、次のようなシングル Qubit Clifford ゲートの標準セットが含まれています。

$ $ H = \ frac{1}{\ sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 &-1 \end{bmatrix}、\qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2、\qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4H、$ $

$ $ Y = \begin{bmatrix} 0 &-i \\\\ i & 0 \end{bmatrix} = T ^ 2HT ^ 4 HT ^ 6、\qquad Z = \begin{bmatrix}1 & 0\\\\ 0 &-1 \end{bmatrix} = T ^ 4。
$$

ここでは、操作 $X $、$Y $、$Z $ は、特に頻繁に使用され、creator Wolfgang p Li の後に[*p li 演算子*](https://en.wikipedia.org/wiki/Pauli_matrices)という名前が付けられています。
Clifford ゲート ($T $ gate) と共に、これらの操作を構成して、1つの qubit のすべてのユニタリ変換を概数化できます。

これらの操作、Bloch 球表現、Q # の実装の詳細については、「[組み込みの操作と関数](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions)」を参照してください。

これらのプリミティブからのユニタリ変換を構築する方法の例として、上記の Bloch 球に示されている3つの変換は、ゲートシーケンス $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}/mapHZH \begin{bmatrix} 1 に対応しています。\\\\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $。

前のは、スタックの論理レベルでの操作を記述するために最も一般的なプリミティブゲートを構成しています (この論理レベルはクォンタムアルゴリズムのレベルと考えられます)。多くの場合、アルゴリズムではあまり基本的でない操作を検討すると便利です。レベル。関数の説明レベルに近い操作などです。 幸いにも、Q # では、より高レベルの unitaries 実装するためのメソッドが用意されています。これにより、すべてのものを明示的に Clifford に分解して $ ゲート $T することなく、高レベルのアルゴリズムを実装できます。

最も単純なプリミティブは、1つの qubit 回転です。 通常、3つの単一 qubit 回転は、$R x $、$R y $、$R z $ と見なされます。 たとえば、$R 回転のアクションを視覚化するには、Bloch 球の $x $ 軸の方向に沿って右のつまみをポイントし、ベクトルを、$-シータ/2 $ ラジアンの角度を使用して手で回転させます。 この $2 $ のわかりにくい要因は、Bloch 球にプロットされるときに直交ベクトルが $ 180 ^-circ $ と区別されることですが、実際には実際には $ 90 ^-circ $ 度が幾何学的に分離されるという事実です。 対応するユニタリ行列は次のとおりです。

\ begin{align *} & R_z (\ シータ) = e ^ {-i\begin{bmatrix} {-\end{bmatrix}} = e ^ {-i \ シータ/2} & 0\\\\ 0 & e ^ {i \ シータ/2}, \\\\ & R_x (\ シータ) = e ^ {-i\ シータ x/2} = HR_z (\ シータ) H = \begin{bmatrix} \ cos (\シータ/2) &-i\ sin (\ シータ/2)\\\\-i\ sin (\ シータ/2) & \ cos (\ シータ/2) \end{bmatrix}、\\\\ & R_y (-シータ) = e ^ {-i-シータ Y/2} = SHR_z (\ シータ) HS ^ \ ダガー = \begin{bmatrix} \ cos (\ シータ/2) &-\ sin (\ シータ/2)\\\\/sin (\ シータ/2) & \ cos (\ シータ/2) \end{bmatrix}.& # {align*}

3つの回転を組み合わせて、3つの次元で任意の回転を実行できるのと同様に、Bloch 球表現では、すべての配列を3つの回転のシーケンスとして書き込むことができます。 具体的には、すべてのユニタリマトリックスに $U $-alpha, \ ベータ, \ ガンマ, \ デルタ $ が存在します。この場合、$U = e ^ {i\ alpha} R_x (\ ベータ) R_z (\ gamma) R_x (\ デルタ) $ となります。 したがって、$-シータ $ は任意の値を取ることができるので、$R z (-シータ) $ および $H $ は、ユニバーサルゲートセットを形成します。 このような理由により、クォンタムシミュレーションのアプリケーションにより、このような継続的ゲートは、特にクォンタムアルゴリズムのデザインレベルで、クォンタムの計算に不可欠です。 フォールトトレラントなハードウェア実装を実現するために、最終的には、これらの回転を厳密に近似する個別のゲートシーケンスにコンパイルされます。