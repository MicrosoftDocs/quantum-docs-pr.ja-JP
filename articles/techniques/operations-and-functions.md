---
title: '操作と関数-Q # の手法 |Microsoft Docs'
description: '操作と関数-Q # の手法'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820778"
---
# <a name="q-operations-and-functions"></a>Q # 操作と関数

Q # プログラムは、1つまたは複数の操作で構成されています。この*操作*では、クォンタムデータに対して実行できる副作用と、典型的なデータを変更できる1つ以上の*関数*が含まれます。 操作とは対照的に、関数は純粋な古典動作を説明するために使用されます。また、古典出力値の計算以外にも影響はありません。

Q # で定義された各操作は、その言語で定義されている組み込みの組み込み操作を含む、他の任意の数の操作を呼び出すことができます。 これらの組み込み操作が定義されている特定の方法は、ターゲットコンピューターによって異なります。 コンパイルされると、各操作はターゲットコンピューターに提供できる .NET クラス型として表されます。

## <a name="defining-new-operations"></a>新しい操作の定義

前に説明したように、Q # で記述されたクォンタムプログラムの最も基本的な構成要素は*操作*であり、たとえば、シミュレーターを使用するか、q # 内の他の操作によって呼び出すことができます。
各操作は、入力を受け取り、出力を生成し、1つまたは複数の操作の特殊化の実装を指定します。
たとえば、次の操作は、既定の本文の特殊化のみを定義し、入力として1つの qubit を受け取り、その入力に対して組み込みの `X` 操作を呼び出します。

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

キーワード `operation` によって操作の定義が開始され、その後に名前が付けられます。ここでは、`BitFlip`ます。
次に、入力の型が `Qubit`として定義され、新しい操作内の入力を参照するための名前 `target` が定義されます。
同様に、`Unit` は、操作の出力が空であることを定義します。
これは、 C#とその他の命令型言語の `void` と同様に使用されF#ます。また、とその他の機能言語の `unit` と同じです。

> [!NOTE]
> これについては以下で詳しく説明しますが、Q # の各操作は1つの入力を受け取り、ただ1つの出力を返します。
> 複数の入力と出力は、複数の値をまとめて1つの値にまとめる*タプル*を使用して表されます。
> これは、Q # が "タプルインタプル" 言語であるということです。
> この概念に従うと、`Unit`型の "空の" タプルとして `()` を読み取る必要があります。

新しい操作では、既定の本体の特殊化の実装のみを明示的に指定する必要がある場合は、宣言内で実装を直接指定できます。 また、次に示すように、1つ以上の `functor` 操作などのの実装を定義することもできます。 上記の例では、唯一のステートメントは、組み込みの Q # 操作 <xref:microsoft.quantum.intrinsic.x>を呼び出すことです。

操作では、`Unit`よりも興味深い型を返すこともできます。
たとえば、<xref:microsoft.quantum.intrinsic.m> 操作は、測定を実行したことを表す `Result`型の出力を返します。 出力を操作から別の操作に渡すことも、`let` キーワードと共に使用して新しい変数を定義することもできます。
<!-- Link to UID for superdense conceptual and example documentation. -->
これにより、次のように低レベルでクォンタム操作と対話する古典的な計算を表すことができます。

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>ファンクター、adjoint、および制御
操作で、 *adjointed*または*制御*されている場合の操作の動作を定義できます。 操作の adjoint 特殊化は、逆の実行時の動作方法を指定し、制御された特殊化は、クォンタムレジスタの状態に適用された場合の操作の動作方法を指定します。
これらの特殊化の存在は、次の例の `is Adj + Ctl` 操作シグネチャの一部として宣言できます。 そのような暗黙的に宣言された各特殊化の対応する実装が、コンパイラによって生成されます。 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Q # の多くの操作は、ユニタリゲートを表します。
> $U $ が、操作 `U`によって表されるユニタリゲートである場合、`Adjoint U` は、$U、ダガー $ のようなユニタリゲートを表します。

実装がコンパイラによって生成されない場合は、明示的に指定できます。 このような明示的な特殊化の宣言は、適切な生成ディレクティブまたはユーザー定義の実装で構成されます。 たとえば、上記の `PrepareEntangledPair` のコードは、明示的な特殊化宣言を含む次のコードと同じです。 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
キーワード `auto` は、特殊化された実装を生成する方法をコンパイラが決定する必要があることを示します。
コンパイラが特定の特殊化の実装を自動的に生成できない場合、またはより効率的な実装を指定できる場合は、実装を手動で定義することもできます。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
上の例では、`adjoint invert;` は、本体の実装を反転することによって adjoint の特殊化が生成されることを示し、`controlled adjoint invert;` は、制御された特殊化の実装を反転することによって、制御された adjoint 特殊化が生成されることを示します。

これについては、上位の[制御フロー](xref:microsoft.quantum.concepts.control-flow)でさらに例を紹介します。

操作の特殊化を呼び出すには、`Adjoint` または `Controlled` キーワードを使用します。
たとえば、上記の superdense コーディングの例では、`PrepareEntangledPair` の adjoint を使用して、ありの状態を qubits のペアに変換することで、より多くのコンパクトを記述できます。

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

機能を使用するための操作を設計する際に考慮すべき重要な制限がいくつかあります。
他の操作の出力値を使用する操作のために特に特殊化されたものは、コンパイラによって自動的に生成されません。これは、このような操作でステートメントの順序を変更して同じ効果を得る方法があいまいであるためです。


## <a name="defining-new-functions"></a>新しい関数の定義

また、Q # では、関数を定義することもできます。*関数*は、出力値を計算しても影響を与えることができないということです。
特に、関数は、操作を呼び出したり、qubits に作用したり、乱数をサンプリングしたりすることはできません。また、関数に入力値を超える状態に依存することもあります。
その結果、Q # 関数は*純粋*に同じ入力値を同じ出力値にマップすることになります。
これにより、Q # コンパイラは、操作の特殊化を生成するときに関数が呼び出される方法とタイミングを安全に並べ替えることができます。

関数の定義は、操作を定義する場合と同様に機能します。ただし、関数に対して adjoint または制御された特殊化を定義することはできません。
その例をご紹介します。

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
これを行うには、操作ではなく関数の観点から古典的なロジックを記述することをお勧めします。これにより、操作内からより簡単に使用できるようになります。
たとえば、`Square` を操作として記述した場合、コンパイラは、同じ入力でそれを呼び出すことによって同じ出力が一貫して生成されることを保証できませんでした。

関数と演算の違いをアンダースコアにするには、Q # 操作内からランダムな数値をサンプリングするクラシックデプロイの問題について考えてみます。

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

`U` が呼び出されるたびに、`target`に対して異なる操作が行われます。
特に、`adjoint auto` 特殊化宣言を `U`に追加した場合、`U(target); Adjoint U(target);` は id として機能することを保証できません (つまり、非 op)。
これは、[ベクターとマトリックス](xref:microsoft.quantum.concepts.vectors)で見た adjoint の定義に違反しています。これにより、が <xref:microsoft.quantum.math.randomreal> 操作を呼び出したときに、コンパイラによって提供される保証を損なうことがある操作で adjoint 特殊化を自動生成できるようになります。<xref:microsoft.quantum.math.randomreal> は、adjoint または制御されたバージョンが存在しない操作です。

一方、`Square` などの関数呼び出しを許可しても安全です。そのため、コンパイラは、出力を安定した状態に保つために、`Square` への入力を保持するだけで済みます。
したがって、できるだけ多くの従来のロジックを関数に分離することにより、他の関数や操作でそのロジックを簡単に再利用できるようになります。

## <a name="control-flow"></a>制御フロー

演算または関数内では、最も一般的な命令型の共通言語と同様に、各ステートメントが順番に実行されます。
ただし、この制御フローは、次の3つの方法で変更できます。

- `if` ステートメント
- `for` ループ
- `repeat`-`until` ループ

[「成功までの繰り返し (ru)](xref:microsoft.quantum.techniques.qubits#measurements)回線」について説明するまで、後者については説明しません。
ただし、`if` および `for` 制御フローの構造は、従来のほとんどのプログラミング言語をよく理解しています。
具体的には、`if` ステートメントは条件を受け取ることができ、その後に1つ以上の `elif` ステートメントが続き、`else`で終わることがあります。

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

同様に、`for` ループは、整数の範囲または配列の要素に対する反復処理を示します。

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

重要な点として、`for` ループや `if` のステートメントを、特殊化が自動生成される操作で使用することもできます。 この場合、`for` ループの adjoint は方向を反転し、各反復の adjoint を取ります。
これは、"靴と socks" の原則に従っています。 socks の後に靴を元に戻したい場合は、靴を元に戻してから、socks への配置を元に戻す必要があります。
靴を decidedly ている間に、試してみて、お客様の socks を試してみることができます。

## <a name="operations-and-functions-as-first-class-values"></a>ファーストクラスの値としての操作と関数

制御フローと従来のロジックについては、操作ではなく関数を使用するという1つの重要な手法として、Q # の操作と関数を*ファーストクラス*で利用することが挙げられます。
つまり、言語の各値が独自の権限であるということです。
たとえば、次のコードは完全に有効な Q # コードです (少し間接的な場合)。

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

上記のスニペットの変数 `ourH` の値は、他の操作と同様にその値を呼び出すことができるように、操作 <xref:microsoft.quantum.intrinsic.h>になります。
これにより、高度な制御フローの概念を形成する操作を入力の一部として実行する操作を記述できます。
たとえば、同じターゲット qubit に2回適用して、操作を "正方形" にすることを考えてみます。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

この例では、型 `(Qubit => Unit)` に表示される `=>` 矢印は、入力フィールド `op` が `Qubit` 型の入力としてを受け取り、その出力として空のタプルを生成する操作であることを示しています。
また、サポートされている動作に関する情報を含む、その操作の種類の特性を指定します。
`(Qubit => Unit)` 型の操作では、`Adjoint` と `Controlled` のファンクタのどちらもサポートされていません。 その型の操作が `Adjoint` のファンクタなどをサポートする必要があることを示すには、それを adjointable として宣言する必要があります。 これを行うには、型に `is Adj` 注釈を使用します。 同様に、`(Qubit => Unit is Ctl)` は、その型の操作が `Controlled` のファンクタをサポートしていることを示します。 この詳細については、「Q # での型」 (xref: microsoft. quantum..................................

ここでは、操作を出力の一部として返すこともできることを強調しています。これは、一部の種類のクラシック条件ロジックを、操作の形式でクォンタムプログラムの説明を返す従来の関数として分離できるようにするためです。
簡単な例として、2ビットの古典的なメッセージを受信するパーティがメッセージを使用して、qubit を適切なテレポートの状態にデコードする必要がある場合の例を考えてみます。
これは、これらの2つの従来のビットを受け取り、適切なデコード操作を返す関数の観点から記述できます。

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

この新しい関数は実際には関数です。 `hereBit` と `thereBit`の同じ値を使用して呼び出すと、常に同じ操作が返されます。
そのため、デコードロジックがさまざまな操作の特殊化の定義とどのようにやり取りするかを気にせずに、デコーダーを操作中に安全に実行できます。
つまり、関数内で古典的なロジックを分離し、入力が保持されている限り、関数呼び出しを impunity で並べ替えることができることをコンパイラに保証しています。

また、関数をファーストクラスの値として扱うこともできます。これは、[操作と関数の種類](#operations-and-functions-as-first-class-values)について詳しく説明する際に、さらに詳細に説明します。

## <a name="partially-applying-operations-and-functions"></a>操作と関数の部分的な適用

*部分的なアプリケーション*を使用して操作を返す関数については、実際には呼び出しを行わずに関数または演算に入力の1つ以上の部分を指定できるようにすることで、さらに多くのことを行うことができます。 たとえば、上記の `ApplyTwice` の例を呼び出すと、入力操作が適用される qubit をすぐに指定しなくてもよいことを示すことができます。

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

この場合、ローカル変数 `twiceOp` は部分的に適用される操作 `ApplyTwice(op, _)`を保持します。この場合、まだ指定されていない入力部分は `_`によって示されます。
実際には、次の行で `twiceOp` を呼び出すと、部分的に適用される操作に入力として、入力の残りの部分すべてが元の操作に渡されます。
したがって、上記のスニペットは、実際には `ApplyTwice(op, target)` を直接呼び出すのと同じです。新しいローカル変数が導入されています。これにより、入力の一部を提供しながら、呼び出しを遅延させることができます。

部分的に適用された操作は、入力全体が提供されるまでは実際には呼び出されないため、関数内でも部分的に操作を部分的に適用できます。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

原則として、`SquareOperation` 内の古典的なロジックははるかに複雑になる可能性がありますが、コンパイラが関数に対して提供できる保証によって、操作の残りの部分から分離されています。
このアプローチは、一般的な制御フローを、quantum プログラム内で簡単に使用できる方法で表現するために、Q # 標準ライブラリ全体で使用されます。
