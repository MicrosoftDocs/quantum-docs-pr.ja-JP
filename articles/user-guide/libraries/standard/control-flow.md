---
title: Q#標準 libararies フロー制御
description: Microsoft 標準ライブラリのフロー制御操作と関数について説明し Q# ます。
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: ad107f5c65a4bf368d12d30e4a72786f2076205c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690872"
---
# <a name="higher-order-control-flow"></a>Higher-Order 制御フロー #

標準ライブラリの主要な役割の1つは、高レベルのアルゴリズムアイデアを [量子プログラム](https://en.wikipedia.org/wiki/Quantum_programming)として簡単に表現できるようにすることです。
そのため、 Q# キャノンはさまざまなフロー制御の構成要素を提供しており、それぞれが関数と操作の部分的な適用を使用して実装されています。
すぐに例にジャンプする場合は、レジスタに "CNOT はしご" を構築したいケースを考えてみます。

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

繰り返しとループを使用して、このパターンを表現でき `for` ます。

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

ただし、などの <xref:Microsoft.Quantum.Canon.ApplyToEachCA> および配列操作関数で表現 <xref:Microsoft.Quantum.Arrays.Zipped> されますが、これははるかに短く、読みやすくなります。

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

このセクションの残りの部分では、canon to コンパクト express クォンタムプログラムによって提供されるさまざまなフロー制御操作と関数の使用方法について、いくつかの例を提供します。

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a>配列と範囲に対する操作と関数の適用 ##

キャノンによって提供される主な抽象化の1つは、イテレーションのことです。
たとえば、という形式の $U、1つの 1 qubit の $U である $ のような形式のユニタリを使用します。
では Q# 、を使用し <xref:Microsoft.Quantum.Arrays.IndexRange> て、これをレジスタに対するループとして表すことができ `for` ます。

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

その後、この新しい操作を使用して、$H/otimes/cドット/otimes `HAll(register)` h $ に適用できます。

ただし、特に大きなアルゴリズムでは、これは面倒です。
さらに、この方法は、各 qubit に適用する特定の操作に特化しています。
このアルゴリズムの概念をより明示的に表現するために、操作がファーストクラスであるという事実を使用できます。

```qsharp
ApplyToEachCA(H, register);
```

ここで、サフィックスは、 `CA` への呼び出し `ApplyToEach` がそれ自体が adjointable で、制御可能であることを示しています。
したがって、 `U` で `Adjoint` とがサポートされている場合、 `Controlled` 次の行が同等になります。

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

特に、これは、 `ApplyToEachCA` adjoint の特殊化が自動生成される操作に、の呼び出しが表示される可能性があることを意味します。
同様に、 <xref:Microsoft.Quantum.Canon.ApplyToEachIndex> は、フォームのパターンを表すのに便利です。また、は、 `U(0, targets[0]); U(1, targets[1]); ...` 入力でサポートされている機能の組み合わせごとにバージョンを提供します。

> [!TIP]
> `ApplyToEach` は、以外の入力を受け取る操作で使用できるように、型指定されたパラメーターです `Qubit` 。
> たとえば、 `codeBlocks` が復旧する必要がある値の配列であるとし <xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister> ます。
> 次に `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 、エラー修正コード `code` と復旧関数 `recoveryFn` を各ブロックに個別に適用します。
> これは、従来の入力に対しても保持されます。で `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` は、$-pi/$2 の回転が $X $ に対して適用され、$Y $ に関する $pi/$3 の回転が適用されます。

また、キャノンでは、 Q# 関数型プログラミングに慣れている古典的な列挙パターンもサポートしています。
たとえば、は、 <xref:Microsoft.Quantum.Arrays.Fold> リストに対して関数を縮小するために、パターン $f (f (s \_ {\ text{\ text{\ text{\ text{\ text{\ text{\ text{\ text{\ text{\ text{/text{\), \_ \_ \ ドット) $) を実装します。
このパターンを使用すると、合計、製品、最小、最大化、およびその他の機能を実装できます。

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

同様に、やなどの関数を <xref:Microsoft.Quantum.Arrays.Mapped> 使用して、 <xref:Microsoft.Quantum.Arrays.MappedByIndex> の関数型プログラミングの概念を表現でき Q# ます。

## <a name="composing-operations-and-functions"></a>操作と関数の作成 ##

キャノンの take 操作および関数によって提供される制御フローの構造を入力として提供します。これにより、複数の操作または関数を1つの呼び出し可能に構成するのに役立ちます。
たとえば、"^ {\ dagger} $ $UVU パターンは、 <xref:Microsoft.Quantum.Canon.ApplyWith> このパターンの抽象化として、キャノンが操作を提供するクォンタムプログラミングで非常に一般的です。
この抽象化を使用すると、 `Controlled` シーケンスに対して動作 `U(qubit); V(qubit); Adjoint U(qubit);` する必要がないので、回線への compliation をより効率的に行うことができ `U` ます。
これを確認するには、$c (U) $ を表す、 `Controlled U([control], target)` $c (V) $ を同じ方法で定義します。
次に、任意の状態を $ \ket{\psi} $ にします。 \begin{align} c (U) c (V) c (U) ^ \ ダガー \ket/ {1} otimes \ket{\psi} & = \ket/ {1} otimes (uvu ^ {-dagger} \ket{\psi}) \\ \\ & = (\ bold 完了 \ otimes u) (c (V)) (\ bold Done/otimes u ^ ダガー) \ket/ {1} otimes \ket{\psi}.
の定義によって \end{align} `Controlled` ます。
一方、\begin{align} c (U) c (V) c (U) ^ \ ダガー \ket/ {0} otimes \ket{\psi} & = \ket/otimes {0} \ket{\psi} \\ \\ & = \ket/ {0} otimes (UU ^ \ ダガー \ket{\psi}) \\ \\ & = (\ bold done/Otimes u) (c (V)) (\ bold done/otimes u ^) \ket、 {0} otimes \ket{\psi}.
\end{align} によって、すべての入力状態に $U $ out をこの方法で考慮することができます。
つまり、$c (UVU ^ \ ダガー) = U c (V) U ^ \ ダガー $ です。
操作の制御は一般にコストがかかる場合があるため、やなどの制御されたバリアントを使用する `WithC` と、 `WithCA` 適用する必要があるコントロールの数を減らすことができます。

> [!NOTE]
> $U $ をファクタリングするもう1つの結果は、ファンクタをに適用する方法さえわからないことです `Controlled` `U` 。
> `ApplyWithCA` したがって、想定されるほど弱いシグネチャがあります。
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

同様に、は、 <xref:Microsoft.Quantum.Canon.Bound> 他の一連の操作を順番に適用する操作を生成します。
たとえば、次のような場合です。

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

反復パターンと組み合わせることで、これは特に役に立ちます。

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a>Time-Ordered コンポジション ###

それでも、部分的なアプリケーションや従来の関数の観点からフロー制御を検討し、従来のフロー制御の観点からは、非常に高度なクォンタムの概念をモデル化することができます。
このような類似性は、順序付け演算子が呼び出し操作の副作用と完全に対応していることを認識することによって正確になります。これは、他のすべての入力演算子の観点からの特定の呼び出しシーケンスを作成して、特定の順番演算子として動作するための命令を出力する従来のサブルーチンの呼び出しシーケンスを作成する
このビューでは、はマトリックス製品を正確に表したものです。これは、 `Bound` `Bound([A, B])(target)` がと等価であり、 `A(target); B(target);` さらに、$BA $ に対応する呼び出しシーケンスです。

より高度な例として、 [Trotter – Suzuki の拡張](https://arxiv.org/abs/math-ph/0506007v1)があります。
[データ構造](xref:microsoft.quantum.libraries.data-structures)の Dynamical Generator 表現に関するセクションで説明したように、Trotter – Suzuki 拡張は、マトリックス指数を表現するために特に便利な方法を提供します。
たとえば、最小の順序で展開を適用すると、$ および $B $ $A の演算子に対して、$A = A ^ \ ダガー $ と $B = B ^ \ ダガー $ のようになります。 \begin{align} \ tag{★} \ label{eq: trotter-suzuki-0} \ exp (i [A + B] t) = \ lim_ {n}/left (\ exp (i A t/n) \ exp (i B t/n)) ^ n
\end{align} 表現では、$A + B $ の下にある状態を、$A $ と $B $ アロンの順に進化させることで、ほぼ進化できることがわかります。
$A $ の下で、 `A : (Double, Qubit[]) => Unit` ^ {i t A} $ $e 適用される操作によって進化が示されている場合は、呼び出しシーケンスの再配置に関して Trotter – Suzuki 拡張の表現が明確になります。
具体的には、となどの操作を指定した場合、 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` `A = U(0, _, _)` `B = U(1, _, _)` `U` フォームのシーケンスを生成することにより、time $t $ の整数を表す新しい操作を定義できます。

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

この時点で、Trotter – Suzuki 拡張については、 *クォンタムメカニズムをまったく参照する* 必要がなくなりました。
拡張は、実質的には $ \eqref{eq: trotter-0} $ によって実現される非常に具体的な反復パターンです。
この反復パターンは、次の方法で実装され <xref:Microsoft.Quantum.Canon.DecomposedIntoTimestepsCA> ます。

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

のシグネチャは `DecomposeIntoTimeStepsCA` 、の一般的なパターンに従います Q# 。ここでは、配列またはその場で計算される要素を使用してサポートされるコレクションは、最初の要素が長さを示す値である組によって表され `Int` ます。

## <a name="putting-it-together-controlling-operations"></a>まとめ: 操作の制御 ##

最後に、キャノンは、 `Controlled` クォンタム操作の条件を追加する方法を提供することで、ファンクタ上に構築されます。
特に、クォンタムの算術演算では、$ \ket{0\cdots 0} $ 以外の計算ベースの状態に対する条件演算に共通です。
上記の制御操作と関数を使用すると、1つのステートメントでより一般的なクォンタム条件を実行できます。
で <xref:Microsoft.Quantum.Canon.ControlledOnBitString> は、そのしくみ (san の種類のパラメーター) に移動して、1つずつ分割します。
最初に行う必要があるのは、任意の計算基準の状態に対してコントロールを実装する操作を実際に実行する操作を定義することです。
ただし、この操作を直接呼び出すのではなく、 `_` 名前の先頭にを追加して、他の場所にある別の構造体の実装であることを示します。

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

`Bool`指定した操作に適用するエアコンを指定するために使用する、配列として表現されたビットの文字列を使用し `oracle` ます。
この操作では実際にアプリケーションが直接実行されるため、コントロールとターゲットレジスタを両方とも使用する必要があり `Qubit[]` ます。

次に、 \_ $ \ket{\vec{s}} $ を $ \ket{0\cdots 0} $ に変換することによって、計算基準の状態が $ \ket{\vec{s}} = \ket{s 0 s \_ 1 \ ドット s \_ {n-1}} $ に対する制御が実現することに注意してください。
具体的には、$ \ket{\vec{s}} = X ^ {s \_ 0} \ Otimes x ^ {s \_ 1} \ otimes/cドット/otimes x ^ {s \_ {n-1}} \ket{0\cdots 0} $。
$X ^ {\ dagger} = X $ であるため、これは $ \ket{0\dots 0} = X ^ {s \_ 0}-Otimes x ^ {s 1} \ otimes/ \_ cドット/Otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $ であることを意味します。
これにより、$P = X ^ {s \_ 0} \ Otimes x ^ {s \_ 1}/otimes/cドット/otimes x ^ {s \_ {n-1}} $ を適用し、$- `Controlled oracle` vec{s} $ に変換して戻すことができます。
この構築は正確 `ApplyWith` であるため、新しい操作の本文をそれに応じて記述します。

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

ここでは、 <xref:Microsoft.Quantum.Canon.ApplyPauliFromBitString> で使用するために、$P $ を適用し、そのターゲットに部分的に適用してい `ApplyWith` ます。
ただし、 *コントロール* レジスタを目的の形式に変換する必要があることに注意してください。したがって、内部操作はターゲットに部分的に適用され `(Controlled oracle)` ます。 *target*
これ `ApplyWith` により、必要に応じて、コントロールレジスタが $P $ に角かっこで囲みます。

この時点では、これで完了ですが、新しい操作では、ファンクタを適用するような "感覚" にならないということがわかりません `Controlled` 。
このため、oracle を制御し、新しい操作を返す関数を記述することによって、新しい制御フローの概念を定義します。
このように、新しい関数は、 `Controlled` とキャノンを使用して強力な新しい制御フローコンストラクトを簡単に定義できることを示してい Q# ます。

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
