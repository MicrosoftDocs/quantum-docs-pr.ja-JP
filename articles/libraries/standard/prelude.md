---
title: QDK の組み込みの操作と関数
description: QDK の組み込みの操作と関数について説明します。これには、従来の関数、ユニタリ、ローテーション、測定演算が含まれます。
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907207"
---
# <a name="the-prelude"></a>準備 #

このクォンタム開発キットに含まれる Q # コンパイラとターゲットコンピューターには、Q # でクォンタムプログラムを記述するときに使用できる組み込み関数と操作のセットが用意されています。

## <a name="intrinsic-operations-and-functions"></a>組み込みの操作と関数 ##

標準ライブラリで定義されている組み込み操作は、次のいずれかのカテゴリに分類されます。

- <xref:microsoft.quantum.core> 名前空間で収集される、重要なクラシック関数。
- [Clifford と $T $ ゲート](xref:microsoft.quantum.concepts.qubit)で構成される unitaries を表す操作。
- さまざまな演算子についての回転を表す操作です。
- 測定を実装する操作。

Clifford + $T $ gate セットは、クォンタムコンピューティングでは[universal](xref:microsoft.quantum.concepts.multiple-qubits)であるため、これらの操作では negligibly 小規模エラーの中で、クォンタムアルゴリズムをほぼ実装することができます。
また、回転を提供することにより、プログラマは単一の qubit のユニタリおよび CNOT gate ライブラリ内で作業できるようになります。 このライブラリは、プログラマが Clifford + $T $ 分解を直接表現する必要がないため、また、1つの qubit unitaries を Clifford および $T $ ゲートにコンパイルするための非常に効率的なメソッドが存在するため、より簡単に考えることができます (詳細について[は、こちら](xref:microsoft.quantum.more-information)を参照してください)。

可能であれば、qubits で動作する準備に定義されている操作によって、ターゲットコンピューターが適切な分解を実行するように `Controlled` variant を適用できます。

準備のこの部分で定義されている関数と操作の多くは、@"microsoft.quantum.intrinsic" 名前空間にあります。そのため、ほとんどの Q # ソースファイルには、最初の名前空間宣言の直後にある `open Microsoft.Quantum.Intrinsic;` ディレクティブがあります。
<xref:microsoft.quantum.core> 名前空間が自動的に開かれるため、<xref:microsoft.quantum.core.length> などの関数は、`open` ステートメントをまったく使用せずに使用できます。

### <a name="common-single-qubit-unitary-operations"></a>共通の単一 Qubit の解析操作 ###

準備は、多くの一般的な[シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)も定義します。
これらの操作はすべて、`Controlled` と `Adjoint` の両方の機能を許可します。

#### <a name="pauli-operators"></a>P# li 演算子 ####

<xref:microsoft.quantum.intrinsic.x> 操作は、p Li $X $ 演算子を実装します。
これは、`NOT` ゲートとも呼ばれることもあります。
署名には `(Qubit => Unit is Adj + Ctl)`があります。
これは、単一の qubit のユニタリに対応します。

\ begin{FIXME} \begin{bmatrix} 0 & 1 \\\\%: 現在、quadwhack ハックが使用されています。
1 & 0 \end{bmatrix} です。

<xref:microsoft.quantum.intrinsic.y> 操作は、p Li $Y $ 演算子を実装します。
署名には `(Qubit => Unit is Adj + Ctl)`があります。
これは、単一の qubit のユニタリに対応します。

\ begin{FIXME} \begin{bmatrix} 0 &-i \\\\%: 現在、quadwhack ハックが使用されています。
i & 0 \end{bmatrix} です。

<xref:microsoft.quantum.intrinsic.z> 操作は、p Li $Z $ 演算子を実装します。
署名には `(Qubit => Unit is Adj + Ctl)`があります。
これは、単一の qubit のユニタリに対応します。

\ begin{FIXME} \begin{bmatrix} 1 & 0 \\\\%: 現在、quadwhack ハックが使用されています。
0 &-1 \end{bmatrix} です。

次の例では、これらの変換を[Bloch 球](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere)にマップしています (各ケースの回転軸は赤で強調表示されています)。

![Bloch 球にマップされた p# li 操作](~/media/prelude_pauliBloch.png)

同じ PBloch Li ゲートを同じ qubit に2回適用することは、操作を取り消すことに注意してください (これにより、表面上で2π (360 °) の完全なローテーションが実行され、その結果、開始点に戻ります)。 これにより、次の id が表示されます。

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ bold 完了 $ $

これは、Bloch 球でビジュアルにすることができます。

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>その他のシングル Qubit Cliffords ####

<xref:microsoft.quantum.intrinsic.h> 操作は、Hadamard ゲートを実装します。
このインターチェンジでは、ターゲットの qubit の P\ket Li $X $ 軸と $Z $ 軸が $H{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\ sqrt{2}$ および $H \ket{+} = \ket{0}$ となります。
シグネチャは `(Qubit => Unit is Adj + Ctl)`であり、単一の qubit の場合に対応します。

\ begin{FIXME}/frac{1}{\ sqrt{2}} \begin{bmatrix} 1 & 1 \\\\%: 現在、quadwhack ハックが使用されています。
1 &-1 \end{bmatrix}/end{-1

Hadamard ゲートは、$ \ket{0}$ と $ \ket{1}$ states の法則を作成するために使用できるため、特に重要です。 Bloch 球表現では、これは、$-pi $ ラジアン ($ 180 ^-circ $) によって x 軸を中心とした $ \ket{\psi} $ の回転で、$ pi/2 $ ラジアン ($ 90 ^-circ $) で y 軸を中心とする (時計回りの) 回転であると考えるのが最も簡単です。

![Bloch 球にマップされた Hadamard 操作](~/media/prelude_hadamardBloch.png)

<xref:microsoft.quantum.intrinsic.s> 操作は、$ $S フェーズゲートを実装します。
これは、P# li $Z $ 操作の行列二乗ルートです。
つまり、$S ^ 2 = Z $ です。
シグネチャは `(Qubit => Unit is Adj + Ctl)`であり、単一の qubit の場合に対応します。

\ begin{FIXME} \begin{bmatrix} 1 & 0 \\\\%: 現在、quadwhack ハックが使用されています。
0 & i \end{bmatrix} です。

#### <a name="rotations"></a>回転 ####

上記の P準備 Li および Clifford 操作に加えて、Q # のには、回転を表すさまざまな方法が用意されています。
「[シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)」で説明されているように、ローテーションすることは、クォンタムアルゴリズムにとって重要です。

最初に、$H $ と $T $ ゲートを使用して任意の1つのシングル qubit 操作を表すことができることを呼び出します。 $H ここで、$ は Hadamard 操作、where は \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME: 現在は quad back たたくハックを使用します。
0 & e ^ {i \ pi/4} \end{bmatrix} です。これは、$T ^ 2 = S $ のような <xref:microsoft.quantum.intrinsic.s> 操作の平方根です。
$T $ gate は、<xref:microsoft.quantum.intrinsic.t> 操作によって実装されています。また、`(Qubit => Unit is Adj + Ctl)`シグネチャがあります。これは、これが単一の qubit に対する1回の処理であることを示しています。

これは、任意のシングル qubit 操作を記述するのに十分な原理ですが、準備にはさまざまな方法があるため、さまざまなターゲットマシンで Pauthentication Li 演算子についての回転をより効率的に行うことができます。このような回転を高速にします。
これらの最も基本的な操作は、指定された P# li 軸を中心とした回転を実装する <xref:microsoft.quantum.intrinsic.r> 操作です。 \mathrel{: =} \ exp (-i/phi/シグマ/2),、\ end{の場合は、$/シグマ $ は角度、$ \、$ $ $ exp $ は指数を表します。 $/を指定します (& a) (& a)。
これには `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`のシグネチャがあります。ここで、入力の最初の2つの部分は、$R (-シグマ, \ phi) $ のように、最も前の引数 $-シグマ $ と $/phi $ を表します。
$-シグマ $ と $/phi $ を部分的に適用して、1つの型が単一の qubit の読み込み操作を取得することができます。
たとえば、`R(PauliZ, PI() / 4, _)` には `(Qubit => Unit is Adj + Ctl)`型があります。

> [!NOTE]
> <xref:microsoft.quantum.intrinsic.r> 操作では、入力角度を2で除算し、-1 で乗算します。
> $Z $ ローテーションでは、$ \ket{0}$ eigenstate が $--phi/{1}$2 によって回転され、$ \ket{1}$ eigenstate が $/phi/$2 によって回転されます。これにより、$ $ eigenstate が $ \ket{0}$ eigenstate に対して相対的に $/phi $
>
> 特に、`T` と `R(PauliZ, PI() / 8, _)` は、無関係の[グローバルフェーズ](xref:microsoft.quantum.glossary#global-phase)によってのみ異なることを意味します。
> このため、$T $ は $ \frac{\pi}{8}$-gate とも呼ばれることがあります。
>
> また、`PauliI` を回転させると、単純に $-phi/$2 のグローバルフェーズが適用されることにも注意してください。 このようなフェーズは関係ありませんが、[概念ドキュメント](xref:microsoft.quantum.concepts.qubit)では、制御された `PauliI` のローテーションに関連します。

クォンタムアルゴリズムでは、多くの場合、\mathbb{Z} $ と \mathbb{N} $ での一部の $k \ に対して $-phi = \ pi k/2 ^ n $ $n というように、回転を dyadic の分数として表現すると便利です。
<xref:microsoft.quantum.intrinsic.rfrac> 操作では、この規則を使用して、指定した P# li 軸の周りの回転を実装します。
これは、回転角度が `Int`型の2つの入力として指定され、dyadic の分数として解釈されるという点で <xref:microsoft.quantum.intrinsic.r> とは異なります。
したがって、`RFrac` には `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`シグネチャがあります。
シングル qubit のユニタリ $ \ exp (i-pi k-シグマ/2 ^ n) $ を実装します。 $-シグマ $ は、最初の $k 引数に対応する Pforce Li 行列、$ は2番目の引数、$n $ は3番目の引数です。
`RFrac(_,k,n,_)` は `R(_,-πk/2^n,_)`と同じです。角度は、分数の*負の値*であることに注意してください。

<xref:microsoft.quantum.intrinsic.rx> 操作は、$X $ 軸を中心とした回転を実装します。
署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。
`Rx(_, _)` は `R(PauliX, _, _)`と同じです。

<xref:microsoft.quantum.intrinsic.ry> 操作は、$Y $ 軸を中心とした回転を実装します。
署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。
`Ry(_, _)` は `R(PauliY,_ , _)`と同じです。

<xref:microsoft.quantum.intrinsic.rz> 操作は、$Z $ 軸を中心とした回転を実装します。
署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。
`Rz(_, _)` は `R(PauliZ, _, _)`と同じです。

<xref:microsoft.quantum.intrinsic.r1> 操作では、$ \ket{1}$ の $Z $-$1 eigenstate を中心に、指定された量の回転を実装します。
署名には `((Double, Qubit) => Unit is Adj + Ctl)`があります。
`R1(phi,_)` は `R(PauliZ,phi,_)` の後に続く `R(PauliI,-phi,_)`と同じです。

<xref:microsoft.quantum.intrinsic.r1frac> 操作は、Z = 1 eigenstate に対して指定された量だけ、小数部の回転を実装します。
署名には `((Int,Int, Qubit) => Unit is Adj + Ctl)`があります。
`R1Frac(k,n,_)` は `RFrac(PauliZ,-k.n+1,_)` の後に続く `RFrac(PauliI,k,n+1,_)`と同じです。

Bloch 球にマップされた (このインスタンスの p Li $Z $ axis を中心とした) 回転操作の例を次に示します。

![Bloch 球にマップされた回転操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>マルチ Qubit 操作 ####

準備では、上記のシングル qubit 操作に加えて、複数のマルチ qubit 操作も定義します。

まず、<xref:microsoft.quantum.intrinsic.cnot> 操作は、標準の制御された`NOT` ゲートを実行します。 \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.
& # {unitarily} には、`((Qubit, Qubit) => Unit is Adj + Ctl)`シグネチャがあります。これは、$-name{cnot} $ が2つの個別の qubits で動作することを表します。
`CNOT(q1, q2)` は `(Controlled X)([q1], q2)`と同じです。
`Controlled` のファンクタではレジスタの制御が可能であるため、配列リテラル `[q1]` を使用して、1つのコントロールのみが必要であることを示します。

<xref:microsoft.quantum.intrinsic.ccnot> 操作では、二重制御された NOT gate (Toffoli ゲートとも呼ばれます) を実行します。
署名には `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`があります。
`CCNOT(q1, q2, q3)` は `(Controlled X)([q1, q2], q3)`と同じです。

<xref:microsoft.quantum.intrinsic.swap> 操作は、2つの qubits のクォンタム状態を交換します。
つまり、このメソッドは、ユニタリ行列を実装します。 \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}. になります。
& end{の場合は、署名 `((Qubit, Qubit) => Unit is Adj + Ctl)`ます。
`SWAP(q1,q2)` は、`CNOT(q1, q2)` の後に `CNOT(q2, q1)` を付けてから `CNOT(q1, q2)`することと同じです。

> [!NOTE]
> スワップゲートは、変数の要素を `Qubit[]`型で再配置するのと同じでは*ありません*。
> `SWAP(q1, q2)` を適用すると、`q1` と `q2`によって参照される qubits の状態が変更されますが、`let swappedRegister = [q2, q1];` はこれらの qubits を参照する方法にのみ影響します。
> さらに、`(Controlled SWAP)([q0], (q1, q2))` では、`SWAP` を3番目の qubit の状態に設定できます。これは、要素を再配置することでは表現できません。
> Fredkin gate とも呼ばれる、制御されたスワップゲートは、すべての従来の計算を含めるのに十分な性能を備えています。

最後に、準備には、マルチ qubit の指数演算子を表す2つの操作が用意されています。
<xref:microsoft.quantum.intrinsic.exp> 操作では、複数の Pforce Li マトリックスの製品に基づいて回転を実行します。これには、マルチ qubit の場合は、(-vec{/sigma}) という形式で表されます。 \ phi) \mathrel{: =} \ left (i/phi \ sigma_0/otimes \ sigma_1 \ sigma_n)、\ end{-& lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; $ & lt; sigma_0 \ sigma_1, \ ドット, \ sigma_n) $ は、single qubit の一連の演算子で、$ \ phi $ は角度を表します。
`Exp` ローテーションは、シグネチャ `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`を持つように、`Pauli` 要素の配列として $ \ vec{{sigma} $ を表します。

<xref:microsoft.quantum.intrinsic.expfrac> 操作では、上で説明した dyadic の小数点表記法を使用して、同じローテーションを実行します。
署名には `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`があります。

> [!WARNING]
> 指数演算子のすべての操作は、指数または p Li オペレーターのの製品と同じではありません。
> つまり、$e ^ {i (Z/otimes Z) \phi} \n e e ^ {i Z \phi}/otimes e ^ {i Z \phi} $。

### <a name="measurements"></a>測定 ###

測定する場合、測定される演算子の + 1 eigenvalue は、`Zero` の結果に対応し、-1 eigenvalue が `One` の結果になります。

> [!NOTE]
> この規則は奇妙に見えるかもしれませんが、非常に便利な2つの利点があります。
> 最初に、結果 $ \ket{0}$ が `Result` 値 `Zero`によって表されます。一方、$ \ket{1}$ は `One`に相当します。
> 2つ目の方法として、結果に対応する eigenvalue $/ラムダ $ を、$ is $ \ ラムダ = (-1) ^ r $ という $r に記述できます。

測定操作は、`Adjoint` も `Controlled` のファンクタもサポートしていません。

<xref:microsoft.quantum.intrinsic.measure> 操作では、指定された P# li 演算子の積で1つ以上の qubits の結合測定を実行します。
P# li 配列と qubit 配列の長さが異なる場合、操作は失敗します。
`Measure` に署名 `((Pauli[], Qubit[]) => Result)`があります。

ジョイント測定は、各 qubit を個別に測定するのと同じではないことに注意してください。
たとえば、state $ \ket{11} = \ket{1} \ otimes \ket{1} = xotimes X \ket{00}$ とします。
各 $Z 0 $ と $Z _1 $ を個別に測定すると、$r 0 = $1 および $r _1 = $1 の結果が得られます。
$Z 0 Z_1 $ を測定すると、1つの結果 $r _ {\textrm{joint}} = $0 となり、$ \ket{11}$ の pairity が正であることを表します。
異なる形式で、$ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $ と指定します。
非常に大きなことですが、この測定からはパリティを学習する*だけ*なので、法則に示されている、正のパリティの 2 2-qubit の状態間のクォンタム情報 ($ \ket{00}$ と $ \ket{11}$) は保持されます。
このプロパティは、エラー修正について説明するため、後で必要になります。

便宜上、準備には、qubits を測定するための他の2つの操作も用意されています。
まず、single qubit の測定を実行するのは非常に一般的であるため、準備はこの場合の短縮形を定義します。
<xref:microsoft.quantum.intrinsic.m> 操作では、1つの qubit に対して p Li $Z $ 演算子を測定し、シグネチャ `(Qubit => Result)`を持ちます。
`M(q)` は `Measure([PauliZ], [q])` に相当します。

<xref:microsoft.quantum.measurement.multim> は、qubits の各配列で*個別*に p li $Z $ 演算子を測定し、各 qubits に対して取得された `Result` 値の*配列*を返します。
場合によっては、これを最適化することができます。 署名があります (`Qubit[] => Result[])`。
`MultiM(qs)` は、次の場合と同じです。

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>拡張関数と操作 ##

さらに、準備は、Q # コード内で使用するために、.NET レベルで数学的および型変換関数の豊富なセットを定義します。
たとえば、<xref:microsoft.quantum.extensions.math> 名前空間は、<xref:microsoft.quantum.extensions.math.sin> や <xref:microsoft.quantum.extensions.math.log>などの便利な操作を定義します。
Quantum 開発キットによって提供される実装では、従来の .NET 基底クラスライブラリを使用します。そのため、quantum プログラムとその典型的なドライバーの間で、追加の通信ラウンドトリップが必要になる場合があります。
これによってローカルシミュレーターに問題が発生することはありませんが、リモートシミュレーターまたは実際のハードウェアをターゲットコンピューターとして使用すると、パフォーマンスの問題が発生する可能性があります。
ただし、個々のターゲットコンピューターは、このような操作を特定のシステムにとってより効率的なバージョンで上書きすることによって、このパフォーマンスへの影響を軽減することができます。

### <a name="math"></a>算術 ###

<xref:microsoft.quantum.extensions.math> 名前空間には、.NET 基本クラスライブラリの[`System.Math` クラス](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)の便利な関数が多数用意されています。
これらの関数は、他の Q # 関数と同じ方法で使用できます。

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

.NET の静的メソッドが引数の型に基づいてオーバーロードされている場合、対応する Q # 関数には、入力の型を示すサフィックスで注釈が付けられます。

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>ビットごとの演算 ###

最後に、<xref:microsoft.quantum.extensions.bitwise> 名前空間には、ビットごとの演算子で整数を操作するための便利な関数がいくつか用意されています。
たとえば、<xref:microsoft.quantum.extensions.bitwise.parity> は、整数のビットごとのパリティを別の整数として返します。
