---
title: 量子回路
description: クォンタム回路図を使用して単純で複雑なクォンタム操作を視覚的に表現する方法について説明します。
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: 745f0570bf62c5d98c2896cdc893ec385abd7115
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630405"
---
# <a name="quantum-circuits"></a>クォンタム回線
ここでは、ユニタリ変換 $ \ text { cnot} _ {01 } (H \otimes 1) $ という点を考慮してください。
このゲートシーケンスは、下回っありの2つのビット状態を作成するので、クォンタムコンピューティングにとって基本的な意味を持ちます。

$ $ \mathrm{CNOT}_{01 } (H \otimes 1) \ket{00 } = \frac{1 } {\ sqrt{2 } } \ left (\ket{00 } + \ket{11 } /right), $ $

このような複雑さを持つ操作は、クォンタムアルゴリズムとクォンタムエラー修正で広く普及しています。そのため、*量子回線図*と呼ばれるシンプルな方法で視覚化を行うことができます。
この下回っありのクォンタム状態を準備するためのサーキット図は次のとおりです。

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![下回っありの2つの状態のサーキット図](~/media/1.svg)

## <a name="quantum-circuit-diagram-conventions"></a>クォンタム回路図の表記規則
このクォンタム操作のビジュアル言語は、クォンタム回線を表現するための規則を理解した後に、同等のマトリックスを書き出すよりも簡単に消化できます。
以下の規則を確認します。

回路図では、各実線は qubit レジスタを表しています。
慣例として、一番上の行は qubit レジスタ $0 であり、 $ 余りには順番にラベルが付けられています。 上の例の回線は、2つの qubits (または1つの qubits で構成される2つのレジスタ) で動作しているように表されています。
1つ以上の qubit レジスタに作用するゲートは、ボックスとして示されます。
たとえば、シンボルは

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![シングル qubit レジスタで動作する Hadamard 操作のシンボル](~/media/2.svg)

は、シングル qubit レジスタに対して動作する[Hadamard](xref:microsoft.quantum.intrinsic.h)操作です。

クォンタムゲートは、ゲートが最初に qubits に適用されたときの左端のゲートと共に、時系列順に並べられます。
つまり、回線をクォンタム状態のままにしている場合、ワイヤは図の各ゲートを通じて、左から右にクォンタムの状態を取り込みます。
つまり、 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![左から右に適用されているクォンタムゲートの図](~/media/3.svg)

は、$CBA のユニタリ行列です $ 。
行列乗算は反対の規則に従います。最初に右端の行列が適用されます。 ただし、量子回線図では、最初に一番左のゲートが適用されます。
この違いによって混乱が生じる可能性があるため、線形代数の図と量子回線の図の大きな違いに注意することが重要です。

## <a name="inputs-and-outputs-of-quantum-circuits"></a>クォンタム回線の入力と出力
前に示したすべての例では、クォンタムゲートから送信されたワイヤの数とまったく同じ数 (qubits) の入力がクォンタムゲートに含まれていました。
最初は、クォンタム回線が一般に入力よりも多くの出力を持つことができると考えられるかもしれません。
ただし、これは不可能です。これは、すべてのクォンタム操作、測定値の保存は、すべての処理が行われるためです。
同じ数の出力が入力として含まれていなかった場合は、元に戻すことはできず、そのため、不一致になります。
このため、サーキット図に描画されるすべてのボックスには、それを終了するときとまったく同じ数のワイヤを入力する必要があります。

マルチ qubit 回路図は、単 qubit と同様の規則に従います。
明確な例として、2つの qubit の $B を定義して、$ $ (H S \otimes X) $ と同等の回線を表現することができます。

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![2つの qubit のユニタリ操作のサーキットダイアグラム](~/media/4.svg)

また、 $ 回線が使用されているコンテキストに応じて、2 1-qubit レジスタではなく、1つの2つの qubit レジスタに対するアクションを持つ $B を表示することもできます。 このような抽象回路図の中で最も役に立つのは、複雑なクォンタムアルゴリズムを高いレベルで記述し、基本ゲートにコンパイルする必要がない場合などです。
これは、アルゴリズム内の各サブルーチンがどのように機能するかについてすべての詳細を理解しなくても、大規模なクォンタムアルゴリズムのデータフローに関する直感を取得できることを意味します。

## <a name="controlled-gates"></a>制御ゲート
マルチ qubit クォンタム回路図に組み込まれているもう1つのコンストラクトは制御です。
クォンタム片制御ゲートのアクション。 $-ラムダ (G) $ が示されています。ここでは、1つの qubit の値が $G のアプリケーションを制御し $ ています。この例では、製品状態入力 $-ラムダ (g) (\ alpha \ket{0 } + \ket{1 } ) \ket/ { psi } =-alpha \ket{0 } \ket { } } \ket { }
つまり、制御されたゲートが $ \ psi を含むレジスタに $G 適用されるのは、 $ $ コントロールの qubit が値 $1 を受け取る場合のみです $ 。
一般に、このような制御された操作を回路図に記述します。

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![単一制御ゲートのサーキットダイアグラム](~/media/5.svg)

ここで、黒い円はゲートが制御されるクォンタムビットを表し、垂直方向のワイヤは、コントロール qubit が値 $1 を受け取るときに適用されるユニタリを表し $ ます。
$G = X および $G = Z の特殊なケースでは、 $ $ ゲートの制御されたバージョンを記述するために次の表記を導入します (制御された X ゲートが[$CNOT $ ゲート](xref:microsoft.quantum.intrinsic.cnot)であることに注意してください)。

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![特別なケースの制御ゲートの回路図](~/media/6.svg)

Q # は、操作の制御されたバージョンを自動的に生成するメソッドを提供します。これにより、プログラマは、これらの操作を手作業でコードに渡す必要がなくなります。 この例を次に示します。

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>測定演算子
回路図で視覚化する残りの操作は、測定値です。
測定は、qubit レジスタを受け取り、それを測定し、その結果を古典的な情報として出力します。
測定値はメーター記号で示され、常に入力として qubit レジスタ (実線で示されます) を受け取り、古典的な情報を出力します (2 本の線で示されます)。
具体的には、このようなサブサーキットは次のようになります。

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![測定演算を表すシンボル](~/media/7.svg)

Q # この目的のために[メジャー演算子](xref:microsoft.quantum.intrinsic.measure)を実装します。
詳細については、[測定に関するセクション](xref:microsoft.quantum.libraries.standard.prelude#measurements)を参照してください。

同様に、サブサーキット

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![制御された操作を表す回路図](~/media/8.svg)

クラシックデプロイ制御ゲートを提供します。 $G は、$1 の古典的な制御ビットで条件付きで適用され $ $ ます。

## <a name="teleportation-circuit-diagram"></a>受付回路の図
クォンタムは、これらのコンポーネントを示す最良のクォンタムアルゴリズムであると考えられます。
対応する[クォンタム kata](xref:microsoft.quantum.overview.katas)クォンタムを使用したハンズオンについては、結び付き使用と測定を使用して、quantum コンピューター内 (または quantum ネットワーク内の離れたコンピューター間) でデータを移動する方法について学ぶことができます。
興味深いことに、実際には、qubit の値が何であるかを把握していなくても、特定の qubit の値を1つの qubit から別の値に移動することができます。
これは、プロトコルが量子力学法に従って動作するために必要です。
次に、クォンタムの例を示します。また、クォンタム回線の読み取り方法を示すために、回路の注釈付きバージョンも提供します。

<!--- ![](.\media\tp2.svg){ width=50% } --->
![Quantum の受付回線](~/media/tp2.svg)
