---
title: 型Q#
description: プログラミング言語で使用されるさまざまな型について説明し Q# ます。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.types
no-loc:
- Q#
- $$v
ms.openlocfilehash: b034af0b1d3b967b5680403341813407e4412f93
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869598"
---
# <a name="types-in-no-locq"></a>型Q#

この記事では、 Q# 型モデルと、型を指定して操作するための構文について説明します。 これらの型の式を作成および操作する方法の詳細については、「[型式](xref:microsoft.quantum.guide.expressions)」を参照してください。

Q#は*厳密に型指定*された言語であることに注意してください。これは、これらの型を慎重に使用することで、コンパイル時にプログラムに関して強力な保証を提供するのに役立ち Q# ます。
最も強力な保証を提供するには、の型間の変換を、 Q# その変換を表す関数の呼び出しを使用して明示的に行う必要があります。 
Q#には、名前空間の一部として、さまざまな関数が用意されて <xref:microsoft.quantum.convert> います。
一方、互換性のある型へのアップキャストは暗黙的に行われます。 

Q#には、直接使用されるプリミティブ型と、他の型から新しい型を生成するためのさまざまな方法が用意されています。
この記事の残りの部分では、それぞれについて説明します。

## <a name="primitive-types"></a>プリミティブ型

言語には、 Q# 次の*プリミティブ型*が用意されています。これらはすべて、プログラムで直接使用でき Q# ます。 これらのプリミティブ型を使用して、新しい型を作成することもできます。

- この `Int` 型は、64ビット符号付き整数 (、、など) を表し `2` `107` `-5` ます。
- 型は、、、など、 `BigInt` 任意のサイズの符号付き整数を表し `2L` `107L` `-5L` ます。
   この型は .NET に基づいています。<xref:System.Numerics.BigInteger>
   型のパラメーターに変換されます。

- 型は、、、など `Double` の倍精度浮動小数点数を表し `0.0` `-1.3` `4e-7` ます。
- 型は、 `Bool` またはのいずれかのブール値を表し `true` `false` ます。
- この `Range` 型は、によって示される整数のシーケンスを表し `start..step..stop` ます。これは、ステップが省略可能であることを示します。 
   たとえば、は `start .. stop` に対応 `start..1..stop` し、は `1..2..7` シーケンス $ \{ 1、3、5、7 $ を表し \} ます。
- この `String` 型は、作成後にユーザーに対して非透過の Unicode 文字のシーケンスです。
  エラーまたは診断イベントが発生した場合に、この種類を使用して、 `string` 従来のホストにメッセージを報告します。
- `Unit`型は、値を1つだけ持つことができ `()` ます。 
  Q#関数または操作が情報を返さないことを示すには、この型を使用します。 
- この `Qubit` 型は、クォンタムビットまたは qubit を表します。
   `Qubit`はユーザーに対して非透過的です。 他の操作に渡す場合を除き、これらの操作で可能な操作は、id (等値) をテストすることだけです。
   最終的には、 `Qubit` クォンタムプロセッサ (またはクォンタムシミュレーター) で組み込み命令を呼び出すことによって、に対するアクションを実装します。
- この `Pauli` 型は、4つのシングル qubit のいずれかの演算子を表します。
   この型を使用して、回転の基本操作を表し、測定対象の観測対象を指定します。
   これは `PauliI` 、 `PauliX` `PauliY` `PauliZ` 型の定数である、、、およびの4つの値を持つ列挙型 `Pauli` です。
- 型は、 `Result` 測定の結果を表します。
   これは、 `One` `Zero` 型の定数であるとの2つの値を持つ列挙 `Result` 型です。
   `Zero`+ 1 eigenvalue が測定されたことを示します。`One`-1 eigenvalue が測定されたことを示します。

、、、、、、、およびの各定数 `true` `false` は、 `PauliI` `PauliX` `PauliY` `PauliZ` `One` `Zero` で予約されているすべての記号です Q# 。

## <a name="array-types"></a>配列型

* 有効な型について Q# は、その型の値の配列を表す型があります。
    たとえば、とは、 `Qubit[]` `(Bool, Pauli)[]` `Qubit` 値と組値の配列を表し `(Bool, Pauli)` ます。

* 配列の配列も有効です。 前の例を展開すると、配列の配列 `(Bool, Pauli)` が示され `(Bool, Pauli)[][]` ます。

> [!NOTE] 
> この例は、 `(Bool, Pauli)[][]` 四角形の2次元配列ではなく、配列のジャグ配列を表しています。 Q#は、四角形多次元配列をサポートしていません。

* 配列の値は Q# 、のように、配列の要素を角かっこで囲むことによって、ソースコードで記述でき `[PauliI, PauliX, PauliY, PauliZ]` ます。
配列内のすべての項目の共通基本型によって、配列リテラルの型が決定されます。 そのため、共通の基本型を持たない要素を含む配列を構築すると、エラーが発生します。  
例については、「[呼び出し許容の配列](xref:microsoft.quantum.guide.expressions#arrays-of-callables)」を参照してください。

    > [!WARNING]
    > 作成された配列の要素は変更できません。
    > 変更された配列を作成するには、[更新と再割り当てのステートメント](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)、または[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用します。

* または、キーワードを使用して、配列のサイズから配列を作成することもでき `new` ます。

    ```qsharp
    let zeros = new Int[13];
    // you can also use new for creating empty arrays:
    let emptyRegister = new Qubit[0];
    ```

* `Length`配列からの要素の数をとして取得するには、core 関数を使用し `Int` ます。
* 配列は、配列の要素のサブセットを含む単一の要素または新しい配列を取得するために、添字にすることができます。
配列の添字は0から始まり、型または型である必要があり `Int` `Range` ます。

    ```qsharp
    let arr = [10, 11, 36, 49];
    let ten = arr[0]; // 10
    let odds = arr[1..2..4]; // [11, 49]
    ```

## <a name="tuple-types"></a>タプル型

タプルは、 Q# 値をまとめて1つの値に収集し、それらを簡単に渡すことができるように、全体で使用される強力な概念です。
特に、組表記を使用すると、すべての操作と呼び出し可能が厳密に1つの入力を受け取り、1つの出力のみを返すことを表現できます。

* 0個以上の異なる型 `T0` ( `T1` ,...) を指定する `Tn` と、新しい*タプル型*をとして表すことができます。 `(T0, T1, ..., Tn)`
新しいタプル型を構築するために使用される型は、のように、それ自体をタプルにすることができ `(Int, (Qubit, Qubit))` ます。
ただし、このような入れ子は常に有限ですが、タプル型は、それ自体を含む状況では使用できません。

* 新しいタプル型の値は、組の各型の値のシーケンスによって形成されるタプルです。
たとえば、 `(3, false)` は、型がタプル型であるタプルです `(Int, Bool)` 。
組の配列、配列の組、サブタプルの組などを作成することもできます。

* 0.3 の Q# 場合、 `Unit` は空のタプルの*型*の名前です。 `()` は空のタプルの*値*に使用されます。

* タプルインスタンスは変更できません。
Q#には、作成されたタプルの内容を変更する機構が用意されていません。



### <a name="singleton-tuple-equivalence"></a>シングルトンタプルの等価性

またはなど、シングルトン (単一要素) の組を作成することができ `('T1)` `(5)` `([1,2,3])` ます。
ただし、では、 Q# シングルトンタプルは、囲まれた型の値と等価として扱われます。
つまり、との間、との間、 `5` `(5)` `5` `(((5)))` または `(5, (6))` と `(5, 6)` の間に違いはありません。
書き込みの場合と同じように記述できます。 `(5)+3` `5+3` 両方の式がに評価され `8` ます。

この等価性は、代入式や式など、すべての目的に適用されます。
任意の式を指定すると、かっこで囲まれた同じ式が同じ型の式になります。
たとえば、 `(7)` は型の式、は型の式、は `Int` `([1,2,3])` `Int[]` `((1,2))` 型の `(Int, Int)` 式です。

特に、これは、1つの引数を受け取るか、単一の値を返すとして、入力タプルまたは出力タプル型に1つのフィールドがある操作または関数を表示できることを意味します。

このプロパティは、_シングルトンタプルの等価性_と呼ばれています。


## <a name="user-defined-types"></a>ユーザー定義型

ユーザー定義型の宣言は、キーワード、 `newtype` その後にユーザー定義型の名前、 `=` 有効な型指定、および終端のセミコロンで構成されます。

次に例を示します。

```qsharp
newtype PairOfInts = (Int, Int);
```
    
* 各 Q# ソースファイルは、任意の数のユーザー定義型を宣言できます。
* 型名は名前空間内で一意である必要があり、操作名および関数名と競合しない可能性があります。
* 基本型が同一であっても、ユーザー定義型は区別されません。
特に、基になる型が同一であっても、2つのユーザー定義型の値を自動的に変換することはできません。

### <a name="named-vs-anonymous-items"></a>名前付き項目と匿名項目

ファイルでは、 Q# 任意の有効な型の単一の値を含む新しい名前付きの型を定義できます。
任意のタプル型では、ステートメントを使用して、 `T` のサブタイプである新しいユーザー定義型を宣言でき `T` `newtype` ます。
たとえば、 @"microsoft.quantum.math" 名前空間では、複合数値はユーザー定義型として定義されます。

```qsharp
newtype Complex = (Double, Double);
```
このステートメントは、型の2つの匿名項目を持つ新しい型を作成し `Double` ます。   

ユーザー定義型では、匿名項目以外に、バージョン0.7 以降の*名前付き項目*もサポートされ Q# ます。 たとえば、 `Re` 複素数の実数部と虚数部を表す double 型の項目に、という名前を指定でき `Im` ます。 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
ユーザー定義型の1つの項目に名前を付けることは、すべての項目に名前を付ける必要があることを意味するわけではありません。名前付き項目と名前のない項目の任意の組み合わせがサポートされます。 さらに、内部項目にもという名前を付けることができます。
次の例に示すように、型には `Nested` 基になる型があり、型 `(Double, (Int, String))` の項目だけ `Int` が名前付きで、他のすべての項目は匿名になります。 

```qsharp
newtype Nested = (Double, (ItemName : Int, String)); 
```

名前付き項目には、*アクセス演算子*を使用して直接アクセスできるという利点があり `::` ます。 

```qsharp
function ComplexAddition(c1 : Complex, c2 : Complex) : Complex {
    return Complex(c1::Re + c2::Re, c1::Im + c2::Im);
}
```

潜在的に複雑なタプル型の短いエイリアスを提供するだけでなく、そのような型を定義することの大きな利点は、特定の値の意図を文書化できることです。
の例に戻る `Complex` と、ユーザー定義型として2d 極座標座標を定義することもできます。

```qsharp
newtype Polar = (Radius : Double, Phase : Double);
```

との両方に基になる型がある場合でも、 `Complex` `Polar` `(Double, Double)` 2 つの型は完全には互換性がないため Q# 、極座標を使用して複雑な数値演算関数を誤って呼び出した場合のリスクを最小限に抑えることができます。

#### <a name="access-anonymous-items-with-the-unwrap-operator"></a>ラップ解除演算子を使用した匿名項目へのアクセス

匿名項目にアクセスするには、まず、後置演算子を使用して、ラップされた値を抽出し `!` ます。
"ラップ解除" 演算子を使用 `!` すると、ユーザー定義型に含まれる値を抽出できます。
このような "ラップ解除" 式の型は、ユーザー定義型の基になる型です。 

```qsharp
function PrintedMessage(value : Nested) : Unit {
    let (d, (_, str)) = value!;
    Message ($"{str}, value: {d}");
}
```

単一のラップ解除演算子は、ラップの1つのレイヤーをラップ解除します。 多重ラップされた値にアクセスするには、複数のラップ解除演算子を使用します。

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

ラップ解除演算子の詳細については、「 [」 Q# の「型式](xref:microsoft.quantum.guide.expressions)」を参照してください。

### <a name="creating-values-of-user-defined-types"></a>ユーザー定義型の値の作成

対応する型コンストラクターを呼び出すことによって、ユーザー定義型の値を作成します。

```qsharp
let realUnit = Complex(1.0, 0.0);
let imaginaryUnit = Complex(0.0, 1.0);
```

または、[コピーと更新の式](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions)を使用して、既存の値から新しい値を作成することもできます。 配列の場合と同様に、コピーと更新の式では、指定した名前付き項目を除き、元の式のすべての項目値がコピーされます。 これらの例外の場合、これらの項目の値は、式の右辺に定義されている値になります。 配列項目に使用できるその他の言語構成要素 (たとえば、 [update および-再割り当てステートメント](xref:microsoft.quantum.guide.variables#update-and-reassign-statements)) は、ユーザー定義型の名前付き項目にも存在します。

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

* ユーザー定義型は、他の型を使用する場所であればどこでも使用できます。
特に、ユーザー定義型の配列を定義し、タプル型の要素としてユーザー定義型を含めることができます。

* 再帰型構造を作成することはできません。
つまり、ユーザー定義型を定義する型を、ユーザー定義型の要素を含むタプル型にすることはできません。
一般に、ユーザー定義型は相互に循環依存関係がない場合があるため、次の型定義のセットは無効になります。

    ```qsharp
    newtype TypeA = (Int, TypeB);
    newtype TypeB = (Double, TypeC);
    newtype TypeC = (TypeA, Range);
    ```


## <a name="operation-and-function-types"></a>操作と関数の型

次の型 `'Tinput` が `'Tresult` あります。

* `('Tinput => 'Tresult)`は、任意の*操作*の基本型です。たとえば、のように `((Qubit, Pauli) => Result)` なります。
* `('Tinput -> 'Tresult)`は、任意の*関数*の基本型です。たとえば、のように `(Int -> Int)` なります。 

これらは呼び出し可能の*シグネチャ*と呼ばれます。

* すべて Q# の呼び出しが、1つの値を入力として受け取り、1つの値を出力として返します。
* 入力値と出力値の両方に組を使用できます。
* 結果がない呼び出しの可能性がある場合は、を返し `Unit` ます。
* 入力がない callables は、空のタプルを入力として受け取ります。

### <a name="functors"></a>ファンクター

*関数*型は、シグネチャによって完全に指定されます。 たとえば、角度のサインを計算する関数には型があり `(Double -> Double)` ます。 

*操作に*は、操作の種類の一部として表現されるいくつかの追加の特性があります。 このような特性*には、操作でサポート*される機能に関する情報が含まれます。
たとえば、操作の実行が他の qubits の状態に依存している場合は、ファンクタをサポートする必要があり `Controlled` ます。操作に逆のがある場合は、ファンクタをサポートする必要があり `Adjoint` ます。

> [!NOTE]
> この記事では、操作シグネチャの変更についてのみ説明します。 関数と操作の詳細については、「 [」の Q# 「操作と関数](xref:microsoft.quantum.guide.operationsfunctions)」を参照してください。 

`Controlled`操作の種類でおよび/またはファンクタのサポートを要求するには、 `Adjoint` 対応する特性を示す注釈を追加する必要があります。
注釈 `is Ctl` (たとえば、) は、 `(Qubit => Unit is Ctl)` 操作が制御可能であることを示します。 つまり、その実行は、別の qubit または qubit の状態に依存します。 同様に、注釈は、操作に adjoint があることを示します。つまり、 `is Adj` 操作を連続して適用した後、その状態を状態に変更せずに状態を維持する "逆" にすることができます。 

その型の操作がとのファンクタの両方をサポートしていることを要求する場合は、 `Adjoint` `Controlled` これをとして表現でき `(Qubit => Unit is Adj + Ctl)` ます。 たとえば、組み込みの P# li <xref:microsoft.quantum.intrinsic.x> 操作には型があり `(Qubit => Unit is Adj + Ctl)` ます。 

すべての機能をサポートしていない操作の種類は、入力と出力の型だけで指定し、追加の注釈は付けません。

### <a name="type-parameterized-functions-and-operations"></a>型パラメーターの関数と操作

呼び出し可能な型には、*型パラメーター*を含めることができます。
1つの引用符で始まる記号を使用して、型パラメーターを指定します。たとえば、 `'A` は有効な型パラメーターです。
型パラメーター化された呼び出しを定義する方法の詳細と詳細については、「 [」の Q# 「操作と関数](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)」を参照してください。

1つのシグネチャで、型パラメーターが複数回出現する場合があります。
たとえば、別の関数を配列の各要素に適用し、収集された結果を返す関数は、シグネチャを持ち `(('A[], 'A->'A) -> 'A[])` ます。
同様に、2つの操作の構成を返す関数には、シグネチャがあり `((('A=>'B), ('B=>'C)) -> ('A=>'C))` ます。

型パラメーターの呼び出し可能な呼び出しを呼び出す場合は、同じ型パラメーターを持つすべての引数が同じ型である必要があります。

Q#には、ユーザーが型パラメーターの代わりに使用できる型を制約する機構が用意されていません。

## <a name="next-steps"></a>次のステップ

言語を構成するすべての型を確認したので Q# 、「 [」の Q# 「型式](xref:microsoft.quantum.guide.expressions)」を参照して、これらのさまざまな型の式を作成および操作する方法を学習してください。
