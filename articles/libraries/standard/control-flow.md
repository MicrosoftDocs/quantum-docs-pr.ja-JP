---
title: 'Q # 標準ライブラリ-制御とフロー |Microsoft Docs'
description: 'Q # 標準ライブラリ-制御とフロー'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5e865dbb48029724b6f507ecb63b85d10d80c9a7
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185649"
---
# <a name="higher-order-control-flow"></a>上位制御フロー #

標準ライブラリの主要な役割の1つは、高レベルのアルゴリズムアイデアを[量子プログラム](https://en.wikipedia.org/wiki/Quantum_programming)として簡単に表現できるようにすることです。
このため、Q # キャノンはさまざまなフロー制御の構成要素を提供しており、それぞれが関数と操作の部分的な適用を使用して実装されています。
すぐに例にジャンプする場合は、レジスタに "CNOT はしご" を構築したいケースを考えてみます。

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

反復および `for` ループを使用して、このパターンを表現できます。

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<xref:microsoft.quantum.arrays.zip>などの <xref:microsoft.quantum.canon.applytoeachca> および配列操作関数の観点から見ると、これははるかに短く、読みやすくなります。

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

このセクションの残りの部分では、canon to コンパクト express クォンタムプログラムによって提供されるさまざまなフロー制御操作と関数の使用方法について、いくつかの例を提供します。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>配列と範囲に対する操作と関数の適用 ##

キャノンによって提供される主な抽象化の1つは、イテレーションのことです。
たとえば、という形式の $U、1つの 1 qubit の $U である $ のような形式のユニタリを使用します。
Q # では、これをレジスタの `for` ループとして表すために <xref:microsoft.quantum.arrays.indexrange> を使用する場合があります。

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation HAll(register : Qubit[]) : Unit 
is Adj + Ctl {

    for (qubit in register) {
        H(qubit);
    }
}
```

次に、この新しい操作を `HAll(register)` として使用して、$H/otimes/cドット/otimes H $ を適用できます。

ただし、特に大きなアルゴリズムでは、これは面倒です。
さらに、この方法は、各 qubit に適用する特定の操作に特化しています。
このアルゴリズムの概念をより明示的に表現するために、操作がファーストクラスであるという事実を使用できます。

```qsharp
ApplyToEachCA(H, register);
```

ここで、サフィックス `CA` は、`ApplyToEach` への呼び出し自体が adjointable で、制御可能であることを示しています。
したがって、`U` が `Adjoint` と `Controlled`をサポートしている場合、次の行は同等です。

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

特に、これは、`ApplyToEachCA` の呼び出しが、adjoint の特殊化が自動生成された操作で使用できることを意味します。
同様に、<xref:microsoft.quantum.canon.applytoeachindex> はフォーム `U(0, targets[0]); U(1, targets[1]); ...`のパターンを表すのに便利です。また、入力によってサポートされる機能の組み合わせごとにバージョンを提供します。

> [!TIP]
> `ApplyToEach` は、`Qubit`以外の入力を受け取る操作で使用できるように、型パラメーター化されています。
> たとえば、`codeBlocks` が、回復する必要がある <xref:microsoft.quantum.errorcorrection.logicalregister> 値の配列であるとします。
> その後 `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` は、エラー修正コード `code` と復旧関数 `recoveryFn` を各ブロックに個別に適用します。
> これは、従来の入力に対しても保持されます。 `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` は、$-pi/$2 の回転を $X $ に対して適用し、$Y $ に関する $pi/$3 の回転を適用します。

また、Q # キャノンでは、関数型プログラミングに慣れている古典的な列挙パターンもサポートしています。
たとえば、<xref:microsoft.quantum.arrays.fold> では、リストに対する関数を減らすために、パターン $f (f (s\_{\ text{initial}, x\_0), x\_1), \ ドット) $ が実装されています。
このパターンを使用すると、合計、製品、最小、最大化、およびその他の機能を実装できます。

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同様に、<xref:microsoft.quantum.arrays.mapped> や <xref:microsoft.quantum.arrays.mappedbyindex> などの関数を使用して、Q # の関数型プログラミングの概念を表現できます。

## <a name="composing-operations-and-functions"></a>操作と関数の作成 ##

キャノンの take 操作および関数によって提供される制御フローの構造を入力として提供します。これにより、複数の操作または関数を1つの呼び出し可能に構成するのに役立ちます。
たとえば、"^ {\ dagger} $ $UVU パターンは、このパターンの抽象化として、キャノンが操作を <xref:microsoft.quantum.canon.applywith> できるように、クォンタムプログラミングで非常によく使用されています。
この抽象化を使用すると、シーケンス `U(qubit); V(qubit); Adjoint U(qubit);` `Controlled` が各 `U`に作用する必要がないので、回線への compliation をより効率的に行うことができます。
これを確認するには、$c (U) $ を `Controlled U([control], target)` を表す1つのユニタリにし、$c (V) $ を同じ方法で定義します。
次に、任意の状態を $ \ket{\psi} $ にします。 \begin{align} c (U) c (V) c (U) ^ \ ダガー \ket{1}/otimes \ket{\psi} & = \ket{1}/otimes (UVU ^ {-dagger} \ket{\psi}) \\\\ & = (& lt;/otimes U) (c (V)) (/U ^ ダガー) \k{1} \ otimes \ket{\psi}.
`Controlled`の定義によって \end{align} ます。
その一方で、\begin{align} c (U) c (V) c (U) ^ \ ダガー \ket{0} \ otimes \ket{\psi} & = \ket{0}-otimes \ket{\psi} \\\\ & = \ket{0}/otimes (UU ^ \ ダガー \ket{\psi}) \\\\ & = (\ bold 完了/otimes U) (c (V)) (\ket) ({times U ^-ダガー){0} otimes \ket{\psi}.
\end{align} によって、すべての入力状態に $U $ out をこの方法で考慮することができます。
つまり、$c (UVU ^ \ ダガー) = U c (V) U ^ \ ダガー $ です。
操作の制御は一般にコストがかかる場合があるため、`WithC` や `WithCA` などの制御されたバリアントを使用すると、適用する必要があるコントロールの数を減らすことができます。

> [!NOTE]
> $U $ をファクタリングするもう1つの結果は、`Controlled` ファンクタを `U`に適用する方法さえわからないことです。
> したがって、`ApplyWithCA` には想定されるほど弱いシグネチャがあります。
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同様に、<xref:microsoft.quantum.canon.bind> は、他の一連の操作を順番に適用する操作を生成します。
たとえば、次のような場合です。

```qsharp
H(qubit); X(qubit);
Bind([H, X], qubit);
```

反復パターンと組み合わせることで、これは特に役に立ちます。

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bind([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>時間順序の構成 ###

それでも、部分的なアプリケーションや従来の関数の観点からフロー制御を検討し、従来のフロー制御の観点からは、非常に高度なクォンタムの概念をモデル化することができます。
この例えは、1つの検索演算子が呼び出し操作の副作用と完全に対応していることを認識することによって正確になります。これは、他のすべての入力演算子の観点では、特定のを構築することに対応するためです。特定のユニタリ演算子として動作する命令を出力する、古典サブルーチンの呼び出しシーケンス。
このビューの下では、`Bind([A, B])(target)` は `A(target); B(target);`と同じであるため、`Bind` はマトリックス製品の正確な表現になります。これは、$BA $ に対応する呼び出し順序です。

より高度な例として、 [Trotter – Suzuki の拡張](https://arxiv.org/abs/math-ph/0506007v1)があります。
[データ構造](xref:microsoft.quantum.libraries.data-structures)の Dynamical Generator 表現に関するセクションで説明したように、Trotter – Suzuki 拡張は、マトリックス指数を表現するために特に便利な方法を提供します。
たとえば、最小の順序で展開を適用すると、$ および $B $ $A の演算子に対して、$A = A ^ \ ダガー $ と $B = B ^ \ ダガー $ のようになります。 \begin{align} \ tag{★} \ label{eq: trotter-suzuki-0} \ exp (i [A + B] t) = (\ exp (i A t/n) \ exp (i B t/n) \ exp (i B t/n) ^ n。
\end{align} 表現では、$A + B $ の下にある状態を、$A $ と $B $ アロンの順に進化させることで、ほぼ進化できることがわかります。
$E ^ {i t A} $ に適用される演算 `A : (Double, Qubit[]) => Unit` によって $A $ の推移を表している場合は、呼び出し元のシーケンスの再配置に関して Trotter – Suzuki 拡張の表現が明確になります。
具体的には、`A = U(0, _, _)` や `B = U(1, _, _)`などの操作 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` した場合、フォームのシーケンスを生成することによって、$ $t $ `U` の整数を表す新しい操作を定義できます。

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

この時点で、Trotter – Suzuki 拡張については、*クォンタムメカニズムをまったく参照する*必要がなくなりました。
拡張は、実質的には $ \eqref{eq: trotter-0} $ によって実現される非常に具体的な反復パターンです。
この反復パターンは <xref:microsoft.quantum.canon.decomposeintotimestepsca>によって実装されます。

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

`DecomposeIntoTimeStepsCA` のシグネチャは、Q # での一般的なパターンに従います。このパターンは、配列またはその場で計算される要素を使用してサポートされるコレクションで、最初の要素が長さを示す値 `Int` する組で表されます。

## <a name="putting-it-together-controlling-operations"></a>まとめ: 操作の制御 ##

最後に、キャノンは、クォンタム操作の条件を追加することによって、`Controlled` ファンクタ上に構築されます。
特に、クォンタムの算術演算では、$ \ket{0\cdots 0} $ 以外の計算ベースの状態に対する条件演算に共通です。
上記の制御操作と関数を使用すると、1つのステートメントでより一般的なクォンタム条件を実行できます。
<xref:microsoft.quantum.canon.controlledonbitstring> について説明します (san の型パラメーター)。その後、1つずつ分割します。
最初に行う必要があるのは、任意の計算基準の状態に対してコントロールを実装する操作を実際に実行する操作を定義することです。
ただし、この操作を直接呼び出すのではなく、名前の先頭に `_` を追加して、他の場所に別のコンストラクトが実装されていることを示します。

```qsharp
operation _ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl),
        controlRegister : Qubit[],
        targetRegister: Qubit[]) 
: Unit 
is Adj + Ctl {
```

`Bool` 配列として表現されるビットの文字列を使用して、指定した `oracle` の操作に適用するエアコンを指定することに注意してください。
この操作では実際にはアプリケーションが直接実行されるため、コントロールとターゲットレジスタを両方とも `Qubit[]`として表す必要があります。

次に、コンピューティングベースの状態を制御することに注意してください $ \ket{\vec{s}} = \ket{s\_0 s\_1、ドット s\_{n-1}} $、ビット文字列 $ \ vec{s} $ は、$ \ket{\vec{s}} $ を $ \ket{0\cdots 0} $ に変換することによって実現できます。
特に、$ \ket{\vec{s}} = X ^ {s\_0} \ otimes X ^ {s\_1}/otimes/cドット/otimes X ^ {s\_{n-1}} \ket{0\cdots 0} $。
$X ^ {\ dagger} = X $ であるため、これは $ \ket{0\dots 0} = X ^ {s\_0}/otimes X ^ {s\_1}/otimes/cドット/otimes X ^ {s\_{n-1}} \ket{\vec{s}} $ であることを意味します。
このため、$P = X ^ {s\_0} \ otimes X ^ {s\_1}/otimes/cドット/otimes X ^ {s\_{n-1}} $ を適用し、`Controlled oracle`を適用してから $ \ vec{s} $ に変換して戻します。
この構築は正確に `ApplyWith`ため、新しい操作の本文を適宜記述します。

```qsharp
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

ここでは、<xref:microsoft.quantum.canon.applypaulifrombitstring> を使用して $P $ を適用し、`ApplyWith`で使用するターゲットに部分的に適用しています。
ただし、*コントロール*レジスタを目的の形式に変換する必要があることに注意してください。そのため、内部操作 `(Controlled oracle)` を*ターゲット*に部分的に適用します。
これにより、必要に応じて、コントロールレジスタを $P $ に角かっこで囲むことが `ApplyWith` されます。

この時点では、これで完了ですが、新しい操作では `Controlled` ファンクタを適用するのと同じように感じられません。
このため、oracle を制御し、新しい操作を返す関数を記述することによって、新しい制御フローの概念を定義します。
このようにして、新しい関数は `Controlled`のように非常によく似ています。 Q # とキャノンを使用して、強力な新しい制御フローコンストラクトを簡単に定義できます。

```qsharp
function ControlledOnBitString(
        bits : Bool[],
        oracle: (Qubit[] => Unit is Adj + Ctl)) 
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
