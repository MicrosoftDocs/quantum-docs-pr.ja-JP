---
title: 'Q # 標準ライブラリ-データ構造 |Microsoft Docs'
description: 'Q # 標準ライブラリ-データ構造'
author: QuantumWriter
uid: microsoft.quantum.libraries.data-structures
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e8b28561f1aba37cb5bf41c6176386d19bfacf06
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184510"
---
# <a name="data-structures-and-modeling"></a>データ構造とモデリング #

## <a name="classical-data-structures"></a>典型的データ構造 ##

また、ユーザー定義型を使用して、クォンタムの概念を表します。また、キャノンシステムの制御に使用される典型的なデータを操作するための操作、関数、および型も提供します。
たとえば、<xref:microsoft.quantum.arrays.reversed> 関数は、配列を入力として受け取り、同じ配列を逆の順序で返します。
これは `Qubit[]` 型の配列に対して使用できます。これにより、整数のクォンタム表現間で変換を行うときに、不要な $/演算子名 {swap} $ ゲートが適用されるのを回避できます。
同様に、前のセクションでは、ランダムアクセスコレクションを表すために `(Int, Int -> T)` フォームの種類を示しています。そのため、<xref:microsoft.quantum.arrays.lookupfunction> 関数は、配列型からこのような型を構築する方法を提供します。

### <a name="pairs"></a>座標 ###

キャノンは、分解によるタプルへのアクセスを補完する、ペアに対する関数形式の表記をサポートしています。

```qsharp
let pair = (PauliZ, register); // type (Pauli, Qubit[])
ApplyToEach(H, Snd(pair)); // No need to deconstruct to access the register.
```

### <a name="arrays"></a>配列 ###

Canon には、配列を操作するための関数がいくつか用意されています。
これらの関数は型パラメーター化されるため、任意の Q # 型の配列と共に使用できます。
たとえば、<xref:microsoft.quantum.arrays.reversed> 関数は、入力とは逆の順序で要素を持つ新しい配列を返します。
これは、操作を呼び出すときに、クォンタムレジスタがどのように表されるかを変更するために使用できます。

```qsharp
let leRegister = LittleEndian(register);
// QFT expects a BigEndian, so we can reverse before calling.
QFT(BigEndian(Reversed(leRegister!)));
// This is how the LittleEndianAsBigEndian function is implemented:
QFT(LittleEndianAsBigEndian(leRegister));
```

同様に、<xref:microsoft.quantum.arrays.subarray> 関数は、配列の要素の順序を変更したり、サブセットを取得したりするために使用できます。

```qsharp
// Applies H to qubits 2 and 5.
ApplyToEach(H, Subarray([2, 5], register));
```

フロー制御と組み合わせると、<xref:microsoft.quantum.arrays.zip> などの配列操作関数は、クォンタムプログラムを表す強力な方法を提供できます。

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
Q # では、この抽象化は、操作がファーストクラスの値であることによって表されます。これにより、操作を、ブラックボックス方式でクォンタムアルゴリズムの実装に渡すことができます。
さらに、ユーザー定義型を使用して、さまざまな oracle 表現をタイプセーフな方法でラベル付けすることで、異なる種類のブラックボックス操作を誤って混同ことが困難になります。

このような oracles は、 [Grover の検索](https://en.wikipedia.org/wiki/Grover%27s_algorithm)やクォンタムシミュレーションアルゴリズムなどの有名な例を含む、さまざまなコンテキストで表示されます。
ここでは、振幅増幅とフェーズ推定の2つのアプリケーションに必要な oracles に焦点を当てています。
最初に、進んからフェーズの推定までの振幅増幅の oracles について説明します。

### <a name="amplitude-amplification-oracles"></a>振幅増幅 Oracles ###

振幅増幅アルゴリズムは、状態の反射のシーケンスを適用して、初期状態と最終状態との間の回転を実行します。
アルゴリズムを機能させるには、これらの状態の両方を指定する必要があります。
これらの仕様は、2つの oracles によって指定されます。
これらの oracles は、入力を "ターゲット" サブ空間と "初期" サブ空間という2つのスペースに分割することで機能します。
Oracles は、このようなサブスペースを識別します。これは、p Li 演算子が2つのスペースを識別する方法と似ています。これらのスペースには、$ pm $1 フェーズを適用します。
主な違いは、このアプリケーションではこれらのスペースが半分のスペースである必要がないことです。
また、これら2つのサブスペースは、通常は相互に排他的ではないことに注意してください。両方のスペースのメンバーであるベクターが存在します。
この値が true でない場合、振幅増幅は影響を受けません。そのため、最初のサブ空間が対象のサブ空間と重複しないようにする必要があります。

ここでは、次のアクションを実行するために定義されている\_$0 に $P するために、振幅増幅が必要になる最初の oracle について説明します。  "Initial" サブ空間 $P\_0 \ket{x} =-\ket{x} $ のすべての州 $ \ket{x} $ と、このサブ空間に含まれていないすべての州 $ \ket{y} $ について、\_0 \ket{y} = \ket{y} $ $P ます。
対象のサブ空間をマークする oracle ($P _1 $) は、まったく同じ形式になります。
ターゲットのサブ空間内のすべての州 $ \ket{x} $ (つまり、アルゴリズムによって出力されるすべての状態) に対して、$P _1 \ k {x} =-\ket{x} $ を使用します。
同様に、対象のサブ空間に含まれていないすべての州 $ \ket{y} $ に対して、_1 \ k {y} = \ket{y} $ という $P ます。
次に $Q、これら2つの反射を組み合わせて、施行 =-P_0 P_1 $ というの1つの手順を実行する演算子を形成します。マイナス記号全体は、制御されたアプリケーションでのみ考慮する必要があります。
次に、最初のサブ空間にある $ \ket{\psi} $ という初期状態を取得し、$ \ket{\psi} を実行してから、$ を実行します。
このような反復処理を実行すると、最初の状態が、マークされたスペースを持つ $ \ sin ^ 2 (-シータ) $ と重複している場合、$ iteration を $m した後、この重複が $ \ sin ^ 2 ([2m + 1] \ シータ) $ になります。
そのため、通常は $ [2m + 1] \ シータ = \ pi/2 $; のような無料のパラメーターとして $m $ を選択する必要があります。ただし、このような剛体選択は、固定ポイントの振幅増幅など、一部の種類の振幅増幅では重要ではありません。
このプロセスでは、quadratically を使用してマークされたサブ空間に状態を準備することができます。これは、限定機能に対するクエリの数を減らすとともに、厳密なクラシックデバイスでは実現できません。
これは、多くのアプリケーションがクォンタムコンピューティングを行う場合に、振幅増幅が大きなビルディングブロックであるためです。

アルゴリズムの使用方法を理解するために、oracles の構築を可能にする例を提供すると便利です。  この設定では、データベース検索に Grover のアルゴリズムを実行することを検討してください。
Grover の検索では、目標は、状態 $ \ket{+} ^ {\ otimes n} = H ^ {/otimes n} \ket{0}$ を、(可能性がある) 多くのマークされた状態に変換することです。
さらに簡単にするために、マークされた状態のみが $ \ket{0}$ であるケースを見てみましょう。
次に、2つの oracles が用意されています。1つは、初期状態 $ \ket{+} ^ {\ otimes n} $ をマイナス記号付きでマークし、もう1つはマイナス記号を使用してマークされた状態 $ \ket{0}$ を負符号でマークします。
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

この oracle は、<xref:microsoft.quantum.canon.rall1> 操作の特殊なケースで、リフレクションケース $ + phi = \ pi $ の代わりに任意のフェーズで回転できるようにします。
この場合、`RAll1` は <xref:microsoft.quantum.intrinsic.r1> 準備操作に似ています。これは、single qubit 状態 $ \ket{1}$ の代わりに $ \ket{11\cdots1} $ を回転させる点です。

初期サブ空間をマークする oracle は同様に構築できます。
擬似コードで:

1. すべての qubit に $ ゲート $H 適用します。
2. すべての qubit に $ ゲート $X 適用します。
3. $N ^ {\ text{th} $ qubit に $n $1 の $Z $-gate を適用します。
4. すべての qubit に $ ゲート $X 適用します。
5. すべての qubit に $ ゲート $H 適用します。

今回は、前に説明した <xref:microsoft.quantum.canon.rall1> 操作と共に <xref:microsoft.quantum.canon.applywith> を使用する方法についても説明します。

```qsharp
operation ReflectAboutInitial(register : Qubit[]) : Unit
is Adj + Ctl {
    ApplyWithCA(ApplyToEach(H, _), ApplyWith(ApplyToEach(X, _), RAll1(_, PI()), _), register);
}
```

次に、これら2つの oracles を組み合わせて、2つの状態と決定的な変換 $ \ket{+} ^ {-otimes n} $ から $ \ket{0}$ に比例する Hadamard ゲートの複数のレイヤーを使用します。これは、$-sqrt{2 ^ n} $ (ie $m/proprt{2 ^ n} $)$ \ket{0}$ の状態を無作為に準備するために必要となる約 $ 2 ^ n $ のレイヤーとは、結果 $0 $ が観測されるまで初期状態を準備して測定することです。

### <a name="phase-estimation-oracles"></a>フェーズ推定 Oracles ###

フェーズの推定では、oracles の方がやや自然です。
フェーズの推定の目的は、ユニタリ行列の固有値からサンプリングできるサブルーチンを設計することです。
このメソッドは、化学およびマテリアルサイエンスの物理的な問題が多く発生しているため、不可欠の実験では、次のフェーズ図についての重要な情報を提供するクォンタムシステムのグラウンドステート注ぎを提供しています。分子の材料と反力のあるダイナミクス。
フェーズ推定のすべてのフレーバーには、入力のユニタリが必要です。
このユニタリは、2種類の oracles のいずれかで記述された通常です。

> [!TIP]
> これらのサンプルでは、次に示す oracle の両方の型について説明します。
> 連続クエリ oracles の詳細については、 [ **PhaseEstimation**サンプル](https://github.com/Microsoft/Quantum/tree/master/Samples/src/PhaseEstimation)を参照してください。
> 離散クエリ oracles の詳細については、 [ **IsingPhaseEstimation**サンプル](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingPhaseEstimation)を参照してください。

Oracle の最初の種類は、個別のクエリとして oracle を呼び出し、ユーザー定義型の <xref:microsoft.quantum.oracles.discreteoracle>で表現します。ここでは、単に、インテキスト行列を使用します。
$U $ が、推定する値を持つユニタリの場合、$U $ の oracle は $U $ を実装するサブルーチンの単なるスタンドアロンです。
たとえば、$U $ は、前に定義した振幅推定用の oracle $Q $ になることがあります。
このマトリックスの固有値を使用して、初期状態とターゲット状態の間の重複を推定することができます $ \ sin ^ 2 (quadratically) $。それ以外の場合に必要なサンプルの数を減らすことができます。
これにより、Grover oracle $Q $ を使用して、振幅推定のモニカーを入力として使用して、フェーズ推定の適用を行うことができます。
クォンタム metrology で広く使われているもう1つの一般的なアプリケーションでは、小さな回転角度を推定する必要があります。
言い換えると、$-シータ $ を推定して、フォームの不明な回転ゲート (& z) (\ シータ) $ を $R ます。
このような場合、ゲートの $ \ シータ $ という固定値を学習するために対話するサブルーチンは、$ $ \begin{align} U & = R_z (\ シータ) \\\\ & = \begin{bmatrix} e ^ {-i-シータ/2} & 0 \\\\ 0 & e ^ {i \シータ/2} \end{bmatrix}.
\end{align} $ $

フェーズ推定で使用される oracle の2つ目の種類は、<xref:microsoft.quantum.oracles.continuousoracle> の種類で表される、oracle の連続クエリです。
フェーズ推定のための連続クエリ oracle では、$U (t) $ という形式を使用します。ここで $t $ はクラシックデプロイの既知の実数です。
$ を固定の $U にした場合、連続クエリ oracle では $U (t) = U ^ t $ という形式が使用されます。
これにより、個別のクエリモデルに直接実装できなかった $-sqrt{u} $ などのマトリックスに対してクエリを実行できます。

この種類の oracle は、特定のユニタリを調査していないが、そのために、ユニタリのジェネレーターのプロパティを学習する必要がある場合に役立ちます。
たとえば、dynamical クォンタムのシミュレーションでは、Hermitian $H 行列に対して $U (t) = e ^ {-i H t} $ を厳密に概算したクォンタム回線 ($ と進化時間 $t $) をシミュレートすることを目標としています。
$U (t) $ の固有値は、$H $ の固有値に直接関連付けられています。
これを確認するには、$H $: $H \ket{E} = E\ket {E} $ の eigenvector を考えてみます。これにより、(t) \ket{E} = e ^ {i} \ k {E} = e ^ {-iEt} \ket{E} $ と $U いうマトリックス指数のパワーシリーズ定義から簡単に見ることができます。
したがって、$U (t) $ の eigenphase を推定すると、eigenphase $E $ として eigenvector $ \ket{E} $ がフェーズ推定アルゴリズムに入力されます。
ただし、この場合、$ $t の値はユーザーの裁量で選択できます。これは、$t $ の値が非常に小さい場合 $E $ は $E =-\ phi/t $ を使用して一意に反転できるためです。
クォンタムシミュレーションメソッドでは、小数部の進化を実行する機能が提供されているため、この方法では、単位の推定アルゴリズムによって、(特に、個別のクエリモデルでは、フォームの unitaries $U ^ j $ が許可されます。整数 $j $ に適用するには、連続クエリ oracle を使用すると、実際の値 $t $ に対して、$U ^ t $ という形式の unitaries 概算できます。
これは、$E $; に関する最も多くの情報を提供する実験を正確に選択できるようにするため、フェーズの推定アルゴリズムから効率を上げるために重要です。個別のクエリに基づくメソッドでは、アルゴリズムで最適な数のクエリを選択することによって、危害を加える必要があります。

この具体的な例として、ゲートの回転角度ではなく、クォンタムシステムの procession 周波数を見積もることの問題について考えてみます。
このような量子力学を説明するユニタリは $U (t) = R_z (2 \ オメガ t) $ で、進化時間 $t $ および不明な頻度 $ \ オメガ $ です。
このコンテキストでは、単一 $R z のゲートを使用して、任意の $t $ に対して $U (t) $ をシミュレートできます。そのため、このような場合は、1つのユニタリに対する個別のクエリのみに制限する必要はありません。
このような連続モデルには、対数関数の分岐カットによってマスクされるフェーズ情報があるため、連続したクエリを使用するフェーズ推定プロセスから学習できるプロパティもあります。$t $ の非対応値に対して実行された実験の結果から明らかになります。
このため、このような連続したクエリモデル (フェーズ推定) の場合、oracle は適切なだけでなく、個別のクエリモデルにも適しています。
このため、Q # には両方の形式のクエリの機能があり、ユーザーにそのまま残して、ニーズに合わせてフェーズの推定アルゴリズムを決定し、使用可能な oracle の種類を決定します。

## <a name="dynamical-generator-modeling"></a>Dynamical Generator モデリング ##

時間の経過に伴うジェネレーターは、状態がどのように変化するかを示します。 たとえば、クォンタムの状態 $ \ket{\psi} $ の dynamics は、Schrödinger 式 $ $ \begin{align} i\ frac {d \ket{\psi (t)}} {d t} & = H \ket{\psi (t)}, \end{align} $ $ によって制御されています。 Hermitian matrix $H $、Hamiltonian と呼ばれています。動く. 初期状態が $ \ket{\psi (0)} $ at time $t = $0 の場合、この $t 式に対する正式なソリューションは、$ $ \begin{align} \ket{\psi (t)} = U (t) \ket{\psi (0)}, \end{align} $ $ となります。ここで、マトリックス指数 $U (t) = e ^ {-i H t} $ はと呼ばれます。ユニタリ時間の進化演算子。 次に、このフォームのジェネレーターに焦点を当てていますが、この概念は、開いているクォンタムシステムのシミュレーションや、より抽象的な差分式など、より広範に適用されることを重視しています。

Dynamical シミュレーションの主な目的は、クォンタムコンピューターの qubits でエンコードされたクォンタムの状態に対して進化演算子を実装することです。  多くの場合、Hamiltonian は $d $ より単純な用語の合計に分割されることがあります。

$ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} H_j, \end{align} $ $

各用語による時間の進化は、クォンタムコンピューターで簡単に実装できます。 たとえば、_1X_2 $ 演算子が、qubit レジスタ `qubits`の1番目と2番目の要素に対して動作する $X $ 演算子で $H ある場合、その $t $ は、署名 `Exp([PauliX,PauliX], t, qubits[1..2])`を持つ操作 `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`を呼び出すことによって簡単に実装できます。 Hamiltonian のシミュレーションで後ほど説明するように、1つの解決策として、$H $ による時間の進化にかかる時間を短縮することがあります。

$ $ \begin{align} U (t) & = \ left (e ^ {-iH\_0 t/r} e ^ {-iH\_1 t/r}/cドット e ^ {-iH\_{d-1} t/r} \ 右) ^ {r} + \mathcal{O} (d ^ 2 \) \\|H\_j\\| ^ 2 t ^ 2/r)、\end{align} $ $

> $0 の整数 $r では、近似誤差を制御します。

Dynamical generator モデリングライブラリは、単純なジェネレーターの観点から、複雑なジェネレーターを体系的にエンコードするためのフレームワークを提供します。 そのような説明は、シミュレーションライブラリなどに渡すことによって、選択したシミュレーションアルゴリズムによって時間の進化を実装し、多くの詳細情報が自動的に処理されるようにすることができます。

> [!TIP]
> 以下で説明する dynamical generator ライブラリについては、「」のサンプルを参照してください。 整理モデルに基づく例については、「 [ **isinggenerators**のサンプル](https://github.com/Microsoft/Quantum/tree/master/Samples/src/IsingGenerators)」を参照してください。
> 分子 Hydrogen に基づく例については、 [**H2SimulationCmdLine**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationCmdLine)と[**H2SimulationGUI**](https://github.com/Microsoft/Quantum/tree/master/Samples/src/H2SimulationGUI)のサンプルを参照してください。

### <a name="complete-description-of-a-generator"></a>ジェネレーターの完全な説明 ###

最上位レベルでは、Hamiltonian の完全な説明が、2つのコンポーネントを持つユーザー定義型 `EvolutionGenerator` に含まれています。

```qsharp
newtype EvolutionGenerator = (EvolutionSet, GeneratorSystem);
```

`GeneratorSystem` のユーザー定義型は、Hamiltonian の古典的な説明です。

```qsharp
newtype GeneratorSystem = (Int, (Int -> GeneratorIndex));
```

組の最初の要素 `Int` は、$ $d $ という用語の数を Hamiltonian に格納し、2番目の要素 `(Int -> GeneratorIndex)` は、$\{0, 1,..., d-1\}$ の整数インデックスを一意に識別する `GeneratorIndex` ユーザー定義型にマップする関数です。Hamiltonian のプリミティブ用語。 Hamiltonian では、配列 `GeneratorIndex[]`ではなく関数として用語のコレクションを指定することによって、Hamiltonians を多数の用語で記述する場合に特に便利な、`GeneratorIndex` を実行できるようになります。

とてもでは、`GeneratorIndex` によって識別されるプリミティブ用語についての規則を適用することはできません。 たとえば、前に説明したように、プリミティブな用語は PFermionic の演算子にすることができますが、クォンタムの化学シミュレーションで一般的に使用される annihilation や作成演算子にすることもできます。 `GeneratorIndex` は意味がありません。これは、ポイントした期間による時間の進化が、クォンタム回線として実装されている可能性があるためです。

これは、一部の正規セットから描画されたすべての `GeneratorIndex`を、クォンタム回線として表現される `EvolutionUnitary`である `EvolutionSet` をマップするユーザー定義型を指定することによって解決されます。 `EvolutionSet` は、`GeneratorIndex` の構成方法の規則を定義し、可能な `GeneratorIndex`のセットも定義します。

```qsharp
newtype EvolutionSet = (GeneratorIndex -> EvolutionUnitary);
```

### <a name="pauli-operator-generators"></a>P# li 演算子ジェネレーター ###

ジェネレーターの具体例としては、Hamiltonians 演算子の合計であり、それぞれ異なる係数を持つことがあります。
$ $ \begin{align} H & = \ sum ^ {d-1} _ {j = 0} a_j H_j、\end{align} $ $。各 $ \ hat H_j $ が p Li グループから描画されるようになりました。 このようなシステムでは、`EvolutionSet` 型の `PauliEvolutionSet()` を提供しています。これにより、次のシグネチャを持つ、`GeneratorIndex`によって、Pan Li グループと係数の要素が識別される方法に関する規則が定義されます。

```qsharp
newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```

このエンコードでは、最初のパラメーター `Int[]` は、PI\rightarrow Li 文字列を指定します。ここで、$ & hat $0、$、hat X\rightarrow $1、$/hat Y\rightarrow $2、および $/hat Z\rightarrow $3 です。 2番目のパラメーター `Double[]` は、Hamiltonian 内の p Li 文字列の係数を格納します。 この配列の最初の要素のみが使用されていることに注意してください。 3番目のパラメーターは、この P`Int[]` Li 文字列が処理する qubits のインデックスを作成し、重複する要素を持つことはできません。 したがって、Hamiltonian term $0.4 \ hat X_0 \ hat Y_8\hat I_2\hat Z_1 $ は、

```qsharp
let generatorIndexExample = GeneratorIndex(([1,2,0,3], [0.4]]), [0,8,2,1]);
```

`PauliEvolutionSet()` は、このフォームのすべての `GeneratorIndex` を、次のシグネチャを持つ `EvolutionUnitary` にマップする関数です。

```qsharp
newtype EvolutionUnitary = ((Double, Qubit[]) => Unit is Adj + Ctl);
```

1番目のパラメーターは、時間の長さを表します。これには、`GeneratorIndex`の係数で乗算されます。 2番目のパラメーターは、ユニタリが動作する qubit レジスタです。 

### <a name="time-dependent-generators"></a>時間に依存するジェネレーター ###

多くの場合、モデリングの時間に依存するジェネレーターにも興味があります。これは、Schrödinger 式 $ $ \begin{align} i\ frac {d \ket{\psi (t)}} {d t} & = \ hat H (t) \ket{\psi (t)}, \end{align} $ $ (ジェネレーター $ \ hat H (t) $ が現在) で発生します。時間に依存します。 この場合、上記の時間に依存しないジェネレーターからの拡張機能は簡単です。 $ $T すべての時刻の Hamiltonian を説明する固定 `GeneratorSystem` ではなく、ユーザー定義型 `GeneratorSystemTimeDependent` を使用します。

```qsharp
newtype GeneratorSystemTimeDependent = (Double -> GeneratorSystem);
```

1番目のパラメーターは、[0, 1] $ の連続スケジュールパラメーター $s です。この型の関数は、そのスケジュールの `GeneratorSystem` を返します。 Schedule パラメーターは、$s = t/T $ のような物理時刻パラメーターに線形的に関連付けられている可能性があることに注意してください (例: シミュレーション $T $ の合計時間)。 ただし、通常はそうではありません。

同様に、このジェネレーターの完全な説明には `EvolutionSet`が必要であるため、`EvolutionSchedule` ユーザー定義型を定義します。

```qsharp
newtype EvolutionSchedule = (EvolutionSet, GeneratorSystemTimeDependent);
```
