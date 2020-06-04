---
title: Q# の型
description: 'Q # プログラミング言語で使用されるさまざまな型について説明します。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
ms.openlocfilehash: f7a3ac3813966c0ef695068297ce4d9949ead554
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327290"
---
# <a name="types-in-q"></a>Q# の型

このページでは、Q # 型モデルをレイアウトし、型を指定して操作するための構文について説明します。
次のページ「[型の式](xref:microsoft.quantum.guide.expressions)」では、これらの型の式を作成および操作する方法について詳しく説明しています。

Q # は*厳密に型指定*された言語であるため、これらの型を慎重に使用することは、コンパイル時に q # プログラムに対する強力な保証をコンパイラが提供するのに役立ちます。
最も強力な保証を提供するために、Q # の型間の変換は、その変換を表す関数の呼び出しを使用して明示的に行う必要があります。 このような関数は、名前空間の一部として提供されてい <xref:microsoft.quantum.convert> ます。
一方、互換性のある型へのアップキャストは暗黙的に行われます。 

Q # には、直接使用できるプリミティブ型と、他の型から新しい型を生成するためのさまざまな方法が用意されています。
各項目については、このセクションの残りの部分で説明します。

## <a name="primitive-types"></a>プリミティブ型

Q # 言語には、他の型を構築できるいくつかの*プリミティブ型*が用意されています。

- この `Int` 型は、64ビットの符号付き整数を表します。例: `2` 、 `107` 、 `-5` 。
- 型は、 `BigInt` 任意のサイズの符号付き整数 (、など) を表します `2L` `107L` `-5L` 。
   この型は .NET に基づいています。<xref:System.Numerics.BigInteger>
   各種.
- 型は、 `Double` 倍精度浮動小数点数を表します。例: `0.0` 、 `-1.3` 、 `4e-7` 。
- 型は、 `Bool` またはのいずれかのブール値を表し `true` `false` ます。
- この `Range` 型は、によって示される整数のシーケンスを表し `start..step..stop` ます。これは、ステップが省略可能であることを示します。 
   これは `start .. stop` に対応 `start..1..stop` します。例: は、 `1..2..7` シーケンス $ \{ 1、3、5、7 $ を表し \} ます。
- この `String` 型は、作成後にユーザーに対して非透過の Unicode 文字のシーケンスです。
  この型は、エラーまたは診断イベントが発生した場合に、従来のホストにメッセージを報告するために使用されます。
- `Unit`型は、1つの値のみを許可する型です `()` 。 
  この型は、Q # 関数または操作が情報を返さないことを示すために使用されます。 
- この `Qubit` 型は、クォンタムビットまたは qubit を表します。
   `Qubit`はユーザーに対して非透過的です。他の操作に渡す場合を除き、これらの操作で可能な操作は、id (等値) をテストすることだけです。
   最終的に、に対するアクション `Qubit` は、クォンタムプロセッサ (またはシミュレーション) で組み込み命令を呼び出すことによって実装されます。
- この `Pauli` 型は、4つのシングル qubit のいずれかの演算子を表します。
   この型は、回転の基本操作を表し、測定対象の観測対象を指定するために使用されます。
   これは `PauliI` 、 `PauliX` `PauliY` `PauliZ` 型の定数である、、、およびの4つの値を持つ列挙型 `Pauli` です。
- 型は、 `Result` 測定の結果を表します。
   これは、 `One` `Zero` 型の定数であるとという2つの値を持つ列挙型 `Result` です。
   `Zero`+ 1 eigenvalue が測定されたことを示します。`One`-1 eigenvalue を示します。

、、、、、、、およびの各定数 `true` `false` は、 `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` Q # で予約されているすべての記号です。

## <a name="array-types"></a>配列型

有効な Q # 型が指定され `'T` ている場合、型の値の配列を表す型があり `'T` ます。
この配列型は、やなど、として表され `'T[]` `Qubit[]` `Int[][]` ます。
たとえば、整数のコレクションが示され、 `Int[]` 値の配列の配列が `(Bool, Pauli)` 示され `(Bool, Pauli)[][]` ます。

2番目の例では、これは、四角形の2次元配列ではなく、配列のジャグ配列を表すことに注意してください。
Q # では、四角形多次元配列はサポートされていません。

配列の値は、のように、配列の要素を角かっこで囲むことによって、Q # のソースコードで記述でき `[PauliI, PauliX, PauliY, PauliZ]` ます。
配列リテラルの型は、配列内のすべての項目の共通基本型によって決定されます。 そのため、共通の基本型を持たない要素を含む配列を構築しようとすると、エラーが発生します。  
この例については、「[呼び出しの配列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)」を参照してください。

> [!WARNING]
> 配列の要素は、配列の作成後に変更することはできません。
> [更新と再割り当てのステートメント](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)、または[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用して、変更された配列を作成できます。

または、キーワードを使用して、配列のサイズから配列を作成することもでき `new` ます。

```qsharp
let zeros = new Int[13];
// new also allows for creating empty arrays:
let emptyRegister = new Qubit[0];
```

どちらの場合も、配列が構築されると、コア関数を `Length` 使用して要素の数をとして取得でき `Int` ます。
配列は、角かっこを使用して下付き文字にすることができます。また、添字は型または型のいずれかで、 `Int` `Range` 1 つの要素または配列の要素のサブセットを含む新しい配列を取得します。
配列の添字は0から始まります。

```qsharp
let arr = [10, 11, 36, 49];
let ten = arr[0]; // 10
let odds = arr[1..2..4]; // [11, 49]
```

## <a name="tuple-types"></a>タプル型

0個以上の異なる型を指定した場合は、 `T0` `T1` `Tn` 新しい*タプル型*をとして表すことができます `(T0, T1, ..., Tn)` 。
新しいタプル型を構築するために使用される型は、のように、それ自体をタプルにすることができ `(Int, (Qubit, Qubit))` ます。
ただし、このような入れ子は常に有限ですが、タプル型は、それ自体を含む状況では使用できません。

新しいタプル型の値は、組の各型の値のシーケンスによって形成されるタプルです。
たとえば、 `(3, false)` は、型がタプル型であるタプルです `(Int, Bool)` 。
組、配列の組、サブタプルの組などの配列を作成できます。

Q # 0.3 の場合、 `Unit` は空のタプルの*型*の名前です。 `()` は空のタプル*値*に使用されます。

タプルインスタンスは変更できません。
Q # には、作成されたタプルの内容を変更する機構が用意されていません。

タプルは、1つの値に値をまとめて収集し、それらを簡単に渡すことができるようにするために、Q # 全体で使用される強力な概念です。
特に、タプル表記を使用すると、すべての操作と呼び出し可能が厳密に1つの入力を受け取り、ただ1つの出力を返すことができます。

### <a name="singleton-tuple-equivalence"></a>シングルトンタプルの等価性

またはのように、シングルトン (単一要素) の組を作成することもでき `('T1)` `(5)` `([1,2,3])` ます。
ただし、Q # は、シングルトンタプルを、囲まれた型の値と完全に等価なものとして扱います。
つまり、との間、との間、 `5` `(5)` `5` `(((5)))` または `(5, (6))` と `(5, 6)` の間に違いはありません。
書き込み用に書き込みを行うのと同じです `(5)+3` `5+3` 。両方の式がに評価され `8` ます。

この等価性は、代入式や式など、すべての目的に適用されます。
任意の式を指定すると、かっこで囲まれた同じ式が同じ型の式になります。
たとえば、 `(7)` は式、は `Int` `([1,2,3])` の配列型の式、は型の式です `Int` `((1,2))` `(Int, Int)` 。

特に、これは、入力タプルまたは出力タプル型が1つのフィールドを持つ演算または関数は、1つの引数を受け取るか、単一の値を返すと考えることができます。

このプロパティは、_シングルトンタプルの等価性_と呼ばれています。


## <a name="user-defined-types"></a>ユーザー定義型

ユーザー定義型の宣言は、キーワード、 `newtype` その後にユーザー定義型の名前、 `=` 有効な型指定、および終端のセミコロンで構成されます。

例:

```qsharp
newtype PairOfInts = (Int, Int);
```

各 Q # ソースファイルは、任意の数のユーザー定義型を宣言できます。
型名は名前空間内で一意である必要があり、操作名および関数名と競合しない可能性があります。

基本型が同一の場合でも、ユーザー定義型は区別されます。
特に、基になる型が同一であっても、2つのユーザー定義型の値を自動的に変換することはできません。

### <a name="named-vs-anonymous-items"></a>名前付き項目と匿名項目

Q # ファイルでは、任意の有効な型の単一の値を含む新しい名前付きの型を定義できます。
任意のタプル型では、ステートメントを使用して、 `T` のサブタイプである新しいユーザー定義型を宣言でき `T` `newtype` ます。
たとえば、 @"microsoft.quantum.math" 名前空間では、複素数はユーザー定義型として定義されます。

```qsharp
newtype Complex = (Double, Double);
```
このステートメントは、型の2つの匿名項目を持つ新しい型を作成し `Double` ます。   

ユーザー定義型では、匿名項目以外に、Q # バージョン0.7 以降の*名前付き項目*もサポートされます。 たとえば、 `Re` 複素数の実数部と虚数部を表す double 型の to 項目という名前を付けることができ `Im` ます。 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
ユーザー定義型の1つの項目に名前を付けることは、すべての項目に名前を付ける必要があることを意味するわけではありません。名前付き項目と名前のない項目の任意の組み合わせがサポートされます。 さらに、内部項目にもという名前を付けることができます。
たとえば、 `Nested` 次に定義されている型には基になる型があり、その中に `(Double, (Int, String))` は型の項目だけが指定され、 `Int` 他のすべての項目は匿名になります。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

名前付き項目には、*アクセス演算子*を使用して直接アクセスできるという利点があり `::` ます。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

複雑なタプル型の短いエイリアスを提供するだけでなく、そのような型を定義する大きな利点の1つは、特定の値の意図を文書化できることです。
の例に戻る `Complex` と、ユーザー定義型として2d 極座標座標を定義することもできます。

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

との両方 `Complex` に基になる型がある場合でも、 `Polar` `(Double, Double)` 2 つの型は完全には互換性がありません。これにより、極座標を使用して複雑な数値演算関数を誤って呼び出した場合のリスクを最小限に抑えることができます。
このように、ユーザー定義型は F # のレコードと同様のロールを持ちます。たとえば、 


#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>ラップ解除演算子を使用した匿名項目へのアクセス

一方、匿名の項目にアクセスするには、後置演算子を使用して、ラップされた値を最初に抽出する必要があり `!` ます。
"ラップ解除" 演算子を `!` 使用すると、ユーザー定義型に含まれる値を抽出できます。
このような "ラップ解除" 式の型は、ユーザー定義型の基になる型です。 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

ラップ解除演算子は、ラップのレイヤーを1つだけラップ解除します。
複数のラップ解除演算子は、乗算された値にアクセスするために使用できます。

次に例を示します。

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

ラップ解除演算子の詳細については、 [「Q # の型式」](xref:microsoft.quantum.guide.expressions)を参照してください。

### <a name="creating-values-of-user-defined-types"></a>ユーザー定義型の値の作成

ユーザー定義型の値は、対応する型コンストラクターを呼び出すことによって作成できます。

```
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

または、[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用して、既存の値から新しい値を作成することもできます。 配列の場合と同様に、このような式は、指定された名前付き項目を除き、元の式のすべての項目の値をコピーします。 これらの値は、式の右辺に定義されている値に設定されます。 配列項目に使用できるその他の言語構成要素は[、たとえば、](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)ユーザー定義型の名前付き項目にも存在します。

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


## <a name="operation-and-function-types"></a>操作と関数の型

呼び出し可能の基本型は、またはとして記述され `('Tinput => 'Tresult)` `('Tinput -> 'Tresult)` ます。ここで、との両方 `'Tinput` `'Tresult` が型です。
これらは呼び出し可能の*シグネチャ*と呼ばれます。

すべての Q # 呼び出しが、1つの値を入力として受け取り、1つの値を出力として返すと見なされます。
入力値と出力値は、どちらもタプルにすることができます。
結果が返されない呼び出しの可能性があり `Unit` ます。
入力がない callables は、空のタプルを入力として受け取ります。

> [!NOTE]
> 最初の形式であるは、 `=>` 操作に使用されます。2番目の形式は、関数の場合はとです `->` 。
> たとえば、は、 `((Qubit, Pauli) => Result)` 可能な単一 qubit 測定演算の署名を表します。
*関数*型は、シグネチャによって完全に指定されます。
たとえば、角度のサインを計算する関数には型があり `(Double -> Double)` ます。

*操作---で*はなく、操作の種類の一部として表される特定の追加の特性を持つ関数---。 このような特性には、操作が*サポートする機能*に関する情報が含まれます。
たとえば、操作の実行を他の qubits の状態で条件指定できる場合は、ファンクタをサポートする必要があり `Controlled` ます。操作に逆のがある場合は、ファンクタをサポートする必要があり `Adjoint` ます。 関数と演算の詳細については、「 [Q # の操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。ここでは、操作のシグネチャを変更する方法について説明します。

操作の種類の and またはファンクタのサポートを必要とするために `Controlled` `Adjoint` 、対応する特性を示す注釈を追加する必要があります。
注釈 (例:) は、操作が制御可能であることを `is Ctl` 示します。つまり `(Qubit => Unit is Ctl)` 、別の qubit または qubit の状態に対して実行条件が指定されている---です。 同様に、は、 `is Adj` 操作に adjoint があることを示します。または、操作を連続して適用した後、その状態を状態に変更せずにそのまま状態を維持する "逆" にすることもできます。 

その型の操作がとの両方をサポートしていることを要求する場合は、 `Adjoint` `Controlled` これをとして表現でき `(Qubit => Unit is Adj + Ctl)` ます。 たとえば、組み込みの P# li <xref:microsoft.quantum.intrinsic.x> 操作には型があり `(Qubit => Unit is Adj + Ctl)` ます。 

すべての機能をサポートしていない操作の種類は、入力と出力の型だけで指定し、追加の注釈は付けません。

### <a name="type-parameterized-functions-and-operations"></a>型パラメーターの関数と操作

呼び出し可能な型には、型パラメーターを含めることができます。
型パラメーターは、1つの引用符で始まる記号で示されます。たとえば、 `'A` は有効な型パラメーターです。
型パラメーター化された呼び出しを定義する方法の詳細については、 [Q # ページの操作と関数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)をご確認ください。

1つのシグネチャで、型パラメーターが複数回出現する場合があります。
たとえば、別の関数を配列の各要素に適用し、収集された結果を返す関数は、シグネチャを持ち `(('A[], 'A->'A) -> 'A[])` ます。
同様に、2つの操作の構成を返す関数にはシグネチャがある場合があり `((('A=>'B), ('B=>'C)) -> ('A=>'C))` ます。

型パラメーターの呼び出し可能な呼び出しを呼び出すときは、同じ型パラメーターを持つすべての引数が同じ型である必要があります。

Q # には、型パラメーターに置き換えられる可能性のある型を制限する機構が用意されていません。

## <a name="next-steps"></a>次の手順

Q # 言語を構成するすべての型を確認したので、 [q # の式を入力](xref:microsoft.quantum.guide.expressions)して、これらのさまざまな型の式を作成および操作する方法を確認できます。


