---
title: 'Q # 型モデル |Microsoft Docs'
description: 'Q # 型モデル'
author: QuantumWriter
uid: microsoft.quantum.language.type-model
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4e251053d1b8306bf8956314d8099e95c56bce55
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184748"
---
# <a name="the-type-model"></a>型モデル

このセクションでは、Q # 型モデルについて説明し、型を指定して操作するための構文について説明します。
Q # は*厳密に型指定*された言語であるため、これらの型を慎重に使用することは、コンパイル時に q # プログラムに対する強力な保証をコンパイラが提供するのに役立ちます。

最も強力な保証を提供するために、Q # の型間の変換は、その変換を表す関数の呼び出しを使用して明示的に行う必要があります。 このような関数は、<xref:microsoft.quantum.convert> 名前空間の一部として提供されています。
一方、互換性のある型へのアップキャストは暗黙的に行われます。 

Q # には、直接使用できるプリミティブ型と、他の型から新しい型を生成するためのさまざまな方法が用意されています。
各項目については、このセクションの残りの部分で説明します。

## <a name="primitive-types"></a>プリミティブ型

Q # 言語には、他の型を構築できるいくつかの*プリミティブ型*が用意されています。

- `Int` 型は、64ビット符号付き整数 (例: `2`、`107`、`-5`) を表します。
- `BigInt` 型は、任意のサイズの符号付き整数 (`2L`、`107L`、`-5L`など) を表します。
   この型は .NET <xref:System.Numerics.BigInteger> に基づいています。
   各種.
- `Double` 型は、`0.0`、`-1.3`、`4e-7`などの倍精度浮動小数点数を表します。
- `Bool` 型はブール値を表し、`true` または `false`を指定できます。
- `Qubit` 型は、クォンタムビットまたは qubit を表します。
   `Qubit`s はユーザーに対して非透過的です。他の操作に渡す場合を除き、これらの操作で可能な操作は、id (等値) をテストすることだけです。
   最終的に、`Qubit`に対するアクションは、クォンタムプロセッサ (またはシミュレーション) で組み込み命令を呼び出すことによって実装されます。
- `Pauli` 型は、4つのシングル qubit のいずれかの演算子を表します。
   この型は、回転の基本操作を表し、測定対象の観測対象を指定するために使用されます。
   これは、`PauliI`、`PauliX`、`PauliY`、および `PauliZ`の4つの値を持つ列挙型です。これは、型 `Pauli`の定数です。
- `Result` 型は、測定の結果を表します。
   これは、`One` と `Zero`の2つの値を持つ列挙型であり、`Result`型の定数です。
   `Zero` は、+ 1 eigenvalue が測定されたことを示します。`One` は、-1 eigenvalue を示します。
- `Range` 型は、`start..step..stop`によって示される整数のシーケンスを表します。これは、ステップがオプションであることを示します。 
   この `start .. stop` は `start..1..stop`に対応します。たとえば、`1..2..7` は、$\{1、3、5、7\}$ というシーケンスを表します。
- `String` の種類は、作成後にユーザーに対して非透過の Unicode 文字のシーケンスです。
  この型は、エラーまたは診断イベントが発生した場合に、従来のホストにメッセージを報告するために使用されます。
- `Unit` 型は、値を1つだけ `()`できる型です。 
  この型は、Q # 関数または操作が情報を返さないことを示すために使用されます。 

`true`、`false`、`PauliI`、`PauliX`、`PauliY`、`PauliZ`、`One`、および `Zero` の定数はすべて、Q # の予約済みの記号です。

## <a name="array-types"></a>配列型

有効な Q # 型 `'T`が指定されている場合は、`'T`型の値の配列を表す型があります。
この配列型は `'T[]`として表されます。たとえば、`Qubit[]` や `Int[][]`のようになります。
たとえば、整数のコレクションは `Int[]`を示し、`(Bool, Pauli)` 値の配列の配列は `(Bool, Pauli)[][]`を示します。

2番目の例では、これは、四角形の2次元配列ではなく、配列のジャグ配列を表すことに注意してください。
Q # では、四角形多次元配列はサポートされていません。

配列の値は、`[PauliI, PauliX, PauliY, PauliZ]`のように、配列の要素を角かっこで囲むことによって、Q # のソースコードで書き込むことができます。
配列リテラルの型は、配列内のすべての項目の共通基本型によって決定されます。 

> [!WARNING]
> 配列の要素は、配列の作成後に変更することはできません。
> 更新と再割り当てのステートメント、またはコピーと更新の式を使用して、変更された配列を作成できます。

または、`new` キーワードを使用して、配列のサイズから配列を作成することもできます。

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

どちらの場合も、配列が構築されると、コア関数 `Length` を使用して、`Int`として要素の数を取得できます。
配列は、角かっこを使用して下付き文字にすることができます。また、添字 `Int` または型 `Range`のいずれかを使用して、配列の要素のサブセットを含む単一の要素または新しい配列を取得します。
配列の添字は0から始まります。

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>タプル型

`T0`、`T1`、...、`Tn`という0個以上の型が指定されている場合は、新しい*タプル型*を `(T0, T1, ..., Tn)`として表すことができます。
新しいタプル型を構築するために使用される型は、`(Int, (Qubit, Qubit))`のように、それ自体をタプルにすることができます。
ただし、このような入れ子は常に有限ですが、タプル型は、それ自体を含む状況では使用できません。

新しいタプル型の値は、組の各型の値のシーケンスによって形成されるタプルです。
たとえば、`(3, false)` は、`(Int, Bool)`タプル型のタプルです。
組、配列の組、サブタプルの組などの配列を作成できます。

Q # 0.3 の場合、`Unit` は空のタプルの*型*の名前です。空のタプル*値*には `()` が使用されます。

タプルインスタンスは変更できません。
Q # には、作成されたタプルの内容を変更する機構が用意されていません。

タプルは、1つの値に値をまとめて収集し、それらを簡単に渡すことができるようにするために、Q # 全体で使用される強力な概念です。
特に、タプル表記を使用すると、すべての操作と呼び出し可能が厳密に1つの入力を受け取り、ただ1つの出力を返すことができます。

### <a name="singleton-tuple-equivalence"></a>シングルトンタプルの等価性

`(5)` や `([1,2,3])`など、シングルトン (単一要素) の組を `('T1)`作成することができます。
ただし、Q # は、シングルトンタプルを、囲まれた型の値と完全に等価なものとして扱います。
つまり、`5` と `(5)`、`5` と `(((5)))`の間、または `(5, (6))` と `(5, 6)`の間に違いはありません。

この等価性は、代入式や式など、すべての目的に適用されます。
これは、`5+3`書き込み `(5)+3` として記述するのと同じです。両方の式が `8`として評価されます。
特に、これは、入力タプルまたは出力タプル型が1つのフィールドを持つ演算または関数は、1つの引数を受け取るか、単一の値を返すと考えることができます。

このプロパティは、_シングルトンタプルの等価性_と呼ばれています。

## <a name="user-defined-types"></a>ユーザー定義型

Q # ファイルでは、任意の有効な型の単一の値を含む新しい名前付きの型を定義できます。
`T`タプル型の場合、`newtype` ステートメントを使用して `T` のサブタイプである新しいユーザー定義型を宣言できます。
たとえば、@"microsoft.quantum.canon" 名前空間では、複素数はユーザー定義型として定義されます。

```qsharp
newtype Complex = (Double, Double);
```

このステートメントは、`Double`型の2つの匿名項目を持つ新しい型を作成します。   
ユーザー定義型では、匿名項目以外に、Q # バージョン0.7 以降の名前付き項目もサポートされます。 たとえば、複素数の実数部を表す double 型の `Re` to 項目には、虚数部の `Im` を指定できます。 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
ユーザー定義型の1つの項目に名前を付けることは、すべての項目に名前を付ける必要があることを意味するわけではありません。名前付き項目と名前のない項目の任意の組み合わせがサポートされます さらに、内部項目にもという名前が付けられます。
次の例のように定義されている型 `Nested` には、基になる型 `(Double, (Int, String))`があります。この場合、型 `Int` の項目のみが指定され、その他のすべての項目は匿名になります。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```
名前付き項目には、アクセス演算子 `::`から直接アクセスできるという利点があります。 

```qsharp
function Addition (c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

一方、匿名の項目にアクセスするには、後置演算子 `!`を使用して、ラップされた値を最初に抽出する必要があります。
"ラップ解除" 演算子 (`!`) を使用すると、ユーザー定義型に含まれる値を抽出できます。
このような "ラップ解除" 式の型は、ユーザー定義型の基になる型です。 

```qsharp
function PrintMsg (value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

ラップ解除演算子は、ラップのレイヤーを1つだけラップ解除します。
複数のラップ解除演算子は、乗算された値にアクセスするために使用できます。

その例をご紹介します。

```qsharp
newtype WrappedInt = Int;
newtype DoublyWrappedInt = WrappedInt;

...
    let x = DoublyWrappedInt(WrappedInt(6));
    let y = x!;       // y is WrappedInt(6)
    let z = x!!;      // z is 6
    let a = x + 5;    // This is an error, a DoublyWrappedInt isn't an Int
    let b = x! + 5;   // Also an error
    let c = x!! + 5;  // This is valid, c will be 11
...
```

詳細については、「[式のラップ](xref:microsoft.quantum.language.expressions#unwrap-expressions)解除」と「[演算子の優先順位](xref:microsoft.quantum.language.expressions#operator-precedence)」を参照してください。

ユーザー定義型の値は、対応する型コンストラクターを呼び出すことによって作成できます。

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

または、[コピーと更新の式](xref:microsoft.quantum.language.expressions#copy-and-update-expressions)を使用して、既存の値から新しい値を作成することもできます。 配列の場合と同様に、このような式は、指定された名前付き項目を除き、元の式のすべての項目の値をコピーします。 これらの値は、式の右辺に定義されている値に設定されます。 配列項目で使用できるその他の言語構成要素は[、たとえば、](xref:microsoft.quantum.language.statements#update-and-reassign-statement)ユーザー定義型の名前付き項目にも存在します。

```qsharp
newtype ComplexArray = (Count : Int, Data : Complex[]);

function AsComplexArray (data : Double[]) : ComplexArray {

    mutable res = ComplexArray(0, new Complex[0]);
    for (item in data) {
        set res w/= Data <- res::Data + [Complex(item, 0.)]; // update-and-reassign statement
    }
    return res w/ Count <- Length(res::Data); // returning a copy-and-update expression
}
```

ユーザー定義型は、他の型を使用できる場所であればどこでも使用できます。
特に、ユーザー定義型の配列を定義し、タプル型の要素としてユーザー定義型を含めることができます。

再帰型構造を作成することはできません。
つまり、ユーザー定義型を定義する型を、ユーザー定義型の要素を含むタプル型にすることはできません。
一般に、ユーザー定義型は相互に循環依存関係がない場合があるため、次の型定義のセットは無効になります。

```qsharp
newtype TypeA = (Int, TypeB);
newtype TypeB = (Double, TypeC);
newtype TypeC = (TypeA, Range);
```

複雑なタプル型の短いエイリアスを提供するだけでなく、そのような型を定義する大きな利点の1つは、特定の値の意図を文書化できることです。
`Complex`の例に戻ると、1つのユーザー定義型として2D 極座標座標を定義することもできます。

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

`Complex` と `Polar` の両方に基になる型 `(Double, Double)`があるにもかかわらず、2つの型は両方とも Q # で完全には互換性がないため、極座標を使用して複雑な数値演算関数を誤って呼び出した場合のリスクを最小限に抑えることができます。
このようにして、ユーザー定義型にはレコードと同様F#のロールがあります (例:)。 


## <a name="operation-and-function-types"></a>操作と関数の型

Q #_操作_は、クォンタムサブルーチンです。
つまり、クォンタム操作を含む呼び出し可能なルーチンです。

Q #_関数_は、クォンタムアルゴリズム内で使用される古典的なサブルーチンです。
これには、従来のコードが含まれていても、クォンタム操作は含まれません。
具体的には、関数は、qubits の割り当てや借用を行うことも、操作を呼び出すこともできません。
ただし、処理のために操作または qubits を渡すことができます。
したがって、関数は、同じ引数でそれらを呼び出すと、常に同じ結果が生成されるという意味で完全に決定的です。 

操作と関数は、共に_呼び出しを_実行できると呼びます。  これらの[例](#examples)を次に示します。

すべての Q # 呼び出しが、1つの値を入力として受け取り、1つの値を出力として返すと見なされます。
入力値と出力値は、どちらもタプルにすることができます。
結果が返されない呼び出し可能性があり `Unit`。
入力がない callables は、空のタプルを入力として受け取ります。

任意の呼び出し可能な基本型は `('Tinput => 'Tresult)` または `('Tinput -> 'Tresult)`として記述され、`'Tinput` と `'Tresult` の両方が型になります。
操作には、`=>`を使用した最初の形式が使用されます。関数の2番目の形式 (`->`)。
たとえば、`((Qubit, Pauli) => Result)` は、単一の 1 qubit 測定操作のシグネチャを表します。

関数型は、シグネチャによって完全に指定されます。
たとえば、角度のサインを計算する関数の型は `(Double -> Double)`になります。

操作 (関数ではありません) には、操作の種類の一部として表現される特定の追加_特性_があります。 このような特性には、操作がサポートする機能に関する情報が含まれます。
機能は、基本操作の特殊化を生成するメタ操作です。下記の「ファンク[ター」を参照し](#functors)てください。

操作の種類は、入力の種類、出力の種類、およびその特性によって指定されます。    
操作の種類で `Controlled` または `Adjoint` ファンクタのサポートを必要とするために、対応する特性を示す注釈を追加する必要があります。
たとえば、注釈 `is Ctl` は、操作が制御可能であることを示します。 その型の操作で `Adjoint` と `Controlled` の両方のファンがサポートされるようにするには、これを `(Qubit => Unit is Adj + Ctl)`として表現します。 使用される操作特性 `Adj` および `Ctl` 厳密には、2つの定義済みラベルセットです。各ラベルは、特定のファンクタのサポートなど、特定の操作特性を示します。
したがって、これら2つのセットの和集合を示すために `+` が使用され、`*` が両方のセットに共通するラベルであるかどうかを示すために使用されます。  

たとえば、P# li `X` 操作には `(Qubit => Unit is Adj + Ctl)`型があります。
すべての機能をサポートしていない操作の種類は、入力と出力の型だけで指定し、追加の注釈は付けません。


### <a name="type-parameterized-functions-and-operations"></a>型パラメーターの関数と操作

呼び出し可能な型には、型パラメーターを含めることができます。
型パラメーターは、1つの引用符で始まる記号で示されます。たとえば、`'A` は有効な型パラメーターです。

1つのシグネチャで、型パラメーターが複数回出現する場合があります。
たとえば、別の関数を配列の各要素に適用し、収集された結果を返す関数は、シグネチャ `(('A[], 'A->'A) -> 'A[])`になります。
同様に、2つの操作の構成を返す関数には `((('A=>'B), ('B=>'C)) -> ('A=>'C))`シグネチャがある場合があります。

型パラメーターの呼び出し可能な呼び出しを呼び出すときは、同じ型パラメーターを持つすべての引数が同じ型である必要があります。

Q # には、型パラメーターに置き換えられる可能性のある型を制限する機構が用意されていません。

### <a name="type-compatibility"></a>型の互換性

追加のファンクターがサポートされている操作は、より小さい値を持つ操作のすべての場所で使用できますが、同じシグネチャが必要です。
たとえば、型 `(Qubit => Unit is Adj)` の操作は、型 `(Qubit => Unit)` の操作が必要な場所であればどこでも使用できます。

Q # は、呼び出し可能な戻り値の型に関して共変です。同じ入力型の呼び出し可能なと互換性がある `'A` 型を返す呼び出し可能な型と、と互換性がある `'A` の結果型です。

Q # は、入力の型に関して反変です。入力と同じ結果型の呼び出し可能な型と、`'A`と互換性のある入力型との互換性があるという点で、型 `'A` を受け取る呼び出し可能な。

つまり、次の定義を指定します。

```qsharp
operation Invertible (qs : Qubit[]) : Unit 
is Adj {...} 
operation Unitary (qs : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertibleWith (
   inner: (Qubit[] => Unit is Adj),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith (
   inner: (Qubit[] => Unit is Adj + Ctl),
   outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

次のことが当てはまります。

- 操作 `ConjugateInvertibleWith` は `Invertible` または `Unitary`のいずれかの `inner` 引数を使用して呼び出すことができます。
- 操作 `ConjugateUnitaryWith` は `Unitary`の `inner` 引数を使用して呼び出すことができますが、`Invertible`は呼び出せません。
- `ConjugateInvertibleWith`から `(Qubit[] => Unit is Adj + Ctl)` 型の値が返される場合があります。

> [!IMPORTANT]
> Q # 0.3 では、ユーザー定義型の動作に大きな違いがあります。

ユーザー定義型は、サブタイプとしてではなく、基になる型のラップされたバージョンとして扱われます。
これは、基になる型の値が必要な場合に、ユーザー定義型の値を使用できないことを意味します。

### <a name="functors"></a>ファンクター

Q # のファンクタは、別の操作から新しい操作を定義するファクトリです。
新しい操作の実装を定義するときに、基本操作の実装にアクセスできます。
したがって、関数は、従来の上位レベルの関数よりも複雑な関数を実行できます。

この型は、Q # 型システムには含まれていません。 そのため、変数にバインドしたり、引数として渡したりすることはできません。 

ファンクタは、操作に適用して新しい操作を返すことによって使用されます。
たとえば、`Adjoint` のファンクタを `Y` 操作に適用した結果として得られる操作は、`Adjoint Y`として書き込まれます。
その後、他の操作と同様に、新しい操作を呼び出すことができます。
このため、`Adjoint Y(q1)` は、Adjoint ファンクタを `Y` 操作に適用して新しい操作を生成し、その新しい操作を `q1`に適用します。

同様に、`Controlled X(controls, target)` は制御されたファンを `X` 操作に適用して新しい操作を生成し、その新しい操作を `controls` および `target`に適用します。

Q # の2つの標準のファンクターは `Adjoint` と `Controlled`です。

#### <a name="adjoint"></a>Adjoint

クォンタムコンピューティングでは、操作の adjoint は、操作の複雑な共役転置です。
ユニタリ演算子を実装する操作の場合、adjoint は演算の逆になります。
Qubits のセットに対して他の一連の処理を呼び出すだけの単純な操作の場合、同じ qubits にサブ操作の adjoint を逆順で適用することによって、adjoint を計算できます。

操作式を指定した場合は、`Adjoint` ファンクタを使用して新しい演算式を作成できます。
たとえば、`Adjoint QFT` は、`QFT` 操作の adjoint を指定します。
新しい操作のシグネチャと型は、基本操作と同じです。
特に、新しい操作では `Adjoint`が許可され、基本操作が行われた場合にのみ `Controlled` が許可されます。

Adjoint ファンクタは、独自の逆になります。つまり、`Adjoint Adjoint Op` は常に `Op`と同じです。

#### <a name="controlled"></a>た

操作の制御されたバージョンは、すべてのコントロール qubits が指定された状態にある場合にのみ、基本操作を効果的に適用する新しい操作です。
コントロール qubits が法則内にある場合、基本操作は一貫の適切な部分に適用されます。
したがって、制御された操作は、多くの場合、entangを生成するために使用されます。

Q # では、制御されたバージョンは常に制御 qubits の配列を取得します。また、指定した状態は、常に計算 (`PauliZ`) `One` 状態、$ \ket{1}$ に含まれるすべてのコントロール qubits に対して行われます。
その他の状態に基づいて制御するには、制御された操作の前に適切なユニタリ操作を制御 qubits に適用し、次に、制御された操作の後に逆を適用します。
たとえば、制御された操作の前後のコントロール qubit に `X` 操作を適用すると、その qubit の `Zero` 状態 ($ \ket{0}$) に対して操作が制御されます。の前と後に `H` 操作を適用すると、`PauliX` の `One` の状態を制御します。これは、{0}{1}状態ではなく、P# li X、$ \ket{-} \mathrel{: =} (\ket{2}-\ket `PauliZ`)/\ sqrt `One` $ の-1 eigenvalue です。

操作式を指定した場合は、`Controlled` ファンクタを使用して新しい演算式を作成できます。
新しい操作の署名は、元の操作の署名に基づいています。
結果の型は同じですが、入力の型は2つのタプルで、最初の要素としてコントロール qubit を保持し、2番目の要素として元の操作の引数を保持します。
新しい操作では `Controlled`がサポートされ、元の操作が行われた場合にのみ、`Adjoint` がサポートされます。

元の操作で1つの引数のみを取得した場合は、シングルトン組の等価性がここで再生されます。
たとえば、`Controlled X` は、`X` 操作の制御されたバージョンです。
`X` に型 `(Qubit => Unit is Adj + Ctl)`があるため、`Controlled X` の型は `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`です。シングルトンタプルの等価性のため、これは `((Qubit[], Qubit) => Unit is Adj + Ctl)`と同じです。

基本操作に複数の引数を指定する場合は、操作の制御されたバージョンの対応する引数をかっこで囲み、それらをタプルに変換してください。
たとえば、`Controlled Rz` は、`Rz` 操作の制御されたバージョンです。
`Rz` に型 `((Double, Qubit) => Unit is Adj + Ctl)`があるため、`Controlled Rz` には `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`型があります。
したがって、`Controlled Rz(controls, (0.1, target))` は `Controlled Rz` の有効な呼び出しです (`0.1, target`を囲むかっこに注意してください)。

もう1つの例として、`CNOT(control, target)` を `Controlled X([control], target)`として実装できます。 ターゲットを2つの制御 qubits (CCNOT) で制御する必要がある場合は、`Controlled X([control1, control2], target)` ステートメントを使用できます。

### <a name="examples"></a>例

この Q # 操作の例は、[測定](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/measurement)サンプルから取得したものです。 操作内では、qubits を割り当てて、`H` や `X`などの qubits に対してクォンタム操作を使用できます。

```qsharp
/// # Summary
/// Prepares a state and measures it in the Pauli-Z basis.
operation MeasureOneQubit () : Result {
        mutable result = Zero;

        using (qubit = Qubit()) { // Allocate a qubit
            H(qubit);               // Use a quantum operation on that qubit

            set result = M(qubit);      // Measure the qubit

            if (result == One) {    // Reset the qubit so that it can be released
                X(qubit);
            }

            return result;
        }
 }
```

この関数の例は、 [PhaseEstimation](https://github.com/microsoft/Quantum/tree/master/samples/characterization/phase-estimation)サンプルを基にしています。 純粋にクラシックコードを含みます。 上記の例とは異なり、qubits は割り当てられず、クォンタム操作は使用されません。


```qsharp
/// # Summary
/// Given two arrays, returns a new array that is the pointwise product
/// of each of the given arrays.
function MultiplyPointwise (left : Double[], right : Double[]) : Double[] {
    mutable product = new Double[Length(left)];

    for (idxElement in IndexRange(left)) {
        set product w/= idxElement <- left[idxElement] * right[idxElement];
    }
    return product;
}
```

[ReversibleLogicSynthesis](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/reversible-logic-synthesis)サンプルの例のように、処理のために関数に qubits を渡すこともできます。 Qubits は関数に渡され、処理に使用されます。ただし、どのポイントも qubits の状態自体が変更されることはありません。

```qsharp
/// # Summary
/// Translate MCT masks into multiple-controlled Toffoli gates (with single
/// targets).
function GateMasksToToffoliGates (qubits : Qubit[], masks : MCMTMask[]) : MCTGate[] {

    mutable result = new MCTGate[0];
    let n = Length(qubits);

    for (i in 0 .. Length(masks) - 1) {
        let (controls, targets) = (masks[i])!;
        let controlBits = IntegerBits(controls, n);
        let targetBits = IntegerBits(targets, n);
        let cQubits = Subarray(controlBits, qubits);
        let tQubits = Subarray(targetBits, qubits);

        for (target in tQubits) {
            set result += [MCTGate(cQubits, target)];
        }
    }

    return result;
}
```
