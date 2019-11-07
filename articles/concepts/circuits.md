---
title: クォンタム回線 |Microsoft Docs
description: クォンタム回線
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210691"
---
# <a name="quantum-circuits"></a>クォンタム回線
ここでは、ユニタリ変換 $ \ text{CNOT} _{01}(hotimes 1) $ について考えてみます。
このゲートシーケンスは、下回っありの2つのビット状態を作成するので、クォンタムコンピューティングにとって基本的な意味を持ちます。

$ $ \mathrm{CNOT}_{01}(hotimes 1) \ket{00} = \ frac{1}{\ sqrt{2}} \ left (\ket{00} + \ket{11} 右)、$ $

このような複雑さを持つ操作は、クォンタムアルゴリズムとクォンタムエラー修正で広く普及しています。そのため、*量子回線図*と呼ばれるシンプルな方法で視覚化を行うことができます。
この下回っありのクォンタム状態を準備するためのサーキット図は次のとおりです。

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>クォンタム回路図の表記規則
このクォンタム操作のビジュアル言語は、クォンタム回線を表現するための規則を理解した後に、同等のマトリックスを書き出すよりも簡単に消化できます。
以下の規則を確認します。

回路図では、各実線は qubit レジスタを表しています。
慣例として、一番上の行は qubit レジスタ $0 $ で、残りは順番にラベル付けされます。 上の例の回線は、2つの qubits (または1つの qubits で構成される2つのレジスタ) で動作しているように表されています。
1つ以上の qubit レジスタに作用するゲートは、ボックスとして示されます。
たとえば、シンボルは

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

[Hadamard](xref:microsoft.quantum.primitive.h)ゲートは、シングル qubit レジスタに対して動作します。

クォンタムゲートは、ゲートが最初に qubits に適用されたときの左端のゲートと共に、時系列順に並べられます。
つまり、回線をクォンタム状態のままにしている場合、ワイヤは図の各ゲートを通じて、左から右にクォンタムの状態を取り込みます。
つまり、 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

は、$CBA が $ であることを示します。
行列乗算は反対の規則に従います。最初に右端の行列が適用されます。 ただし、量子回線図では、最初に一番左のゲートが適用されます。
この違いによって混乱が生じる可能性があるため、線形代数の図と量子回線の図の大きな違いに注意することが重要です。

## <a name="inputs-and-outputs-of-quantum-circuits"></a>クォンタム回線の入力と出力
前に示したすべての例では、クォンタムゲートから送信されたワイヤの数とまったく同じ数 (qubits) の入力がクォンタムゲートに含まれていました。
最初は、クォンタム回線が一般に入力よりも多くの出力を持つことができると考えられるかもしれません。
ただし、これは不可能です。これは、すべてのクォンタム操作、測定値の保存は、すべての処理が行われるためです。
同じ数の出力が入力として含まれていなかった場合は、元に戻すことはできず、そのため、不一致になります。
このため、サーキット図に描画されるすべてのボックスには、それを終了するときとまったく同じ数のワイヤを入力する必要があります。

マルチ qubit 回路図は、単 qubit と同様の規則に従います。
明確な例として、$ を $ (H & otimes X) $ に $B、2つの qubit のを定義し、次のように回線を表現することができます。

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

また、回線が使用されているコンテキストに応じて、2 1-qubit レジスタではなく、1つの2つの2つのビットレジスタに対するアクションを持つ $B $ を表示することもできます。 このような抽象回路図の中で最も役に立つのは、複雑なクォンタムアルゴリズムを高いレベルで記述し、基本ゲートにコンパイルする必要がない場合などです。
これは、アルゴリズム内の各サブルーチンがどのように機能するかについてすべての詳細を理解しなくても、大規模なクォンタムアルゴリズムのデータフローに関する直感を取得できることを意味します。

## <a name="controlled-gates"></a>制御ゲート
マルチ qubit クォンタム回路図に組み込まれているもう1つのコンストラクトは制御です。
クォンタム片制御ゲートのアクション ($-ラムダ (G) $ を示しています)。ここでは、1つの qubit の値が $G $ のアプリケーションを制御しています。この例では、製品の状態入力 $ & ラムダ (G) (\ alpha \ket{0} + \ \ket) の次の例を参照してください{1}) \ket{\psi} = \ alpha \ket{0} \ket{\psi} + \ \ket{1} G\ket {\ psi} $。
つまり、制御されたゲートが $ \ psi $ を含むレジスタに $ $G を適用するのは、コントロールの qubit が値 $1 $ を受け取る場合のみです。
一般に、このような制御された操作を回路図に記述します。

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

ここで、黒い円はゲートが制御されているクォンタムビットを表し、垂直方向のワイヤは、コントロール qubit が値 $1 $ を受け取るときに適用されるユニタリを表します。
$G = X $ および $G = Z $ の特殊なケースでは、ゲートの制御されたバージョンを記述するために次の表記が導入されます (制御された X ゲートは[$CNOT $ gate](xref:microsoft.quantum.primitive.cnot)であることに注意してください)。

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

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
![測定回路](~/media/concepts_7.png)

Q # この目的のために[メジャー演算子](xref:microsoft.quantum.primitive.measure)を実装します。
詳細については、[測定に関するセクション](xref:microsoft.quantum.libraries.standard.prelude#measurements)を参照してください。

同様に、サブサーキット

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

クラシックデプロイ制御ゲートを提供します。 $G $ は、$1 $ という従来の制御ビットで条件付きで適用されます。

## <a name="teleportation-circuit-diagram"></a>受付回路の図
[クォンタム](xref:microsoft.quantum.techniques.puttingittogether)は、これらのコンポーネントを示す最良のクォンタムアルゴリズムであると考えられます。
クォンタムコンピューター内 (または、quantum ネットワーク内の離れたコンピューター間でも) データを移動する方法としては、結び付き使用と測定を使用します。
興味深いことに、実際には、qubit の値が何であるかを把握していなくても、特定の qubit の値を1つの qubit から別の値に移動することができます。
これは、プロトコルが量子力学法に従って動作するために必要です。
次に、クォンタムの例を示します。また、クォンタム回線の読み取り方法を示すために、回路の注釈付きバージョンも提供します。

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)