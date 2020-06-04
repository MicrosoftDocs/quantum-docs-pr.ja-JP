---
title: クォンタムコンピューティング用語集
description: クォンタムコンピューティングで使用される一般的な用語、アクション、およびオブジェクトの用語集。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: 042e4e27ef4e42cfc0c24fbb0ae2232cf1bbfe36
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327613"
---
# <a name="quantum-computing-glossary"></a>クォンタムコンピューティング用語集

## <a name="adjoint"></a>Adjoint

[操作](xref:microsoft.quantum.glossary#operation)の複素共役転置。 [ユニタリ](xref:microsoft.quantum.glossary#unitary-operator)演算子を実装する操作の場合、adjoint は演算の逆であり、ダガー記号によって示されます。 たとえば、操作が $U $ という単位の単位を表している場合、は `U` `Adjoint U` $U ^ \ ダガー $ を表します。 詳細については、「 [Adjoint](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)」を参照してください。

## <a name="ancilla"></a>Ancilla

クォンタムコンピューターの一時的なメモリとして機能し、必要に応じて割り当てられ、割り当てが解除される[qubit](xref:microsoft.quantum.glossary#qubit) 。  詳細については、「[複数の qubits](xref:microsoft.quantum.concepts.multiple-qubits)」を参照してください。

## <a name="bell-state"></a>ベルの状態

2つの qubits の下回っ[あり](xref:microsoft.quantum.glossary#entanglement)の4つの[状態](xref:microsoft.quantum.glossary#quantum-state)のうちの1つ。 4つの状態は、$ \ket{\ beta_ {ij}} = (\mathbb{I}/otimes X ^ iZ ^ j) (\ket {00} + \ket {11} )/\ sqrt $ と定義されてい {2} ます。 ベルの状態は、 [EPR ペア](xref:microsoft.quantum.glossary#epr-pair)とも呼ばれます。

## <a name="bloch-sphere"></a>Bloch 球

3次元の単位球のポイントとしての単一[qubit](xref:microsoft.quantum.glossary#qubit) [クォンタム状態](xref:microsoft.quantum.glossary#quantum-state)のグラフィック表現。 詳細については、「 [Bloch 球を使用した Qubits と変換の視覚化](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)」を参照してください。

## <a name="callable"></a>呼び出し可能

Q # 言語の[操作](xref:microsoft.quantum.glossary#operation)または[関数](xref:microsoft.quantum.glossary#function)。 詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。

## <a name="clifford-group"></a>Clifford グループ

[Bloch 球](xref:microsoft.quantum.glossary#bloch-sphere)の octants と、 [p li 演算子](xref:microsoft.quantum.glossary#pauli-operators)の効果の順列を占有する操作のセット。 これには、操作[$X $](xref:microsoft.quantum.intrinsic.x)、 [$Y $](xref:microsoft.quantum.intrinsic.y)、 [$Z $](xref:microsoft.quantum.intrinsic.z)、 [$H $](xref:microsoft.quantum.intrinsic.h) 、 [$S $](xref:microsoft.quantum.intrinsic.s)が含まれます。

## <a name="controlled"></a>た

ターゲット操作のイネーブラーとして1つ以上の[qubits](xref:microsoft.quantum.glossary#qubit)を受け取るクォンタム[操作](xref:microsoft.quantum.glossary#operation)。 詳細については、「[制御対象と adjoint の操作](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations)」を参照してください。

## <a name="dirac-notation"></a>Dirac 表記

[クォンタムの状態](xref:microsoft.quantum.glossary#quantum-state)の表現を簡略化するシンボリックな略記 ( *bra k* notation とも呼ばれます)。  *Bra*部分は、行ベクトルを表します。たとえば、$ \begin{bmatrix} {_1} & {_2} \end{bmatrix} $、 *k*部分は列ベクター、$ \ket{B} = \begin{bmatrix} B {_1} \\ \\ B {_2} \end{bmatrix} $ を表します。 詳細については、「 [Dirac 表記](xref:microsoft.quantum.concepts.dirac)」を参照してください。

## <a name="eigenvalue"></a>Eigenvalue

変換の適用によって、特定の変換の[eigenvector](xref:microsoft.quantum.glossary#eigenvector)の大きさが変更される要因。  正方形の行列 $M $ と eigenvector $v $ の場合、$Mv = cv $ です。ここで、$c $ は eigenvalue で、任意の数の引数を指定できます。 詳細については、「[高度なマトリックスの概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。

## <a name="eigenvector"></a>Eigenvector

指定された変換によって方向が変更されず、そのベクトルの[eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)に対応する係数によって大きさが変更されるベクトル。 正方形の行列 $M $ と eigenvalue $c $ の場合、$Mv = cv $ となります。ここで、$v $ はマトリックスの eigenvector であり、任意の数の引数を指定できます。 詳細については、「[高度なマトリックスの概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。

## <a name="entanglement"></a>もつれ

[Qubits](xref:microsoft.quantum.glossary#qubit)などのクォンタムパーティクルは、互いに独立して記述できないように、接続するか、または複数の*角度で傾ける*ことができます。 これらの測定結果は、無限に分離されている場合でも相関関係があります。 Entanglement、qubit の[状態](xref:microsoft.quantum.glossary#quantum-state)を[測定](xref:microsoft.quantum.glossary#measurement)するために不可欠です。  詳細については、「[高度なマトリックスの概念](xref:microsoft.quantum.concepts.matrix-advanced)」を参照してください。

## <a name="epr-pair"></a>EPR ペア

2つの[qubits](xref:microsoft.quantum.glossary#qubit)の下回っありの4つの[状態](xref:microsoft.quantum.glossary#quantum-state)のうちの1つ。 4つの状態は、$ \ket{\ beta_ {ij}} = (\mathbb/ {1} otimes X ^ iZ ^ j) (\ket {00} + \ket {11} )/\ sqrt $ と定義されてい {2} ます。 EPR ペアは[ベル状態](xref:microsoft.quantum.glossary#bell-state)とも呼ばれます。

## <a name="evolution"></a>発展

クォンタムの[状態](xref:microsoft.quantum.glossary#quantum-state)が時間の経過と共にどのように変化するか。 詳細については、「 [Matrix 指数](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials)」を参照してください。

## <a name="function"></a>機能
純粋なクラシック (非クォンタム) の Q # 言語のサブルーチンの種類。 関数はクォンタムアルゴリズム内で使用されますが、 [qubits](xref:microsoft.quantum.glossary#qubit)または call[操作](xref:microsoft.quantum.glossary#operation)では動作しません。 詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。

## <a name="gate"></a>ゲートウェイ

古典的なロジックゲートの概念に基づいた、クォンタム[操作](xref:microsoft.quantum.glossary#operation)の従来の用語。 [クォンタム回線](xref:microsoft.quantum.glossary#quantum-circuit-diagram)は、従来のロジック回線と同様の概念に基づいて、ゲート (または操作) のネットワークです。

## <a name="global-phase"></a>グローバルフェーズ

2つの[状態](xref:microsoft.quantum.glossary#quantum-state)が1つの複素数の倍数に等しい場合 $e ^ {i\ phi} $、グローバルフェーズが異なると言います。 ローカルフェーズとは異なり、グローバルフェーズはどの[measurment](xref:microsoft.quantum.glossary#measurement)でも観察できません。 詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit)」を参照してください。

## <a name="hadamard"></a>Hadamard

Hadamard 操作 (Hadamard gate または transform とも呼ばれます) は、1つの[qubit](xref:microsoft.quantum.glossary#qubit)に作用し、 [superposition](xref:microsoft.quantum.glossary#superposition) {0} {1} qubit が最初に $ \ket $ 状態にある場合は、$ \ket $ または $ \ket $ の偶数法則に配置し {0} ます。 Q # では、この操作は定義済みの操作によって適用され [`H`](xref:microsoft.quantum.intrinsic.h) ます。

## <a name="immutable"></a>変更不可

値を変更できない変数。 Q # の変更できない変数は、キーワードを使用して作成され `let` ます。 変更*可能*な変数を宣言するには、 [mutable](xref:microsoft.quantum.glossary#immutable)キーワードを使用してを宣言し、キーワードを使用して `set` 値を変更します。 

## <a name="measurement"></a>Measurement

監視の結果を生成する[qubit](xref:microsoft.quantum.glossary#qubit) (または qubit のセット) の操作。従来のビットを取得します。 詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit)」を参照してください。

## <a name="mutable"></a>変更可能

値が作成後に変更される可能性がある変数。 Q # の変更可能な変数は、キーワードを使用して宣言され、 `mutable` キーワードを使用して変更され `set` ます。 キーワードを使用して作成された変数 `let` は[不変](xref:microsoft.quantum.glossary#immutable)であり、その値を変更することはできません。

## <a name="namespace"></a>名前空間

関連する名前 (つまり、[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)) のコレクションのラベル。 たとえば、名前空間は、初期状態の準備に役立つ標準ライブラリで定義されているすべてのシンボルをラベル[付けします](xref:microsoft.quantum.preparation)。

## <a name="operation"></a>Operation

Q # でのクォンタム実行の基本単位。 これは、C、C++、または Python の関数、または C# または Java の静的メソッドとほぼ同じです。 詳細については、「[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。

## <a name="operator-application"></a>オペレーターアプリケーション

クォンタム操作を実行しています。 通常、これは、現在のクォンタム状態ベクトルに対して、通常、ユニタリ行列を適用します。

## <a name="oracle"></a>Oracle

実行時にクォンタムアルゴリズムにデータ依存の情報を提供するサブルーチン。 通常、目標は、法則内の入力に対応する出力の[法則](xref:microsoft.quantum.glossary#superposition)を提供することです。 詳細については、「 [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles)」を参照してください。

## <a name="partial-application"></a>部分アプリケーション

必須の入力をすべて指定せずに[関数](xref:microsoft.quantum.glossary#function)または[操作](xref:microsoft.quantum.glossary#operation)を呼び出します。 これにより、今後のアプリケーションの実行中に、不足しているパラメーター (アンダースコアで示される) のみを必要とする新しい[呼び出し](xref:microsoft.quantum.glossary#callable)可能が返されます。 たとえば、関数を指定する `MyFunc(x : int, y : int) : int {return x + y;}` と、その関数を新しい関数に部分的に適用でき `let NewFunc = MyFunc(_, 3)` ます。 その後、 `NewFunc(2)` 値*5*を返すパラメーターを指定しないで、後で新しい関数を呼び出すことができます。  詳細については、「[部分アプリケーション](xref:microsoft.quantum.guide.operationsfunctions#partial-application)」を参照してください。

## <a name="pauli-operators"></a>P# li 演算子

`X`、、 `Y` およびクォンタム操作として知られる3つの 2 x 2 つのユニタリ行列のセット `Z` 。 Id 行列 ($I $) も、多くの場合、セットに含まれています。  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix} $、$X = \begin{bmatrix} 0 & 1 \\ \\ 1 & 0 \end{bmatrix} $、$Y = \begin{bmatrix} 0 &-i \\ \\ i & 0 \end{bmatrix} $、$Z = \begin{bmatrix} 1 & 0 \\ \\ 0 &-1 \end{bmatrix} $。   詳細については、「 [Single qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)」を参照してください。

## <a name="quantum-circuit-diagram"></a>クォンタム回線の図

単純なクォンタムプログラムの一連の[操作](xref:microsoft.quantum.glossary#operation)(または[ゲート](xref:microsoft.quantum.glossary#gate)) をグラフィカルに表すメソッド。たとえば、 

![回路図のサンプル](~/media/qpe.png). 

詳細については、「[クォンタム回線](xref:microsoft.quantum.concepts.circuits)」を参照してください。

## <a name="quantum-libraries"></a>クォンタムライブラリ

Q # プログラムを作成するための[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)のコレクション。 [標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)は、既定でインストールされます。 使用できるその他のライブラリは、[化学ライブラリ](xref:microsoft.quantum.chemistry.concepts.intro)、[数値ライブラリ](xref:microsoft.quantum.numerics.intro)、 [Machine learning ライブラリ](xref:microsoft.quantum.machine-learning.concepts.intro)です。

## <a name="quantum-state"></a>クォンタムの状態

分離されたクォンタムシステムの正確な状態。[測定](xref:microsoft.quantum.glossary#measurement)確率を抽出できます。 クォンタムコンピューティングでは、この情報を使用して、操作に対する qubits の応答方法をシミュレートします。 詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit)」を参照してください。

## <a name="qubit"></a>Qubit

古典*的なコンピューティングの1つ*の部分に似た、クォンタム情報の基本単位。 詳細については、「 [Qubit](xref:microsoft.quantum.concepts.qubit)」を参照してください。

## <a name="repeat-until-success"></a>繰り返し-成功まで

見込みが成功するクォンタムアルゴリズム。 エラーが発生すると、ルーチンは成功するまで (または制限に達したときに) 再試行します。 詳細については、「[成功まで繰り返す (RUS)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) 」を参照してください。

## <a name="standard-libraries"></a>標準ライブラリ

インストール時に Q # コンパイラと共にインストールされる[操作](xref:microsoft.quantum.glossary#operation)、[関数](xref:microsoft.quantum.glossary#function)、および[ユーザー定義型](xref:microsoft.quantum.glossary#user-defined-type)。 標準ライブラリの実装は、ターゲットコンピューターに対しては依存しません。 詳細については、「[標準ライブラリ](xref:microsoft.quantum.libraries.standard.intro)」を参照してください。

## <a name="superposition"></a>法則

量子コンピューティングの概念は、 [qubit](xref:microsoft.quantum.glossary#qubit)が測定されるまでの2つの状態 ($ \ket {0} $ と $ \ket {1} $) の[measured](xref:microsoft.quantum.glossary#measurement)線形組み合わせです。  詳細については、「[クォンタムコンピューティングについ](xref:microsoft.quantum.overview.understanding)て」を参照してください。

## <a name="target-machine"></a>ターゲットコンピューター

ハードウェアまたはシミュレーションの抽象的なクォンタムプログラムを下げるコンパイルターゲット。 これには通常、ゲートの置換、エラー修正のためのエンコード、ジオメトリレイアウトなど、さまざまな目的のための再書き込みが含まれます。 詳細については、「[クォンタムシミュレーターとホストアプリケーション](xref:microsoft.quantum.machines)」を参照してください。

## <a name="teleportation"></a>テレポーテーション

[結び付き](xref:microsoft.quantum.glossary#entanglement)[測定と測定](xref:microsoft.quantum.glossary#measurement)を[quantum state](xref:microsoft.quantum.glossary#quantum-state)使用して、qubit を物理的に移動せずに1つの場所から別の場所に1つの[qubit](xref:microsoft.quantum.glossary#qubit)のデータを再生成する方法。  詳細については、「クォンタム[回線](xref:microsoft.quantum.concepts.circuits)」と「 [quantum Katas](xref:microsoft.quantum.overview.katas)の各 kata」を参照してください。

## <a name="tuple"></a>タプル

単一の値として機能するコンマ区切り値のコレクション。 組の*型*は、その組に含まれる値の型によって定義されます。 Q # では、タプルは[不変](xref:microsoft.quantum.glossary#immutable)であり、入れ子にしたり、配列を含めたり、配列で使用したりすることができます。 詳細については、「[タプル型](xref:microsoft.quantum.guide.types#tuple-types)」を参照してください。

## <a name="unitary-operator"></a>ユニタリ演算子

逆数が[adjoint](xref:microsoft.quantum.glossary#adjoint)と等しい (つまり、$UU ^ {-dagger} = \ id $ である) 演算子。

## <a name="user-defined-type"></a>ユーザー定義型

1つの単位として参照される組み込み型または以前に定義された型のコレクション。 詳細については、「[ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)」を参照してください。