---
title: QDK の組み込みの操作と関数
description: QDK の組み込みの操作と関数について説明します。これには、従来の関数、ユニタリ、ローテーション、測定演算が含まれます。
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd507d0c644ae711a5e5a1dff9156f571cb0fa92
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833546"
---
# <a name="the-prelude"></a>準備 #

Q#クォンタム開発キットに含まれているコンパイラとターゲットコンピューターには、でクォンタムプログラムを記述するときに使用できる組み込み関数と操作のセットが用意されて Q# います。

## <a name="intrinsic-operations-and-functions"></a>組み込みの操作と関数 ##

標準ライブラリで定義されている組み込み操作は、次のいずれかのカテゴリに分類されます。

- 名前空間で収集される、基本的な従来の関数 <xref:microsoft.quantum.core> 。
- [Clifford と $T $ ゲート](xref:microsoft.quantum.concepts.qubit)で構成される unitaries を表す操作。
- さまざまな演算子についての回転を表す操作です。
- 測定を実装する操作。

Clifford + $T $ gate セットは、クォンタムコンピューティングでは [universal](xref:microsoft.quantum.concepts.multiple-qubits) であるため、これらの操作では negligibly 小規模エラーの中で、クォンタムアルゴリズムをほぼ実装することができます。
また、回転も提供することにより、 Q# プログラマは単一の qubit のユニタリおよび CNOT gate ライブラリ内で作業できるようになります。 このライブラリは、プログラマが Clifford + $T $ 分解を直接表現する必要がないため、また、1つの qubit unitaries を Clifford および $T $ ゲートにコンパイルするための非常に効率的なメソッドが存在するため、より簡単に考えることができます (詳細について [は、こちら](xref:microsoft.quantum.more-information) を参照してください)。

可能であれば、qubits で動作する準備に定義されている操作によって、 `Controlled` ターゲットコンピューターが適切な分解を実行するように、バリアントを適用できます。

準備のこの部分で定義されている関数と操作の多くは @"microsoft.quantum.intrinsic" 名前空間にあります。そのため、ほとんどのソースファイルには、 Q# `open Microsoft.Quantum.Intrinsic;` 最初の名前空間宣言の直後にディレクティブがあります。
<xref:microsoft.quantum.core>名前空間は自動的に開かれるため、などの関数を <xref:microsoft.quantum.core.length> ステートメントなしで使用することもでき `open` ます。

### <a name="common-single-qubit-unitary-operations"></a>共通の単一 Qubit の解析操作 ###

準備は、多くの一般的な [シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)も定義します。
これらの操作では、との両方の機能を使用でき `Controlled` `Adjoint` ます。

#### <a name="pauli-operators"></a>P# li 演算子 ####

操作は、 <xref:microsoft.quantum.intrinsic.x> $X $ 演算子を実装します。
これは、ゲートとも呼ばれ `NOT` ます。
署名があり `(Qubit => Unit is Adj + Ctl)` ます。
これは、単一の qubit のユニタリに対応します。

\begin{bmatrix} 0 & 1 \\ \\ % FIXME: 現在、quadwhack ハックを使用しています。
1 & 0 \end{bmatrix} です。

操作は、 <xref:microsoft.quantum.intrinsic.y> $Y $ 演算子を実装します。
署名があり `(Qubit => Unit is Adj + Ctl)` ます。
これは、単一の qubit のユニタリに対応します。

\begin{bmatrix} 0 &-i \\ \\ % FIXME: 現在、quadwhack ハックを使用しています。
i & 0 \end{bmatrix} です。

操作は、 <xref:microsoft.quantum.intrinsic.z> $Z $ 演算子を実装します。
署名があり `(Qubit => Unit is Adj + Ctl)` ます。
これは、単一の qubit のユニタリに対応します。

\begin{bmatrix} 1 & 0 \\ \\ % FIXME: 現在、quadwhack ハックが使用されています。
0 &-1 \end{bmatrix} です。

次の例では、これらの変換を [Bloch 球](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) にマップしています (各ケースの回転軸は赤で強調表示されています)。

![Bloch 球にマップされた p# li 操作](~/media/prelude_pauliBloch.png)

同じ PBloch Li ゲートを同じ qubit に2回適用することは、操作を取り消すことに注意してください (これにより、表面上で2π (360 °) の完全なローテーションが実行され、その結果、開始点に戻ります)。 これにより、次の id が表示されます。

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \ bold 完了 $ $

これは、Bloch 球でビジュアルにすることができます。

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>その他のシングル Qubit Cliffords ####

操作は、 <xref:microsoft.quantum.intrinsic.h> Hadamard ゲートを実装します。
このインターチェンジは、target qubit の P\ket Li $X $ 軸と $Z $ 軸を $H、 {0} \ket {0} + \ket {1} )/\ sqrt {2} $ と $H \ket{+} = \ket $ というように {0} なります。
このファイルにはシグネチャがあり、 `(Qubit => Unit is Adj + Ctl)` 1 つの qubit の場合に対応します。

\ begin{FIXME}/frac {1} {\ sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ %: 現在、quadwhack ハックが使用されています。
1 &-1 \end{bmatrix}/end{-1

Hadamard ゲートは、$ \ket {0} $ と $ \ket $ の状態の法則を作成するために使用できるため、特に重要です {1} 。 Bloch 球表現では、これは、$-pi $ ラジアン ($ 180 ^-circ $) によって x 軸を中心とした $ \ket{\psi} $ の回転で、$ pi/2 $ ラジアン ($ 90 ^-circ $) で y 軸を中心とする (時計回りの) 回転であると考えるのが最も簡単です。

![Bloch 球にマップされた Hadamard 操作](~/media/prelude_hadamardBloch.png)

操作は、 <xref:microsoft.quantum.intrinsic.s> $ $S フェーズゲートを実装します。
これは、P# li $Z $ 操作の行列二乗ルートです。
つまり、$S ^ 2 = Z $ です。
このファイルにはシグネチャがあり、 `(Qubit => Unit is Adj + Ctl)` 1 つの qubit の場合に対応します。

\begin{bmatrix} 1 & 0 \\ \\ % FIXME: 現在、quadwhack ハックが使用されています。
0 & i \end{bmatrix} です。

#### <a name="rotations"></a>ローテーション ####

上記の P準備 Li および Clifford 操作に加えて、 Q# 回転を表現するさまざまな方法が用意されています。
「 [シングル qubit 操作](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)」で説明されているように、ローテーションすることは、クォンタムアルゴリズムにとって重要です。

最初に、$H $ と $T $ ゲートを使用して任意の1つの Hadamard 操作を表すことができることを呼び出します。ここで、$H $ は操作、where は \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % FIXME: 現在は quad back たたくハックを使用します。
0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:microsoft.quantum.intrinsic.s> operation, such that $T^2 = S$.
$T $ gate は、操作によって実装されてい <xref:microsoft.quantum.intrinsic.t> `(Qubit => Unit is Adj + Ctl)` ます。また、このメソッドは、単一の qubit に対する1つのユニタリ操作であることを示すシグネチャを持っています。

これは、任意のシングル qubit 操作を記述するのに十分な原則ですが、準備には、このような回転を実現するさまざまな方法が用意されているため、異なるターゲットコンピューターでは、Pauthentication Li 演算子についての回転をより効率的に行うことができます。
これらの最も基本的な操作は、 <xref:microsoft.quantum.intrinsic.r> 指定された P# li 軸を中心とした回転を実装する操作です。 \mathrel{: =} \ exp (-i/phi/シグマ/2),、\ end{の場合は、$/シグマ $ は角度、$ \、$ $ $ exp $ は指数を表します。 $/を指定します (& a) (& a)。
これにはシグネチャがあります `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` 。ここで、入力の最初の2つの部分は、(-シグマ, + phi) $ という、ユニタリ演算子 $R を指定するために必要な従来の引数 $/シグマ $ と $ ¥ phi $ を表します。
$-シグマ $ と $/phi $ を部分的に適用して、1つの型が単一の qubit の読み込み操作を取得することができます。
たとえば、に `R(PauliZ, PI() / 4, _)` は型があり `(Qubit => Unit is Adj + Ctl)` ます。

> [!NOTE]
> この操作では、 <xref:microsoft.quantum.intrinsic.r> 入力角度を2で除算し、-1 で乗算します。
> $Z $ ローテーションの場合、これは $ \ket {0} $ eigenstate が $--phi/$2 で回転し、$ \ket $ eigenstate が $/phi/$2 によってローテーションされることを意味し {1} ます。これにより、$ \ket $ eigenstate は $ {1} \ket {0} $ eigenstate に対して相対的に $/phi $ で
>
> 特に、 `T` とは無関係な `R(PauliZ, PI() / 8, _)` [グローバルフェーズ](xref:microsoft.quantum.glossary#global-phase)によってのみ異なることを意味します。
> このため、$T $ は $ \frac{\pi} $-gate と呼ばれることもあり {8} ます。
>
> また、回転によって `PauliI` 、単に $/phi/$2 のグローバルフェーズが適用されることにも注意してください。 このようなフェーズは、 [概念的なドキュメント](xref:microsoft.quantum.concepts.qubit)の場合とは無関係ですが、制御された回転に関連し `PauliI` ます。

クォンタムアルゴリズムでは、多くの場合、\mathbb{Z} $ と \mathbb{N} $ での一部の $k \ に対して $-phi = \ pi k/2 ^ n $ $n というように、回転を dyadic の分数として表現すると便利です。
操作は、 <xref:microsoft.quantum.intrinsic.rfrac> この規則を使用して、指定された P# li 軸を中心とした回転を実装します。
これは、 <xref:microsoft.quantum.intrinsic.r> 回転角度が、 `Int` dyadic の割合として解釈される型の2つの入力として指定されている点で異なります。
このため、に `RFrac` はシグネチャがあり `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` ます。
シングル qubit のユニタリ $ \ exp (i-pi k-シグマ/2 ^ n) $ を実装します。 $-シグマ $ は、最初の $k 引数に対応する Pforce Li 行列、$ は2番目の引数、$n $ は3番目の引数です。
`RFrac(_,k,n,_)` はと同じです。 `R(_,-πk/2^n,_)` 角度は分数の負の *値* であることに注意してください。

操作は、 <xref:microsoft.quantum.intrinsic.rx> $X $ 軸に対する回転を実装します。
署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。
`Rx(_, _)` は `R(PauliX, _, _)` と同じです。

操作は、 <xref:microsoft.quantum.intrinsic.ry> $Y $ 軸に対する回転を実装します。
署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。
`Ry(_, _)` は `R(PauliY,_ , _)` と同じです。

操作は、 <xref:microsoft.quantum.intrinsic.rz> $Z $ 軸に対する回転を実装します。
署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。
`Rz(_, _)` は `R(PauliZ, _, _)` と同じです。

操作は、$ <xref:microsoft.quantum.intrinsic.r1> \ket $ に対して指定された量の回転を実装し {1} ます。これは $Z $ の $-$1 eigenstate です。
署名があり `((Double, Qubit) => Unit is Adj + Ctl)` ます。
`R1(phi,_)` は、の `R(PauliZ,phi,_)` 後に続くと同じです `R(PauliI,-phi,_)` 。

操作は、 <xref:microsoft.quantum.intrinsic.r1frac> Z = 1 eigenstate に対して指定された量だけ、小数部の回転を実装します。
署名があり `((Int,Int, Qubit) => Unit is Adj + Ctl)` ます。
`R1Frac(k,n,_)` は、の `RFrac(PauliZ,-k.n+1,_)` 後に続くと同じです `RFrac(PauliI,k,n+1,_)` 。

Bloch 球にマップされた (このインスタンスの p Li $Z $ axis を中心とした) 回転操作の例を次に示します。

![Bloch 球にマップされた回転操作](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>マルチ Qubit 操作 ####

準備では、上記のシングル qubit 操作に加えて、複数のマルチ qubit 操作も定義します。

1つ目の操作では、標準の制御され <xref:microsoft.quantum.intrinsic.cnot> た `NOT` ゲート、& begin{\mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}. を実行します。
\ end{eation} 署名が含ま `((Qubit, Qubit) => Unit is Adj + Ctl)` れています。これは、$-unitarily name{cnot} $ が2つの個別の qubits で動作することを表します。
`CNOT(q1, q2)` は `(Controlled X)([q1], q2)` と同じです。
`Controlled`ファンクタではレジスタの制御が可能であるため、配列リテラルを使用して `[q1]` 、1つのコントロールのみが必要であることを示します。

この <xref:microsoft.quantum.intrinsic.ccnot> 操作は、二重制御された NOT gate (Toffoli ゲートとも呼ばれます) を実行します。
署名があり `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` ます。
`CCNOT(q1, q2, q3)` は `(Controlled X)([q1, q2], q3)` と同じです。

操作は、 <xref:microsoft.quantum.intrinsic.swap> 2 つの qubits のクォンタムの状態を交換します。
つまり、このメソッドは、ユニタリ行列を実装します。 \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 & \\ \\ 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}. です。
(& a)、署名が含まれてい `((Qubit, Qubit) => Unit is Adj + Ctl)` ます。
`SWAP(q1,q2)` は `CNOT(q1, q2)` 、との後に続くと同じです `CNOT(q2, q1)` `CNOT(q1, q2)` 。

> [!NOTE]
> スワップゲートは、変数の要素を型で再配置するのと同じでは *ありません* `Qubit[]` 。
> を適用する `SWAP(q1, q2)` と、とによって参照される qubits の状態が変更されますが、は `q1` これらの `q2` `let swappedRegister = [q2, q1];` qubits を参照する方法にのみ影響します。
> さらに、は、 `(Controlled SWAP)([q0], (q1, q2))` `SWAP` 要素の並べ替えによっては表現できない3番目の qubit の状態に対して条件を設定できます。
> Fredkin gate とも呼ばれる、制御されたスワップゲートは、すべての従来の計算を含めるのに十分な性能を備えています。

最後に、準備には、マルチ qubit の指数演算子を表す2つの操作が用意されています。
この <xref:microsoft.quantum.intrinsic.exp> 操作は、複数の Pforce li マトリックスの製品に基づいて回転を実行します。これは、マルチ qubit の場合は、(-vec{/sigma}) によって表されます。 \ phi) \mathrel{: =} \ left (i/phi \ sigma_0/otimes \ sigma_1 \ sigma_n)、\ end{-& lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; & lt; $ & lt; sigma_0 \ sigma_1, \ ドット, \ sigma_n) $ は、single qubit の一連の演算子で、$ \ phi $ は角度を表します。
回転は、 `Exp` $ \ vec{-sigma} $ を要素の配列として表し `Pauli` 、署名があることを意味し `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` ます。

操作は、 <xref:microsoft.quantum.intrinsic.expfrac> 上記の dyadic の小数点表記を使用して、同じローテーションを実行します。
署名があり `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` ます。

> [!WARNING]
> 指数演算子のすべての操作は、指数または p Li オペレーターのの製品と同じではありません。
> つまり、$e ^ {i (Z/otimes Z) \phi} \n e e ^ {i Z \phi}/otimes e ^ {i Z \phi} $。

### <a name="measurements"></a>測定 ###

測定する場合、測定される演算子の + 1 eigenvalue は結果に対応 `Zero` し、-1 eigenvalue が結果になり `One` ます。

> [!NOTE]
> この規則は奇妙に見えるかもしれませんが、非常に便利な2つの利点があります。
> まず、$ \ket $ {0} `Result` を観察すると、$ `Zero` \ket $ が {1} に相当する値で表され `One` ます。
> 2つ目の方法として、結果に対応する eigenvalue $/ラムダ $ を、$ is $ \ ラムダ = (-1) ^ r $ という $r に記述できます。

測定演算では、もファンクタもサポートされて `Adjoint` `Controlled` いません。

操作は、 <xref:microsoft.quantum.intrinsic.measure> 指定された P# li 演算子の積で1つ以上の qubits の結合測定を実行します。
P# li 配列と qubit 配列の長さが異なる場合、操作は失敗します。
`Measure` に署名があり `((Pauli[], Qubit[]) => Result)` ます。

ジョイント測定は、各 qubit を個別に測定するのと同じではないことに注意してください。
たとえば、$ \ket {11} = \ket/ {1} otimes \Ket {1} = Xotimes X \ket $ という状態を考えてみ {00} ます。
各 $Z 0 $ と $Z _1 $ を個別に測定すると、$r 0 = $1 および $r _1 = $1 の結果が得られます。
$Z 0 Z_1 $ を測定すると、$ \ket $ の pairity が正であることを表す _ {\textrm{joint}} = $0 という1つの $r 結果が得られ {11} ます。
異なる形式で、$ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $ と指定します。
非常に大きなことですが、この測定からはパリティを学習する *だけ* なので、法則に示されている、正のパリティの 2 2-qubit の状態間のクォンタム情報 ($ \ket {00} $ と $ \ket {11} $) は保持されます。
このプロパティは、エラー修正について説明するため、後で必要になります。

便宜上、準備には、qubits を測定するための他の2つの操作も用意されています。
まず、single qubit の測定を実行するのは非常に一般的であるため、準備はこの場合の短縮形を定義します。
この操作では、 <xref:microsoft.quantum.intrinsic.m> 1 つの qubit に対して P# li $Z $ 演算子を測定し、シグネチャを持ち `(Qubit => Result)` ます。
`M(q)` は `Measure([PauliZ], [q])` に相当します。

は、 <xref:microsoft.quantum.measurement.multim> qubits の各配列で *個別* に $Z $ 演算子を測定し、qubits ごとに取得された値の *配列* を返し `Result` ます。
場合によっては、これを最適化することができます。 シグネチャ () があり `Qubit[] => Result[])` ます。
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

また、準備は、コード内で使用するために、.NET レベルで数学的および型変換関数の豊富なセットを定義し Q# ます。
たとえば、名前空間は、やなどの <xref:microsoft.quantum.math> 便利な操作を定義し <xref:microsoft.quantum.math.sin> <xref:microsoft.quantum.math.log> ます。
Quantum 開発キットによって提供される実装では、従来の .NET 基底クラスライブラリを使用します。そのため、quantum プログラムとその典型的なドライバーの間で、追加の通信ラウンドトリップが必要になる場合があります。
これによってローカルシミュレーターに問題が発生することはありませんが、リモートシミュレーターまたは実際のハードウェアをターゲットコンピューターとして使用すると、パフォーマンスの問題が発生する可能性があります。
ただし、個々のターゲットコンピューターは、このような操作を特定のシステムにとってより効率的なバージョンで上書きすることによって、このパフォーマンスへの影響を軽減することができます。

### <a name="math"></a>数値演算 ###

名前空間には、 <xref:microsoft.quantum.math> .net 基底クラスライブラリの[ `System.Math` クラス](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)の便利な関数が多数用意されています。
これらの関数は、他の関数と同じ方法で使用でき Q# ます。

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

.NET の静的メソッドが引数の型に基づいてオーバーロードされている場合、対応する Q# 関数には、入力の型を示すサフィックスで注釈が付けられます。

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>ビットごとの演算 ###

最後に、 <xref:microsoft.quantum.bitwise> 名前空間には、ビットごとの演算子で整数を操作するための便利な関数がいくつか用意されています。
たとえば、は、 <xref:microsoft.quantum.bitwise.parity> 整数のビットごとのパリティを別の整数として返します。
