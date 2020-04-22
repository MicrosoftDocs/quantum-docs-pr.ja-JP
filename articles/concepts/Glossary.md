---
title: 量子計算用語集
description: 量子コンピューティングで使用される一般的な用語、アクション、オブジェクトの用語集。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482222"
---
# <a name="quantum-computing-glossary"></a>量子計算用語集

## <a name="adjoint"></a>随伴

[操作](xref:microsoft.quantum.glossary#operation)の複合コンジュゲート転置. [単項](xref:microsoft.quantum.glossary#unitary-operator)演算子を実装する操作の場合、ジョイントは操作の逆であり、短剣記号で示されます。 たとえば、演算`U`が $U$の一項演算子を`Adjoint U`表す場合は、$U^\dagger$ を表します。 詳細については、「 [Adjoint](xref:microsoft.quantum.language.file-structure#adjoint)」を参照してください。

## <a name="ancilla"></a>アンシラ

量子コンピュータの一時メモリとして機能し、必要に応じて割り当て解除される[qubit。](xref:microsoft.quantum.glossary#qubit)  詳細については、「[複数のクビット](xref:microsoft.quantum.concepts.multiple-qubits)」を参照してください。

## <a name="bell-state"></a>ベル状態

2つの量子ビットの4つの特異的な最大[絡み合った](xref:microsoft.quantum.glossary#entanglement)[量子状態](xref:microsoft.quantum.glossary#quantum-state)のうちの1つ。 4 つの状態は $\ket{\beta_ {ij}} = (\mathbb{I} \otimes X^iZ^j) (\ケット{00}+ \ケット{11}) / \sqrt{2}$と定義されます。 ベル状態は[EPR ペア](xref:microsoft.quantum.glossary#epr-pair)とも呼ばれます。

## <a name="bloch-sphere"></a>ブロッホ球体

3 次元の単位球の点としての単[一量子](xref:microsoft.quantum.glossary#qubit)[状態](xref:microsoft.quantum.glossary#quantum-state)のグラフィカル表現。 詳細については、「[ブロッホ球体を使用したクビットと変換の視覚化](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)」を参照してください。

## <a name="callable"></a>呼び出し

Q# 言語の[操作](xref:microsoft.quantum.glossary#operation)または[関数](xref:microsoft.quantum.glossary#function)。 詳しくは、[操作と関数の型を](xref:microsoft.quantum.language.type-model#operation-and-function-types)参照してください。

## <a name="clifford-group"></a>クリフォードグループ

[ブロッホ球](xref:microsoft.quantum.glossary#bloch-sphere)の八角形を占める一連の操作と[、パウリ演算子](xref:microsoft.quantum.glossary#pauli-operators)の効果の順列. これには[、$X$](xref:microsoft.quantum.intrinsic.x)、 [$Y $](xref:microsoft.quantum.intrinsic.y)、 [$Z $](xref:microsoft.quantum.intrinsic.z)、 $H $ [、$S](xref:microsoft.quantum.intrinsic.s) [$](xref:microsoft.quantum.intrinsic.h)の操作が含まれます。

## <a name="controlled"></a>制御

ターゲット[操作](xref:microsoft.quantum.glossary#operation)のイネーブラーとして 1 つ以上[の量子ビット](xref:microsoft.quantum.glossary#qubit)を使用するクォンタム演算。 詳細については、「[制御」](xref:microsoft.quantum.language.type-model#controlled)を参照してください。

## <a name="dirac-notation"></a>ディラック表記法

[量子状態](xref:microsoft.quantum.glossary#quantum-state)の表現を単純化する記号的な短縮形、*ブラジャーケット*表記とも呼ばれる。  *ブラジャー*部分は行ベクトルを表します( 例:$\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ と *、ケット*部分は列ベクトル\\\\を表します。 詳細については、「[ディラック表記法](xref:microsoft.quantum.concepts.dirac)」を参照してください。

## <a name="eigenvalue"></a>固有値

変換の適用によって、特定の変換の[固有ベクトル](xref:microsoft.quantum.glossary#eigenvector)の大きさが変化する係数。  平方行列$M$と固有ベクトル$v$を与えられ、$Mv = cv$、$c$ は固有値であり、任意の引数の複素数にすることができます。 詳細については、「[マトリックスの詳細な概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。

## <a name="eigenvector"></a>固有ベクトル

指定された変換によって方向が変更されず、そのベクトルの固有[値](xref:microsoft.quantum.glossary#eigenvalue)に対応する係数によって大きさが変化するベクトル。 $M$ の平方行列と固有値$c$ を指定すると、$Mv = cv$ ($v$ は行列の固有ベクトルであり、任意の引数の複素数を指定できます) 詳細については、「[マトリックスの詳細な概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。

## <a name="entanglement"></a>エンタングルメント

[量子ビット](xref:microsoft.quantum.glossary#qubit)などの量子粒子は、互いに独立して記述できないように接続または*絡み合*うことができます。 測定結果は、無限に離れて分離しても相関しています。 エンタングルメントは、クビットの[状態](xref:microsoft.quantum.glossary#quantum-state)を[測定](xref:microsoft.quantum.glossary#measurement)するために不可欠です。  詳細については、「[マトリックスの詳細な概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。

## <a name="epr-pair"></a>EPR ペア

2つの[量子ビット](xref:microsoft.quantum.glossary#qubit)の4つの特異的な最大絡み合った[量子状態](xref:microsoft.quantum.glossary#quantum-state)のうちの1つ。 4 つの状態は $\ket{\beta_ {ij}} ={1} (\mathbb \otimes X^iZ^j) (\ケット{00}+ \ケット{11}) / \sqrt{2}$と定義されます。 EPR ペアは[ベル状態](xref:microsoft.quantum.glossary#bell-state)とも呼ばれます

## <a name="evolution"></a>進化

時間の経過とともに[量子状態](xref:microsoft.quantum.glossary#quantum-state)がどのように変化するかを示します。 詳細については、「[行列指数](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)」を参照してください。

## <a name="function"></a>機能
純粋に古典的な (非量子) Q# 言語のサブルーチンの一種。 関数はクォンタム アルゴリズム内で使用されますが、[量子ビット](xref:microsoft.quantum.glossary#qubit)または呼び出し[操作](xref:microsoft.quantum.glossary#operation)に対しては機能できません。 詳しくは、[操作と関数の型を](xref:microsoft.quantum.language.type-model#operation-and-function-types)参照してください。

## <a name="gate"></a>ゲート

古典的な論理ゲートの概念に基づく量子[操作](xref:microsoft.quantum.glossary#operation)のレガシー用語。 [量子回路](xref:microsoft.quantum.glossary#quantum-circuit-diagram)は、古典的な論理回路の同様の概念に基づくゲート(または操作)のネットワークです。

## <a name="global-phase"></a>グローバルフェーズ

2 つの[状態](xref:microsoft.quantum.glossary#quantum-state)が、$e^{i\phi}$の複素数の倍数まで同じである場合、それらはグローバルフェーズまで異なると言われます。 局所段階とは異なり、グローバルなフェーズ[は、測定](xref:microsoft.quantum.glossary#measurement)を通じて観察することはできません。 詳細については[、「Qubit」](xref:microsoft.quantum.concepts.qubit)を参照してください。

## <a name="hadamard"></a>Hadamard

ハダマール操作 (ハダマール ゲートまたは変換とも呼ばれます) は、単一[の量子ビット](xref:microsoft.quantum.glossary#qubit)に作用し、qubit が最初に{0}$\ket${0}{1}状態にある場合は$\ket $ または $\ket $ の[重ね合わせ](xref:microsoft.quantum.glossary#superposition)に置きます。 Q# では、この操作は定義済みの[`H`](xref:microsoft.quantum.intrinsic.h)操作によって適用されます。

## <a name="immutable"></a>固定

値を変更できない変数。 キーワードを使用して、Q# の変更できない変数`let`が作成されます。 変更*可能*な変数を宣言するには[、mutable](xref:microsoft.quantum.glossary#immutable)キーワードを使用して宣言し`set`、値を変更するキーワードを使用します。 

## <a name="measurement"></a>Measurement

観察の結果を生成する[量子ビット](xref:microsoft.quantum.glossary#qubit)(または量子ビットのセット) の操作で、事実上、古典的なビットを取得します。 詳細については[、「Qubit」](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)を参照してください。

## <a name="mutable"></a>変更可能

作成後に値を変更できる変数。 Q# の可変変数は、キーワードを`mutable`使用して宣言され、キーワード`set`を使用して変更されます。 キーワードで作成された`let`変数は[変更不可](xref:microsoft.quantum.glossary#immutable)であり、その値は変更できません。

## <a name="namespace"></a>名前空間

関連する名前のコレクション ([操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)) のラベル。 たとえば、名前空間[Microsoft.Quantum.Preparing は](xref:microsoft.quantum.preparation)、初期状態の準備に役立つ標準ライブラリで定義されているすべてのシンボルにラベルを付けます。

## <a name="operation"></a>Operation

Q# でのクォンタム実行の基本単位。 C、C++、またはPythonの関数、またはC#またはJavaの静的メソッドとほぼ同等です。 詳しくは、[操作と関数の型を](xref:microsoft.quantum.language.type-model#operation-and-function-types)参照してください。

## <a name="operator-application"></a>オペレーターアプリケーション

量子操作を実行する。 これは通常、現在の量子状態ベクトルに分母行列を適用する。

## <a name="oracle"></a>Oracle

実行時にクォンタム アルゴリズムにデータ依存情報を提供するサブルーチン。 一般的に目標は、[重ね合わせ](xref:microsoft.quantum.glossary#superposition)の入力に対応する出力の重ね合わせを提供することです。 詳細については[、「Oracle」](xref:microsoft.quantum.libraries.data-structures#oracles)を参照してください。

## <a name="partial-application"></a>部分的なアプリケーション

必要な入力をすべて入力せずに[関数](xref:microsoft.quantum.glossary#function)または[操作](xref:microsoft.quantum.glossary#operation)を呼び出す。 これは、将来のアプリケーションで指定する (アンダースコアで示される) 不足しているパラメーターのみを必要とする新しい[呼び出し可能](xref:microsoft.quantum.glossary#callable)を返します。 たとえば、関数を指定すると`MyFunc(x : int, y : int) : int {return x + y;}`、その関数を部分的に新しい関数`let NewFunc = MyFunc(_, 3)`に適用できます。 その後、値`NewFunc(2)`*5*を返す欠落パラメーターを使用して、後で新しい関数を呼び出すことができます。  詳細については、「[部分アプリケーション](xref:microsoft.quantum.language.expressions#partial-application)」を参照してください。

## <a name="pauli-operators"></a>パウリ演算子

と呼ばれる 3 つの 2 x 2 単位`X`行列`Y`の`Z`セットと量子演算。 多くの場合、$I$ という単位行列もセットに含まれます。  $I = \begin{bmatrix} \\ \\ 1 & 0 0 & 1 \end{bmatrix}$, $X \\ \\ = \begin{bmatrix} 0 & 1 1 1 & 0 \\ \\ \end{bmatrix}$, $Y = \begin{bmatrix} 0 \\ \\ & -i & 0 \end{bmatrix}$$Z = \begin{bmatrix} 1 & 0 & -1 \end{bmatrix$$.   詳細については、[単一の量子ビット操作を](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)参照してください。

## <a name="quantum-circuit-diagram"></a>量子回路図

単純な量子プログラムの[操作](xref:microsoft.quantum.glossary#operation)シーケンス (または[ゲート](xref:microsoft.quantum.glossary#gate)) をグラフィカルに表現する方法(例![えばサンプル回路](~/media/qpe.png)図. 詳細については、「[量子回路」を](xref:microsoft.quantum.concepts.circuits)参照してください。

## <a name="quantum-libraries"></a>量子ライブラリ

Q# プログラムを作成するための[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)のコレクション。 [標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)はデフォルトでインストールされます。 その他に、[化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro)、[数値ライブラリ](xref:microsoft.quantum.numerics.intro)、[機械学習ライブラリ](xref:microsoft.quantum.machine-learning.concepts.intro)があります。

## <a name="quantum-state"></a>量子状態

[測定](xref:microsoft.quantum.glossary#measurement)確率を抽出できる、単離された量子系の正確な状態。 量子コンピューティングでは、量子シミュレータはこの情報を使用して、量子ビットが操作にどのように反応するかをシミュレートします。 詳細については[、「Qubit」](xref:microsoft.quantum.concepts.qubit)を参照してください。

## <a name="qubit"></a>クビット

量子情報の基本単位であり、古典的なコンピューティングの*ビット*に似ています。 詳細については[、「Qubit」](xref:microsoft.quantum.concepts.qubit)を参照してください。

## <a name="repeat-until-success"></a>繰り返し成功まで

前駆体的に成功する量子アルゴリズム。 失敗すると、ルーチンは成功するまで (または制限に達するまで) 再試行します。 詳細については、「[成功するまで繰り返す (RUS)」を](xref:microsoft.quantum.techniques.qubits#measurements)参照してください。

## <a name="standard-libraries"></a>標準ライブラリ

[インストール](xref:microsoft.quantum.glossary#operation)時に Q# コンパイラと共にインストールされる操作、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)。 標準ライブラリ実装は、ターゲットマシンに関しては不用意です。 詳細については、[標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)を参照してください。

## <a name="superposition"></a>重ね 合わせ

量子コンピューティングの概念は、[量子ビット](xref:microsoft.quantum.glossary#qubit)が[測定](xref:microsoft.quantum.glossary#measurement)されるまで$\ket{\0}$と$\ket{\1}$の2つの状態の線形組み合わせであるという考え方です。  詳細については、「[量子コンピューティングとは 」](xref:microsoft.quantum.overview.what)を参照してください。

## <a name="target-machine"></a>ターゲットマシン

抽象的な量子プログラムをハードウェアまたはシミュレーションに向けて低下するコンパイルターゲット。 これには、ゲートの置換、エラー修正のためのエンコーディング、幾何学的レイアウトなど、多くの目的での書き換えが含まれます。 詳細については、「 [Quantum シミュレーターとホスト アプリケーション](xref:microsoft.quantum.machines)」を参照してください。

## <a name="teleportation"></a>テレポーテーション

[エンタングルメント](xref:microsoft.quantum.glossary#entanglement)と[測定](xref:microsoft.quantum.glossary#measurement)を使用して、[quantum state](xref:microsoft.quantum.glossary#quantum-state)量子ビットを物理的に移動することなく、ある場所から別の場所へ、ある[量子ビット](xref:microsoft.quantum.glossary#qubit)のデータを再生成する方法。  詳細については、「[量子回路](xref:microsoft.quantum.concepts.circuits)とすべてを[組み合わせる](xref:microsoft.quantum.techniques.puttingittogether)」を参照してください。

## <a name="tuple"></a>組

単一の値として機能するコンマ区切り値のコレクション。 組の*型*は、タプルに含まれる値の型によって定義されます。 Q# では、タプルは[不変で](xref:microsoft.quantum.glossary#immutable)、入れ子にしたり、配列を含めたり、配列で使用することができます。 詳細については、「[タプルタイプ](xref:microsoft.quantum.language.type-model#tuple-types)」を参照してください。

## <a name="unitary-operator"></a>ユニタリー演算子

逆が[その接合部](xref:microsoft.quantum.glossary#adjoint)と等しい演算子、つまり、$UU^{\dagger} = \id$です。

## <a name="user-defined-type"></a>ユーザー定義型

組み込み型または定義済みの型のコレクションで、単一の単位と呼ばれる場合があります。 詳細については、「[ユーザー定義型](xref:microsoft.quantum.language.type-model#user-defined-types)」を参照してください。