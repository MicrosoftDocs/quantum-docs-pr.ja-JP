---
title: 標準ライブラリのデータ構造 Q#
description: Microsoft 標準ライブラリのデータ構造、oracles、dynamical ジェネレーターについて説明し Q# ます。
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 222fa7d0d33d4ac6c15e9ee9e6e97f380867a145
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868522"
---
# <a name="data-structures-and-modeling"></a>データ構造とモデリング #

## <a name="classical-data-structures"></a>典型的データ構造 ##

また、ユーザー定義型を使用して、クォンタムの概念を表します。また、キャノンシステムの制御に使用される典型的なデータを操作するための操作、関数、および型も提供します。
たとえば、関数は、 <xref:microsoft.quantum.arrays.reversed> 配列を入力として受け取り、同じ配列を逆の順序で返します。
これは、型の配列に対して使用でき `Qubit[]` ます。これにより、整数のクォンタム表現間で変換を行うときに、不要な $/演算子 name{swap} $ ゲートが適用されるのを回避できます。
同様に、前のセクションで説明したように、フォームの型は `(Int, Int -> T)` ランダムアクセスコレクションを表すのに役立ちます。そのため、関数は、 <xref:microsoft.quantum.arrays.lookupfunction> 配列型からこのような型を構築する便利な方法を提供します。

### <a name="pairs"></a>ペア ###

キャノンは、分解によるタプルへのアクセスを補完する、ペアに対する関数形式の表記をサポートしています。

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>配列 ###

Canon には、配列を操作するための関数がいくつか用意されています。
これらの関数は型パラメーター化されるため、任意の型の配列と共に使用でき Q# ます。
たとえば、関数は、 <xref:microsoft.quantum.arrays.reversed> 入力とは逆の順序で要素を持つ新しい配列を返します。
これは、操作を呼び出すときに、クォンタムレジスタがどのように表されるかを変更するために使用できます。

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

同様に、関数を使用して、 <xref:microsoft.quantum.arrays.subarray> 配列の要素の順序を変更したり、サブセットを取得したりできます。

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

フロー制御と組み合わせると、などの配列操作関数は、 <xref:microsoft.quantum.arrays.zip> クォンタムプログラムを表現するための強力な方法を提供できます。

```qsharp
// Applies X₃ Y₁ Z₇ to a register of any size.
ApplyToEach(
    ApplyPauli(_, register),
    Map(
        EmbedPauli(_, _, Length(register)),
        Zip([PauliX, PauliY, PauliZ], [3, 1, 7])
    )
);
```

## <a name="oracles"></a>Oracles ##

フェーズの[推定](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm)と[振幅増幅](https://en.wikipedia.org/wiki/Amplitude_amplification)の資料では、oracle の概念が頻繁に表示されます。
ここで、oracle という用語は、qubits のセットに対して動作し、その回答をフェーズとして返すブラックボックスクォンタムサブルーチンを指します。
多くの場合、このサブルーチンは、他のいくつかのパラメーターに加えて oracle を受け入れるクォンタムアルゴリズムへの入力と考えることができます。また、一連のクォンタム操作を適用し、このクォンタムサブルーチンの呼び出しを基本的なゲートと同様に処理します。
当然ながら、より大きなアルゴリズムを実際に実装するためには、oracle の根本的な分解を基本的なゲートに提供する必要がありますが、このような分解は、oracle を呼び出すアルゴリズムを理解するためには必要ありません。
では Q# 、この抽象化は、操作がファーストクラスの値であることによって表されます。これにより、操作を、ブラックボックス方式でクォンタムアルゴリズムの実装に渡すことができます。
さらに、ユーザー定義型を使用して、さまざまな oracle 表現をタイプセーフな方法でラベル付けすることで、さまざまな種類のブラックボックス操作を誤って混同ことが困難になります。

このような oracles は、 [Grover の検索](https://en.wikipedia.org/wiki/Grover%27s_algorithm)やクォンタムシミュレーションアルゴリズムなどの有名な例を含む、さまざまなコンテキストで表示されます。
ここでは、振幅増幅とフェーズ推定の2つのアプリケーションに必要な oracles に焦点を当てています。
最初に、振幅増幅の oracles について説明してから、フェーズの推定に進みます。

### <a name="amplitude-amplification-oracles"></a>振幅増幅 Oracles ###

振幅増幅アルゴリズムは、状態の反射のシーケンスを適用して、初期状態と最終状態との間の回転を実行します。
アルゴリズムを機能させるには、これらの状態の両方を指定する必要があります。
これらの仕様は、2つの oracles によって指定されます。
これらの oracles は、入力を "ターゲット" サブ空間と "初期" サブ空間という2つのスペースに分割することで機能します。
Oracles は、このようなサブスペースを識別します。これは、p Li 演算子が2つのスペースを識別する方法と似ています。これらのスペースには、$ pm $1 フェーズを適用します。
主な違いは、このアプリケーションではこれらのスペースが半分のスペースである必要がないことです。
また、これら2つのサブスペースは、通常は相互に排他的ではないことに注意してください。両方のスペースのメンバーであるベクターが存在します。
この値が true でない場合、振幅増幅は影響を受けません。そのため、最初のサブ空間が対象のサブ空間と重複しないようにする必要があります。

ここでは、振幅増幅を $0 に $P するために必要な最初の oracle について説明します。これは、 \_ 次のアクションを行うように定義されています。  "Initial" サブ空間 $P 0 \ket{x} =-\ket{x} $ のすべての州 $ \ket{x} $ に対して \_ 、このサブ空間に含まれていないすべての州 $ \ket{y} $ には、 \_ 0 \ket{y} = \ket{y} $ が $P ます。
対象のサブ空間をマークする oracle ($P _1 $) は、まったく同じ形式になります。
ターゲットのサブ空間内のすべての州 $ \ket{x} $ (つまり、アルゴリズムによって出力されるすべての状態) に対して、$P _1 \ k {x} =-\ket{x} $ を使用します。
同様に、対象のサブ空間に含まれていないすべての州 $ \ket{y} $ に対して、_1 \ k {y} = \ket{y} $ という $P ます。
次に、これら2つの反射を結合して、施行 =-P_0 P_1 $ という $Q の1つの手順を実行する演算子を形成します。この場合、マイナス記号全体は、制御されたアプリケーションで考慮する必要があります。
次に、最初のサブ空間にある $ \ket{\psi} $ という初期状態を取得し、$ \ket{\psi} を実行してから、$ を実行します。
このような反復処理を実行すると、最初の状態が、マークされたスペースを持つ $ \ sin ^ 2 (-シータ) $ と重複している場合、$ iteration を $m した後、この重複が $ \ sin ^ 2 ([2m + 1] \ シータ) $ になります。
そのため、通常は $ [2m + 1] \ シータ = \ pi/2 $; のような無料のパラメーターとして $m $ を選択する必要があります。ただし、このような剛体選択は、固定ポイントの振幅増幅など、一部の種類の振幅増幅では重要ではありません。
このプロセスでは、quadratically を使用してマークされたサブ空間に状態を準備することができます。これは、限定機能に対するクエリの数を減らすとともに、厳密なクラシックデバイスでは実現できません。
これは、多くのアプリケーションがクォンタムコンピューティングを行う場合に、振幅増幅が大きなビルディングブロックであるためです。

アルゴリズムの使用方法を理解するために、oracles の構築を可能にする例を提供すると便利です。  この設定では、データベース検索に Grover のアルゴリズムを実行することを検討してください。
Grover の検索では、目標は、状態を $ \ket{+} ^ {\ otimes n} = H ^ {/otimes n} \ket {0} $ から (可能性がある) 多くのマークされた状態に変換することです。
さらに簡単にするために、マークされた状態のみが $ \ket $ であるケースを見てみましょう {0} 。
次に、2つの oracles が用意されています。1つは、マイナス記号を使用して初期状態 $ \ket{+} ^ {\ otimes n} $ にマークを付け、もう1つはマイナス記号を使用してマークされた状態 $ \ket $ をマークし {0} ます。
2番目のゲートは、キャノンの制御フロー操作を使用して、次の処理操作を使用して実装できます。

```qsharp
operation ReflectAboutAllZeros(register : Qubit[]) : Unit 
is Adj + Ctl {

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);

    // Apply an $n-1$ controlled $Z$-gate to the $n^{\text{th}}$ qubit.
    // This gate will lead to a sign flip if and only if every qubit is
    // $1$, which happens only if each of the qubits were $0$ before step 1.
    Controlled Z(Most(register), Tail(register));

    // Apply $X$ gates to every qubit.
    ApplyToEach(X, register);
}
```

この oracle は操作の特殊なケースであり <xref:microsoft.quantum.canon.rall1> 、リフレクションケース $ + phi = \ pi $ の代わりに任意のフェーズで回転できます。
この場合、 `RAll1` は準備操作に似てい <xref:microsoft.quantum.intrinsic.r1> ます。これは、single qubit 状態 $ \ket $ の代わりに $ \ket{11\cdots1} $ を回転させる点です {1} 。

初期サブ空間をマークする oracle は同様に構築できます。
擬似コードで:

1. すべての qubit に $ ゲート $H 適用します。
2. すべての qubit に $ ゲート $X 適用します。
3. $N ^ {\ text{th} $ qubit に $n $1 の $Z $-gate を適用します。
4. すべての qubit に $ ゲート $X 適用します。
5. すべての qubit に $ ゲート $H 適用します。

今回は、前に説明した <xref:microsoft.quantum.canon.applywith> 操作と共にを使用する方法も示し <xref:microsoft.quantum.canon.rall1> ます。

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

次に、これら2つの oracles を組み合わせて、2つの状態と決定的な変換 $ \ket{+} ^ {-otimes n} $ から $ \ket $ への回転を可能にします。これ {0} は、Hadamard ゲートの複数のレイヤーを使用して、$ \ sqrt{2 ^ n} $ に比例します。 (ie $m \、\ sqrt{2 ^ n} $) と約 $ 2 ^ n $ のレイヤーで、$ \ket $ の状態を無作為に準備するために必要となるのは、 {0} 結果 $0 $ が観測されるまで初期状態を準備して測定することです。

### <a name="phase-estimation-oracles"></a>フェーズ推定 Oracles ###

フェーズの推定では、oracles の方がやや自然です。
フェーズの推定の目的は、ユニタリ行列の固有値からサンプリングできるサブルーチンを設計することです。
この方法は、化学およびマテリアルサイエンスの物理的な問題が多く発生しているため、このような実験では、物質のフェーズ図と分子の反応力学に関する貴重な情報を提供する、注ぎの quantum システムのグラウンドステートを提供しています。
フェーズ推定のすべてのフレーバーには、入力のユニタリが必要です。
このユニタリは、2種類の oracles のいずれかで記述された通常です。

> [!TIP]
> これらのサンプルでは、次に示す oracle の両方の型について説明します。
> 連続クエリ oracles の詳細については、 [ **PhaseEstimation**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)を参照してください。
> 離散クエリ oracles の詳細については、 [ **IsingPhaseEstimation**サンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/phase-estimation)を参照してください。

Oracle の最初の種類は、個別のクエリとして oracle を呼び出し、ユーザー定義型で表現します。単に、1つのインテキスト <xref:microsoft.quantum.oracles.discreteoracle> 行列を使用します。
$U $ が、推定する値を持つユニタリの場合、$U $ の oracle は $U $ を実装するサブルーチンの単なるスタンドアロンです。
たとえば、$U $ は、前に定義した振幅推定用の oracle $Q $ になることがあります。
このマトリックスの固有値を使用して、初期状態とターゲット状態の間の重複を推定することができます $ \ sin ^ 2 (quadratically) $。それ以外の場合に必要なサンプルの数を減らすことができます。
これにより、Grover oracle $Q $ を使用して、振幅推定のモニカーを入力として使用して、フェーズ推定の適用を行うことができます。
クォンタム metrology で広く使われているもう1つの一般的なアプリケーションでは、小さな回転角度を推定する必要があります。
つまり、$-シータ $ を推定して、$R _z (\ シータ) $ という形式の不明な回転ゲートを計算します。
このような場合、ゲートの $ \ シータ $ という固定値を学習するために対話するサブルーチンは $ $ \begin{align} U & = R_z (-シータ) \\ \\ & = \begin{bmatrix} e ^ {-i/シータ/2} & 0 \\ \\ 0 & e ^ {i \ シータ/2} \end{bmatrix}.
\end{align} $ $

フェーズ推定で使用される oracle の2つ目の種類は、型によって表される、oracle の連続クエリです <xref:microsoft.quantum.oracles.continuousoracle> 。
フェーズ推定のための連続クエリ oracle では、$U (t) $ という形式を使用します。ここで $t $ はクラシックデプロイの既知の実数です。
$ を固定の $U にした場合、連続クエリ oracle では $U (t) = U ^ t $ という形式が使用されます。
これにより、個別のクエリモデルに直接実装できなかった $-sqrt{u} $ などのマトリックスに対してクエリを実行できます。

この種類の oracle は、特定のユニタリを調査していないが、そのために、ユニタリのジェネレーターのプロパティを学習する必要がある場合に役立ちます。
たとえば、dynamical クォンタムのシミュレーションでは、Hermitian $H 行列に対して $U (t) = e ^ {-i H t} $ を厳密に概算したクォンタム回線 ($ と進化時間 $t $) をシミュレートすることを目標としています。
$U (t) $ の固有値は、$H $ の固有値に直接関連付けられています。
これを確認するには、$H $: $H \ket{E} = E\ket {E} $ の eigenvector を考えてみます。これにより、(t) \ket{E} = e ^ {i} \ k {E} = e ^ {-iEt} \ket{E} $ と $U いうマトリックス指数のパワーシリーズ定義から簡単に見ることができます。
したがって、$U (t) $ の eigenphase を推定すると、eigenphase $E $ として eigenvector $ \ket{E} $ がフェーズ推定アルゴリズムに入力されます。
ただし、この場合、$ $t の値はユーザーの裁量で選択できます。これは、$t $ の値が非常に小さい場合 $E $ は $E =-\ phi/t $ を使用して一意に反転できるためです。
クォンタムシミュレーションメソッドでは、小数部の進化を実行する機能が提供されているため、この設定により、フェーズ推定アルゴリズムでは、インデックスを作成するときに追加の自由度が与えられます。特に、離散クエリモデルでは、$j 整数に対して $U ^ j $ という形式の unitaries $U を使用できます。
これは、$E $; に関する最も多くの情報を提供する実験を正確に選択できるようにするため、フェーズの推定アルゴリズムから効率を上げるために重要です。個別のクエリに基づくメソッドでは、アルゴリズムで最適な数のクエリを選択することによって、危害を加える必要があります。

この具体的な例として、ゲートの回転角度ではなく、クォンタムシステムの procession 周波数を見積もることの問題について考えてみます。
このような量子力学を説明するユニタリは $U (t) = R_z (2 \ オメガ t) $ で、進化時間 $t $ および不明な頻度 $ \ オメガ $ です。
このコンテキストでは、1つの $R _z $ gate を使用して任意の $t $ に対して $U (t) $ をシミュレートできます。そのため、このような場合は、個別のクエリのみを使用して、そのようにする必要はありません。
このような連続モデルには、連続したクエリを使用するフェーズ推定プロセスから得られるプロパティが含まれています。これは、対数関数の分岐カットによってマスクされるフェーズ情報が、$t $ の非対応値に対して実行される実験の結果から明らかになる可能性があるためです。
このため、このような連続したクエリモデル (フェーズ推定) の場合、oracle は適切なだけでなく、個別のクエリモデルにも適しています。
このため、 Q# 両方の形式のクエリに対して機能があり、ユーザーにそのまま残して、ニーズと使用可能な oracle の種類に合わせてフェーズ推定アルゴリズムを決定します。

## <a name="dynamical-generator-modeling"></a>Dynamical Generator モデリング ##

時間の経過に伴うジェネレーターは、状態がどのように変化するかを示します。 たとえば、クォンタムの状態 $ \ket{\psi} $ の dynamics は、Schrödinger 式 $ $ \begin{align} i\ frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ によって制御されます。これは、Hermitian と呼ばれる Hamiltonian matrix $H $ で、モーションのジェネレーターとなります。 初期状態が $ \ket{\psi (0)} $ の場合 $t = $0、この式に対する正式なソリューション $t $ は、原則として、$ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}、\end{align} $ $ のように記述されています。この場合、行列指数 $U (t) = e ^ {-i H t} $ は、ユニタリ時間の進化演算子と呼ばれます。 次に、このフォームのジェネレーターに焦点を当てていますが、この概念は、開いているクォンタムシステムのシミュレーションや、より抽象的な差分式など、より広範に適用されることを重視しています。

Dynamical シミュレーションの主な目的は、クォンタムコンピューターの qubits でエンコードされたクォンタムの状態に対して進化演算子を実装することです。  多くの場合、Hamiltonian は $d $ より単純な用語の合計に分割されることがあります。

$ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

各用語による時間の進化は、クォンタムコンピューターで簡単に実装できます。 たとえば、$H _j $ は、qubit レジスタの1番目と2番目の要素に対して動作する $X _1X_2 $ 演算子で `qubits` あり、その後の任意の $t 時間における時間の増加は、シグネチャを持つ操作を呼び出すことによって簡単に実装できます `Exp([PauliX,PauliX], t, qubits[1..2])` `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` 。 Hamiltonian のシミュレーションで後ほど説明するように、1つの解決策として、$H $ による時間の進化にかかる時間を短縮することがあります。

$ $ \begin{align} U (t) & = \ left (e ^ {-iH \_ 0 t/r} e ^ {-ih \_ 1 t/r} \ cドット e ^ {-ih \_ {d-1} t/r} \ right) ^ {r} + \mathcal{O} (d ^ 2 \ max_j \\ |H \_ j \\ | ^ 2 t ^ 2/r)、\end{align} $ $

> $0 の整数 $r では、近似誤差を制御します。

Dynamical generator モデリングライブラリは、単純なジェネレーターの観点から、複雑なジェネレーターを体系的にエンコードするためのフレームワークを提供します。 そのような説明は、シミュレーションライブラリなどに渡すことによって、選択したシミュレーションアルゴリズムによって時間の進化を実装し、多くの詳細情報が自動的に処理されるようにすることができます。

> [!TIP]
> 以下で説明する dynamical generator ライブラリについては、「」のサンプルを参照してください。 整理モデルに基づく例については、「 [ **isinggenerators**のサンプル](https://github.com/microsoft/Quantum/tree/master/samples/simulation/ising/generators)」を参照してください。
> 分子 Hydrogen に基づく例については、 [**H2SimulationCmdLine**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/command-line)と[**H2SimulationGUI**](https://github.com/microsoft/Quantum/tree/master/samples/simulation/h2/gui)のサンプルを参照してください。

### <a name="complete-description-of-a-generator"></a>ジェネレーターの完全な説明 ###

最上位レベルでは、Hamiltonian の完全な説明が、 `EvolutionGenerator` 2 つのコンポーネントを持つユーザー定義型に含まれています。

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem`ユーザー定義型は、Hamiltonian の古典的な説明です。

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

組の最初の要素は、 `Int` Hamiltonian 内の $ $d $ という語句の数を格納します。2番目の要素 `(Int -> GeneratorIndex)` は、 \{ \} `GeneratorIndex` Hamiltonian 内の各プリミティブ用語を一意に識別するユーザー定義型に、$ 0, 1,..., d-1 $ の整数インデックスをマップする関数です。 Hamiltonian では、配列としてではなく関数として用語のコレクションを指定することによって `GeneratorIndex[]` 、非常に多くの `GeneratorIndex` 用語で Hamiltonians を記述する場合に特に便利なの計算を実行できます。

とてもは、によって識別されるプリミティブ用語に `GeneratorIndex` は、簡単にシミュレートできるという規則を適用しません。 たとえば、前に説明したように、プリミティブな用語は PFermionic の演算子にすることができますが、クォンタムの化学シミュレーションで一般的に使用される annihilation や作成演算子にすることもできます。 単独では、は、 `GeneratorIndex` それが指す用語による時間の進化が、クォンタム回線として実装される可能性があるため、意味がありません。

これを解決するには、 `EvolutionSet` `GeneratorIndex` いくつかの正規セットから描画されたを、1つの `EvolutionUnitary` をクォンタムのサーキットとして表現される、にマップするユーザー定義型を指定します。 は、 `EvolutionSet` を構造化する方法の規則を定義 `GeneratorIndex` し、可能なのセットも定義し `GeneratorIndex` ます。

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>P# li 演算子ジェネレーター ###

ジェネレーターの具体例としては、Hamiltonians 演算子の合計であり、それぞれ異なる係数を持つことがあります。
$ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} a_j H_j, \end{align} $ $。各 H_j $ $ $ は、現在、p Li グループから描画されています。 このようなシステムでは、 `PauliEvolutionSet()` 次の `EvolutionSet` シグネチャを持つによって、P# li グループと係数の要素がどのように識別されるかの規則を定義する型のを提供し `GeneratorIndex` ます。

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

このエンコーディングでは、最初のパラメーターは `Int[]` PI\rightarrow li 文字列を指定します。ここで、$/hat $0、$ \ hat X\rightarrow $1、$/hat Y\rightarrow $2、および $/hat Z\rightarrow $3 です。 2番目のパラメーターは、 `Double[]` Hamiltonian 内の P# li 文字列の係数を格納します。 この配列の最初の要素のみが使用されていることに注意してください。 3番目のパラメーターは、 `Int[]` この psystem.string li 文字列が処理する qubits のインデックスを作成し、重複する要素を持つことはできません。 したがって、Hamiltonian term $0.4 \ hat X_0; hat Y_8/hat I_2/hat Z_1 $ は、

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()`は、この形式のいずれかを、次のシグネチャを持つにマップする関数です `GeneratorIndex` `EvolutionUnitary` 。

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

1番目のパラメーターは、時間の長さを表します。この時間には、に含まれる係数が乗算され `GeneratorIndex` ます。 2番目のパラメーターは、ユニタリが動作する qubit レジスタです。 

### <a name="time-dependent-generators"></a>時間に依存するジェネレーター ###

多くの場合、モデリングの時間に依存するジェネレーターにも興味があります。これは、Schrödinger 式 $ $ \begin{align} i\ frac {d \ket{\psi (t)}} {d t} & = \ hat H (t) \ket{\psi (t)}, \end{align} $ $ で発生する可能性があるためです。 この場合、上記の時間に依存しないジェネレーターからの拡張機能は簡単です。 $ $T すべての時間について Hamiltonian を記述するように固定されているのではなく、 `GeneratorSystem` `GeneratorSystemTimeDependent` ユーザー定義型を使用します。

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

1番目のパラメーターは、[0, 1] $ の連続スケジュールパラメーター $s です。この型の関数は、 `GeneratorSystem` そのスケジュールのを返します。 Schedule パラメーターは、$s = t/T $ のような物理時刻パラメーターに線形的に関連付けられている可能性があることに注意してください (例: シミュレーション $T $ の合計時間)。 ただし、通常はそうではありません。

同様に、このジェネレーターの完全な説明にはが必要である `EvolutionSet` ため、 `EvolutionSchedule` ユーザー定義型を定義します。

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
