---
title: Q の操作と関数#
description: 操作と関数を定義して呼び出す方法、および制御される操作と adjoint 操作の特殊化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 08eaf150a38afd789f8a23f567ff111d002bac07
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884218"
---
# <a name="operations-and-functions-in-q"></a>Q の操作と関数#

## <a name="defining-new-operations"></a>新しい操作の定義

操作は Q # の中核です。
宣言した後は、たとえばシミュレーターを使用するか、Q # 内の他の操作によって、従来の .NET アプリケーションから呼び出すことができます。
Q # で定義されている各操作は、その言語で定義されている組み込みの組み込み操作を含む、他の任意の数の操作を呼び出すことができます。 Q # がこれらの組み込み操作を定義する具体的な方法は、ターゲットコンピューターによって異なります。
コンパイルされると、各操作はターゲットコンピューターに提供できる .NET クラス型として表されます。

各 Q # ソースファイルでは、任意の数の操作を定義できます。
操作名は名前空間内で一意である必要があり、型名または関数名と競合することはできません。

操作の宣言は、キーワード、 `operation` その後に操作の名前であるシンボル、操作の引数を定義する型指定された識別子のタプル、コロン `:` 、操作の結果の型を記述する型の注釈、オプションで操作の特性、左中かっこ、および操作の宣言の本体 (中かっこで囲まれた) で構成され `{ }` ます。

各操作は、入力を受け取り、出力を生成し、1つまたは複数の操作の特殊化の実装を指定します。
この記事の各セクションでは、考えられる特殊化、およびそれらを定義して呼び出す方法について詳しく説明します。
ここでは、次の操作について考えてみます。この操作では、既定の本文の特殊化のみが定義され、入力として1つの qubit が使用され、 <xref:microsoft.quantum.intrinsic.x> その入力に対して組み込み演算が呼び出されます。

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

キーワードは `operation` 操作の定義を開始し、その後に名前を付けます。ここでは、 `BitFlip` です。
次に、入力の型が、 `Qubit` `target` 新しい操作内の入力を参照するために、名前と共に定義されます。
最後に、は、 `Unit` 操作の出力が空であることを定義します。
`Unit`は、 `void` C# およびその他の命令型言語のと同様に使用され、 `unit` F # およびその他の関数型言語のと同じです。

操作では、より興味深い型も返すことができ `Unit` ます。
たとえば、操作は、 <xref:microsoft.quantum.intrinsic.m> 測定を実行したことを表す型の出力を返し `Result` ます。  操作から別の操作に渡すことも、キーワードを使用して `let` 新しい変数を定義することもできます。

このアプローチでは[、次の](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)ように低レベルでクォンタム操作と対話する古典的な計算を表すことができます。

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Q # の各操作は、1つの入力だけを受け取り、1つの出力のみを返します。
> 複数の入力と出力は、複数の値をまとめて1つの値にまとめる*タプル*を使用して表されます。
> この点について、Q # は "タプルインタプル" 言語です。
> この概念に従うと、空のかっこのセットは、 `()` 型を持つ "空の" タプルとして読み取る必要があり `Unit` ます。

## <a name="controlled-and-adjoint-operations"></a>制御と Adjoint の操作

Q # での多くの操作の場合と同様に、操作によって、 *adjointed*または*制御*されたときの操作の動作を定義することができます。 操作の*adjoint*特殊化では、操作の "逆" の動作を指定します。一方、*制御*された特殊化では、そのアプリケーションが特定のクォンタムレジスタの状態に条件を適用する場合の操作方法を指定します。

クォンタム操作の adjoints は、クォンタムコンピューティングの多くの側面にとって非常に重要です。 有用な Q&a プログラミング手法と共に説明されているこのような状況の例については、この記事の[活用](#conjugations)を参照してください。 

操作の制御されたバージョンは、すべてのコントロール qubits が指定された状態にある場合にのみ、基本操作を効果的に適用する新しい操作です。
コントロール qubits が法則内にある場合、基本操作は一貫の適切な部分に適用されます。
したがって、制御された操作は、多くの場合、entangを生成するために使用されます。

当然ながら、制御された*adjoint*特殊化も存在し、操作の adjoint の制御されたアプリケーションを指定できます。

> [!NOTE]
> $U $ が、操作によって実装されるユニタリ変換である場合 `U` 、は、 `Adjoint U` $U ^ \ ダガー $ のように、複雑な共役の転置である、この変換を表します。
> 操作を連続して適用した後、その adjoint を状態にしたまま、状態は変更されません。これは、$UU ^ & ダガー = U ^ \ ダガー U = \ id $ (id マトリックス) に示されています。
> 制御された操作のユニタリ表現は少し微妙なですが、「[クォンタムコンピューティングの概念: 複数の qubits](xref:microsoft.quantum.concepts.multiple-qubits)」で詳細を確認できます。

次のセクションでは、これらのさまざまな特殊化を Q # コードで呼び出す方法と、それらをサポートする操作を定義する方法について説明します。

### <a name="calling-operation-specializations"></a>呼び出し操作の特殊化

Q # の*ファンクタ*は、別の操作から新しい操作を定義するファクトリです。
Q # の2つの標準のファンクターは `Adjoint` と `Controlled` です。

新しい操作の実装を定義するときに、基本操作の実装にアクセスできます。
したがって、関数は、従来の上位レベルの関数よりも複雑な関数を実行できます。 この型は、Q # 型システムには含まれていません。 そのため、変数にバインドしたり、引数として渡したりすることはできません。 

新しい操作を返す操作に適用して、ファンクタを使用します。
たとえば、 `Adjoint` ファンクタを操作に適用すると、 `Y` 新しい操作が返さ `Adjoint Y` れます。 他の操作と同様に、新しい操作を呼び出すことができます。
またはの機能のアプリケーションをサポートする操作の場合 `Adjoint` `Controlled` 、戻り値の型は必ずしもである必要があり `Unit` ます。 

#### <a name="adjoint-functor"></a>`Adjoint`クタ

したがって、は、 `Adjoint Y(q1)` `Adjoint` ファンクタを操作に適用して `Y` 新しい操作を生成し、その新しい操作をに適用し `q1` ます。
新しい操作のシグネチャと型は、基本操作と同じ `Y` です。
特に、新しい操作は、をサポートし、基本操作が実行された場合に `Adjoint` のみをサポートし `Controlled` ます。
`Adjoint`ファンクタは独自の逆です。つまり、 `Adjoint Adjoint Op` は常にと同じです `Op` 。

#### <a name="controlled-functor"></a>`Controlled`クタ

同様に、は、 `Controlled X(controls, target)` `Controlled` ファンクタを操作に適用して `X` 新しい操作を生成し、その新しい操作をとに適用し `controls` `target` ます。

> [!NOTE]
> Q # では、制御されたバージョンは常に制御 qubits の配列を受け取り、制御は常に計算 ( `PauliZ` ) 状態 ($ \ket $) にあるすべてのコントロール qubits に基づいてい `One` {1} ます。
> 他の状態に基づいて制御するには、制御された操作の前に適切なユニタリ操作を制御 qubits に適用し、次に、制御された操作の後に、逆操作の実行を適用します。
> たとえば、次のようになります。制御され `X` た操作の前後に制御 qubit に操作を適用すると、操作は `Zero` その qubit の状態 ($ \ket $) を制御し、状態の制御の前後に操作を適用します。これは、状態 {0} `H` で `PauliX` `One` はなく、p li X, $ \ket {-} \mathrel{: =} (\ket {0} -\ket {1} )//sqrt {2} $ `PauliZ` `One` の値です。

操作式を指定した場合は、ファンクタを使用して新しい演算式を作成でき `Controlled` ます。
新しい操作の署名は、元の操作の署名に基づいています。
結果の型は同じですが、入力の型は2つのタプルで、最初の要素としてコントロール qubit を保持し、2番目の要素として元の操作の引数を保持します。
新しい操作は `Controlled` をサポートし、元の操作が行われた場合にのみをサポートし `Adjoint` ます。

元の操作で1つの引数のみを取得した場合、[シングルトンタプルの等価性](xref:microsoft.quantum.guide.types)がここで行われます。
たとえば、 `Controlled X` は操作の制御されたバージョンです `X` 。 
`X`に型がある `(Qubit => Unit is Adj + Ctl)` ため、 `Controlled X` 型があります `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` 。シングルトンタプルの等価性があるため、これはと同じ `((Qubit[], Qubit) => Unit is Adj + Ctl)` です。

基本操作に複数の引数を指定する場合は、操作の制御されたバージョンの対応する引数をかっこで囲み、それらをタプルに変換してください。
たとえば、 `Controlled Rz` は操作の制御されたバージョンです `Rz` 。 
`Rz`に型がある `((Double, Qubit) => Unit is Adj + Ctl)` ため、 `Controlled Rz` 型は `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` です。
したがって、は `Controlled Rz(controls, (0.1, target))` の有効な呼び出しであると考えら `Controlled Rz` れます (を囲むかっこに注意して `0.1, target` ください)。

別の例として、を `CNOT(control, target)` として実装でき `Controlled X([control], target)` ます。 ターゲットを2つの制御 qubits (CCNOT) で制御する必要がある場合は、ステートメントを使用し `Controlled X([control1, control2], target)` ます。

#### `Controlled Adjoint` 

およびの各ファンクター `Controlled` `Adjoint` commute では、またはの適用に違いはありません `Controlled Adjoint Op` `Adjoint Controlled Op` 。


## <a name="defining-controlled-and-adjoint-implementations"></a>制御と Adjoint の実装の定義

前の例の最初の操作の宣言では、操作 `BitFlip` とは `DecodeSuperdense` それぞれシグネチャ `(Qubit => Unit)` とで定義されていました `((Qubit, Qubit) => (Result, Result))` 。
`DecodeSuperdense`測定値が含まれているため、これは一連の処理ではなく、adjoint 特殊化ではありません (このような操作が返す関連の要件を思い出して `Unit` ください)。
ただし、 `BitFlip` 単にユニタリ操作を実行 <xref:microsoft.quantum.intrinsic.x> するため、両方の特殊化を使用して定義することもできます。

このセクションでは、Q # 操作宣言に特殊化の存在を含める方法を詳しく説明します。したがって、またはの機能と組み合わせて呼び出すことができ `Adjoint` `Controlled` ます。
特定の特殊化を宣言するために有効であるか無効である状況の詳細については、この記事の「[特殊化を有効に定義するための状況](#circumstances-for-validly-defining-specializations)」を参照してください。

操作特性は、宣言された操作に適用できる機能の種類と、その影響を定義します。 これらの特殊化の存在は、操作のシグネチャの一部として宣言できます。特に、、、のいずれかの操作特性を持つ注釈を使用し `is Adj` `is Ctl` `is Adj + Ctl` ます。
各特殊化の実際の実装は、*暗黙的*または*明示的に*定義することができます。

### <a name="implicitly-specifying-implementations"></a>暗黙的な実装の指定

この場合、操作宣言の本体は、既定の実装だけで構成されます。 次に例を示します。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
ここでは、このような暗黙的に宣言されたそれぞれに対応する実装が、またはのいずれかのが使用された場合に実行されるように、コンパイラによって自動的に生成され `Adjoint` `Controlled` ます。

そのため、の呼び出しに `Adjoint PrepareEntangledPair` より、コンパイラは、の adjoint `CNOT` と、の adjoint を実装し `H` ます。
これらの個々の操作は自己完結型であるため、結果として得られる操作は、 `Adjoint PrepareEntangledPair` とを適用するだけで構成され `CNOT(here, there)` `H(here)` ます。
したがって、これを使用すると、前の例のをさらにコンパクトに書き込むことができます。これを行うには、 `DecodeSuperdense` の adjoint を使用して、 `PrepareEntangledPair` ありの状態を qubits のペアに変換します。

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

宣言の操作特性を持つ注釈は、コンパイラが既定の実装に基づいて他の特殊化を自動生成するために役立ちます。 

機能を使用するための操作を設計する際に考慮すべき重要な制限事項がいくつかあります。
他の操作の出力値を使用する操作のために特に特殊化されたものは、コンパイラによって自動的に生成され*ません*。これは、このような操作でステートメントの順序を変更して同じ効果を得る方法があいまいであるためです。

そのため、多くの場合、さまざまな実装を明示的に指定すると便利です。

### <a name="explicitly-specifying-implementations"></a>明示的な実装の指定

コンパイラが実装を生成できない場合は、明示的に指定できます。 このような明示的な特殊化の宣言は、適切な*生成ディレクティブ*またはユーザー定義の実装で構成されます。
次に、明示的な特殊化の例をいくつか示します。 


#### <a name="explicit-specialization-declarations"></a>明示的特殊化の宣言

Q # 操作には、次の明示的特殊化宣言を含めることができます。

- 特殊化は、 `body` 動作が適用されていない操作の実装を指定します。
- 特殊化は、 `adjoint` ファンクタが適用された操作の実装を指定し `Adjoint` ます。
- 特殊化は、 `controlled` ファンクタが適用された操作の実装を指定し `Controlled` ます。
- 特殊化は、 `controlled adjoint` との両方が適用された操作の実装を指定し `Adjoint` `Controlled` ます。
  この特殊化は `adjoint controlled` 、2つのファンクター commute から名前を付けることもできます。


操作の特殊化は、特殊化タグ (やなど) と `body` それ `adjoint` に続く次のいずれかで構成されます。

- 次に示すように、明示的な宣言。
- 特殊化を生成する*方法*をコンパイラに指示する*ディレクティブ*。次のいずれかになります。
  - `intrinsic`。ターゲットコンピューターが特殊化を提供することを示します。
  - `distribute`。およびの特殊化と共に使用され `controlled` `controlled adjoint` ます。
    と共に使用すると、 `controlled` コンパイラは、のすべての操作にを適用することによって、特殊化を計算する必要があることを示し `Controlled` `body` ます。
    と共に使用すると、特化された `controlled adjoint` `Controlled` すべての操作にを適用することによって、コンパイラが特殊化を計算する必要があることを示し `adjoint` ます。
  - `invert`。これは、を反転させることによって、コンパイラが特殊化を計算する必要があることを示し `adjoint` `body` ます。たとえば、演算の順序を逆にし、それぞれに adjoint を適用します。
    と共に使用すると、コンパイラが特殊化を反転すること `adjoint controlled` によって特殊化を計算する必要があることを示し `controlled` ます。
  - `self`。 adjoint の特殊化が特殊化と同じであることを示し `body` ます。
    `self`との特殊化では、を使用することが有効です `adjoint` `adjoint controlled` 。
    の場合 `adjoint controlled` 、 `self` `adjoint controlled` 特殊化は特殊化と同じであることを意味し `controlled` ます。
  - `auto`。コンパイラが適切なディレクティブを選択して適用する必要があることを示します。
    特殊化としてを使用することはできません `auto` `body` 。

ディレクティブとすべてには、 `auto` 末尾にセミコロンが必要 `;` です。
`auto`の明示的な宣言が指定されている場合、ディレクティブは次の生成されたディレクティブに解決され `body` ます。

- 特殊化は、 `adjoint` ディレクティブに従って生成され `invert` ます。
- 特殊化は、 `controlled` ディレクティブに従って生成され `distribute` ます。
- `adjoint controlled`の明示的な宣言が指定されている場合は、ディレクティブに従って特殊化が生成され `invert` `controlled` `adjoint` ます。それ以外の場合は、が生成され `distribute` ます。

> [!TIP]   
> 操作が自己 adjoint の場合は、generation ディレクティブを使用して adjoint または制御対象の adjoint 特殊化を明示的に指定し、 `self` コンパイラが最適化のためにその情報を使用できるようにします。

ユーザー定義の実装を含む特殊化宣言は、引数の組の後に、特殊化を実装する Q # コードを持つステートメントブロックで構成されます。
引数リストでは、 `...` は、操作全体に対して宣言された引数を表すために使用されます。
とでは、 `body` `adjoint` 引数リストは常にである必要があります `(...)` 。 `controlled` と `adjoint controlled` では、引数リストは、コントロール qubits の配列を表す記号であり、の後に `...` かっこで囲まれたを使用する必要があります (例:) `(controls,...)` 。

### <a name="examples"></a>使用例

操作の宣言は、次のように単純なものにすることができます。これにより、プリミティブな P# li X 操作が定義されます。

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
P# li X 操作の adjoint がディレクティブで定義されていることに注意して `self` ください。これは、定義によって独自の逆関数が使用されるためです `X` 。

前の `PrepareEntangledPair` 例では、コードは明示的な特殊化宣言を含む次のコードと同じです。 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
キーワードは、特殊化された `auto` 実装を生成する方法をコンパイラが決定する必要があることを示します。

#### <a name="user-defined-specialization-implementation"></a>ユーザー定義の特殊化の実装

コンパイラが特定の特殊化の実装を自動的に生成できない場合、またはより効率的な実装を指定できる場合は、実装を手動で定義できます。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
前の例では、は、本体の実装を反転することによって adjoint の特殊化が生成されることを示し、制御された `adjoint invert;` `controlled adjoint invert;` 特殊化の実装を反転することによって、制御対象の adjoint 特殊化が生成されることを示しています。

既定の本体以外の1つ以上の特殊化を明示的に宣言する必要がある場合は、既定の本体の実装を適切な特殊化宣言にもラップする必要があります。

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>特殊化を有効に定義するための状況

#### <a name="operation-declarations-with-adjointcontrolled"></a>Adjoint/制御された操作の宣言

Adjoint または制御されたバージョンがない操作を指定することはできます。 たとえば、測定操作は、反転できるも制御もされていないため、どちらもありません。

操作は、その `Adjoint` `Controlled` 宣言にそれぞれの特殊化の暗黙的または明示的な宣言が含まれている場合、およびの機能をサポートします。

明示的に宣言された adjoint/制御された特殊化は、adjoint/制御された特殊化が存在することを意味します。 

本文に繰り返しが有効なループ、set ステートメント、測定、return ステートメント、またはファンクタをサポートしない他の操作への呼び出しが含まれている操作については `Adjoint` 、またはディレクティブの後に adjoint の特殊化を自動生成する `invert` `auto` ことはできません。

ファンクタをサポートしていない他の操作への呼び出しが本文に含まれている操作の場合 `Controlled` 、ディレクティブまたはディレクティブの後で制御される特殊化を自動生成する `distribute` `auto` ことはできません。

#### <a name="controlled-adjoint"></a>制御された Adjoint

操作の制御された adjoint バージョンでは、操作の adjoint のクォンタム制御バージョンを実装する方法を指定します。
制御されていない adjoint バージョンを持つ操作を指定することはできます。たとえば、測定操作には制御できない、または反転できるではないため、adjoint バージョンは制御されません。

操作の制御された adjoint 特殊化は、adjoint と制御対象の両方の特殊化が存在する場合にのみ存在する必要があります。 この場合、制御対象の adjoint 特殊化の存在が推論されます。 実装が明示的に定義されていない場合、コンパイルによって適切な特殊化が生成されます。

制御された adjoint バージョンを持たない他の操作への呼び出しが本文に含まれている操作の場合、、、またはディレクティブの後に adjoint 特殊化を自動生成する `invert` `distribute` `auto` ことはできません。


### <a name="type-compatibility"></a>型の互換性

追加のファンクターがサポートされている操作を使用します。これにより、同じシグネチャを持つ、より少数の動作を持つ操作を使用します。 たとえば、 `(Qubit => Unit is Adj)` 型の操作を使用する任意の場所で、型の操作を使用し `(Qubit => Unit)` ます。

Q # は呼び出し可能な戻り値の型に関して*共変*です。型を返す呼び出し可能なは、 `'A` 同じ入力型の呼び出し可能なと、と互換性のある結果型と互換性があります `'A` 。

Q # は入力型に関して*反変*です。入力として型を受け取る呼び出し可能なは、 `'A` 同じ結果型およびと互換性のある入力型の呼び出しと互換性があり `'A` ます。

つまり、次の定義を指定します。

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

できます

- `ConjugateInvertWith`またはの引数を使用して、関数を呼び出し `inner` `Invert` `ApplyUnitary` ます。
- の引数を指定して関数を呼び出し `ConjugateUnitaryWith` `inner` `ApplyUnitary` ますが、は呼び出しません `Invert` 。
- から型の値を `(Qubit[] => Unit is Adj + Ctl)` 返し `ConjugateInvertWith` ます。

> [!IMPORTANT]
> Q # 0.3 では、ユーザー定義型の動作に大きな違いが導入されました。

ユーザー定義型は、サブタイプとしてではなく、基になる型のラップされたバージョンとして扱われます。
これは、基になる型の値がであると予想される場合に、ユーザー定義型の値が使用できないことを意味します。


### <a name="conjugations"></a>活用

従来のビットとは対照的に、qubits を再設定すると、qubits の差が大きくなっても残りの計算には望ましくない影響が生じる可能性があるため、量子メモリの解放は若干複雑になります。 これらの効果は、メモリを解放する前に、実行された計算を適切に "元に戻す" ことで回避できます。 クォンタムコンピューティングの一般的なパターンは次のようになります。 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

0.9 リリース以降、Q # は前の変換を実装する活用形ステートメントをサポートしています。 このステートメントを使用すると、 `ApplyWith` 次のように操作を実装できます。

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
このような活用形ステートメントは、外部および内部の変換を操作として簡単に利用できなくても、複数のステートメントで構成されるブロックで記述する方が便利な場合に、はるかに便利になります。 

内部ブロックで定義されているステートメントの逆変換は、コンパイラによって自動的に生成され、適用ブロックの完了後に実行されます。
内部ブロックの一部として使用される変更可能な変数は、適用ブロックで再バインドできないため、生成された変換は、ブロック内の計算の adjoint であることが保証されます。 


## <a name="defining-new-functions"></a>新しい関数の定義

関数は純粋に決定的で、Q # の従来のルーチンです。これは、の操作とは異なり、出力値を計算しても影響を与えることはできません。
特に、関数は操作を呼び出すことができません。操作を行う、割り当て、または借りる。乱数の例それ以外の場合は、関数に対する入力値を超えた状態に依存します。
その結果、Q # 関数は*純粋*に同じ入力値を同じ出力値にマップすることになります。
この動作により、Q # コンパイラは、操作の特殊化を生成するときに、関数を呼び出す方法とタイミングを安全に並べ替えることができます。

各 Q # ソースファイルでは、任意の数の関数を定義できます。
関数名は名前空間内で一意である必要があり、操作名または型名と競合することはできません。

関数の定義は、操作を定義する場合と同様に機能します。ただし、関数に対して adjoint または制御された特殊化を定義することはできません。
次に例を示します。

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

or 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>関数の古典ロジック = = 良好

これを行うことができる場合は常に、操作ではなく関数の観点から古典ロジックを記述して、操作でより簡単に使用できるようにすると便利です。 たとえば、前の `Square` 宣言を*操作*として記述した場合、コンパイラは、同じ入力でそれを呼び出すことによって同じ出力が一貫して生成されることを保証できませんでした。

関数と演算の違いをアンダースコアにするには、Q # 操作内からランダムな数値をサンプリングするクラシックデプロイの問題について考えてみます。

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

が呼び出されるたびに `U` 、に対して異なるアクションがあり `target` ます。
特に、コンパイラは、特殊化宣言をに追加した場合に `adjoint auto` `U` 、 `U(target); Adjoint U(target);` id として機能する (つまり、非 op として) ことを保証できません。
これは、[ベクターおよびマトリックス](xref:microsoft.quantum.concepts.vectors)で定義されている adjoint の定義に違反しています。これにより、コンパイラは、操作を呼び出したときに、コンパイラによって提供される保証を損なう操作で adjoint 特殊化を自動生成すること <xref:microsoft.quantum.math.randomreal> ができ <xref:microsoft.quantum.math.randomreal> ます。は、adjoint または制御されたバージョンが存在しない操作です。

一方、などの関数呼び出しを許可すると、 `Square` は安全であり、出力を安定した状態に保つためにのみ、入力を保持する必要があることをコンパイラに保証し `Square` ます。
したがって、できるだけ多くの従来のロジックを関数に分離することにより、他の関数や操作でそのロジックを簡単に再利用できるようになります。


## <a name="generic-type-parameterized-callables"></a>ジェネリック (型パラメーター化された) 呼び出しの許容型

定義する関数や操作の多くは、実際に入力の型に依存しているわけではなく、他の関数や演算を使用して暗黙的に型を使用するだけではありません。
たとえば、多くの関数言語に共通する*マップ*の概念を考えてみます。関数 $f (x) $ と値 $ x_1、x_2、\ ドット、x_n $ のコレクションが指定されている場合、 \{ \} map は新しいコレクション $ \{ f (x_1)、f (x_2)、\ ドット、f (x_n) $ を返し \} ます。
これを Q # に実装するには、関数が最初のクラスであるという事実を活用します。
ここでは `Map` 、をプレースホルダーとして使用し、必要な型を確認する方法の簡単な例を示し `T` ます。

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

この関数は、どの実際の型を置き換えるかにかかわらず、非常によく似ていることに注意してください。
たとえば、整数から Paulis へのマップは、浮動小数点数から文字列へのマップとほぼ同じです。

```qsharp
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

原則として、発生する型のペアごとにのバージョンを記述することもでき `Map` ますが、これにはいくつかの問題があります。
たとえば、でバグが見つかった場合は、 `Map` 修正プログラムがすべてのバージョンので一様に適用されていることを確認する必要があり `Map` ます。
さらに、新しい組または UDT を構築する場合は、新しい型と共に新しいを作成する必要もあり `Map` ます。
これは、このような関数の少数の扱いですが、と同じ形式の関数を多数収集すると、 `Map` 新しい型の導入にかかるコストが非常に短い順序で非常になります。

ただし、このような問題の多くは、異なるバージョンのがどのように関連しているかを認識するために必要な情報がコンパイラに与えられていないという事実から得られ `Map` ます。
実際には、コンパイラは `Map` q #*型*から q # 関数に対して何らかの数学的関数として扱う必要があります。

Q # は、関数と操作が*型パラメーター*と、その通常のタプルパラメーターを持つことができるようにすることで、この概念を形式化しています。
前の例では、最初のケースでは型パラメーターを、2番目のケースではと考える必要が `Map` `Int, Pauli` `Double, String` あります。
ほとんどの場合、これらの型パラメーターは通常の型であるかのように使用します。 型パラメーターの値を使用して、配列と組を作成し、関数と演算を呼び出し、通常の変数または変更可能な変数に代入します。

> [!NOTE]
> 間接的な依存関係の最も大きなケースは、qubits の場合です。この場合、Q # プログラムは型の構造に直接依存することはでき `Qubit` ず、そのような型を他の操作や関数に渡す**必要があり**ます。

前の例に戻ると、には型パラメーターが必要であることがわかります。これは、への入力を表し、もう1つは、からの出力を表すための `Map` パラメーターです `fn` `fn` 。
Q # では、 `<>` {} 関数または操作の名前の後に山かっこ (つまり、brakets $ \braket $!) を宣言に追加し、それぞれの型パラメーターを一覧表示することによって記述します。
各型パラメーターの名前は、型パラメーターであり、 `'` 通常の型 (*具象*型とも呼ばれます) ではないことを示すティックで始める必要があります。
したがって、 `Map` は次のように記述されます。

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

の定義は `Map<'Input, 'Output>` 、previoius のバージョンと非常によく似ていることに注意してください。
唯一の違いは、コンパイラは、とに直接依存しないことを明示的に通知しましたが、を `Map` `'Input` 通じて `'Output` 間接的に使用することで、任意の2つの型に対して機能し `fn` ます。
この方法でを定義すると `Map<'Input, 'Output>` 、通常の関数と同じように呼び出すことができます。

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> ジェネリック関数と操作の記述は、"組イン組アウト" が Q # の関数と演算について考える非常に便利な方法である1つの場所です。
> すべての関数は1つの入力を受け取り、ただ1つの出力を返すため、型の入力は `'T -> 'U` どの Q # 関数と*も*一致します。
> 同様に、任意の操作を型の入力に渡すこともでき `'T => 'U` ます。

2番目の例として、次の2つの関数の合成を返す関数を記述するという課題を考えてみます。

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

ここでは、、、およびを正確に指定する必要がある `A` `B` ため、 `C` 新しい関数のユーティリティが著しく制限され `Compose` ます。
結局のところ、は、、、 `Compose` およびを介してのみ依存し `A` `B` `C` *via* `innerFn` `outerFn` ます。
別の方法として、型パラメーターをに追加して `Compose` 、*任意*の、、およびに対して動作することを示すことができます `A` 。これらのパラメーターは、 `B` `C` とで想定されているものと一致している必要が `innerFn` `outerFn` あります。

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q # 標準ライブラリは、このような種類のパラメーター化された操作と関数の範囲を提供して、上位の制御フローを簡単に表現できるようにします。
これらの詳細については、「 [Q # 標準ライブラリ」ガイド](xref:microsoft.quantum.libraries.standard.intro)を参照してください。


## <a name="callables-as-first-class-values"></a>Callables ファーストクラスの値として指定される

制御フローと従来のロジックについては、操作ではなく関数を使用するという1つの重要な手法として、Q # の操作と関数を*ファーストクラス*で利用することが挙げられます。
つまり、言語の各値が独自の権限であるということです。
たとえば、次のコードは完全に有効な Q # コードです (少し間接的な場合)。

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

前のスニペットの変数の値 `ourH` は操作 <xref:microsoft.quantum.intrinsic.h> であり、他の操作と同様にその値を呼び出すことができます。
この機能を使用すると、入力の一部として操作を実行し、上位の制御フローの概念を形成する操作を記述できます。
たとえば、同じターゲット qubit に2回適用して、操作を "正方形" にすることを考えてみます。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>関数からの操作の返却

出力の一部として操作を返すこともできることを強調することが重要です。これは、ある種のクラシック条件ロジックを、操作の形式でクォンタムプログラムの記述を返す、古典的な関数として分離できるようにするためです。
簡単な例として、2ビットの古典的なメッセージを受信するパーティがメッセージを使用して、qubit を適切なテレポートの状態にデコードする必要がある場合の例を考えてみます。
これは、これらの2つの古典ビットを受け取り、適切なデコード操作を返す関数の観点から記述できます。

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

この新しい関数は実際には関数です。では、との同じ値を使用して呼び出すと `hereBit` `thereBit` 、常に同じ操作が返されます。
したがって、デコーダーは、デコードロジックがさまざまな操作の特殊化の定義とどのようにやり取りするかを気にせずに、操作内で安全に実行できます。
つまり、関数内の古典的なロジックは分離され、入力が保持されている限り、関数呼び出しを impunity で並べ替えることができることをコンパイラに保証します。


## <a name="partial-application"></a>部分アプリケーション

*部分的なアプリケーション*を使用して操作を返す関数では、関数を実際に呼び出すことなく、関数または演算に入力の1つ以上の部分を指定することにより、さらに多くのことを行うことができます。 前の `ApplyTwice` 例では、入力操作を適用する必要がある qubit を指定することができます。

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

この場合、ローカル変数は `twiceOp` 部分的に適用される操作を保持します。ここで、は、 `ApplyTwice(op, _)` まだ指定され `_` ていない入力部分を示します。
次の行でを呼び出す場合は、 `twiceOp` 部分的に適用される操作に入力として、入力の残りの部分すべてを元の操作に渡します。
したがって、前のスニペットは、実際にはを直接呼び出すのと同じです `ApplyTwice(op, target)` 。新しいローカル変数を導入したので、入力の一部を提供しながら、呼び出しを遅延させることができます。

部分的に適用された操作は、入力全体が提供されるまでは実際には呼び出されないため、関数内からも部分的に操作を部分的に適用できます。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

原則として、内の従来のロジックははるかに複雑になる `SquareOperation` 可能性がありますが、コンパイラが関数に関して提供できる保証によって、操作の残りの部分から分離されています。 Q # 標準ライブラリでは、この方法を通じて、量子プログラムが簡単に使用できるように、従来の制御フローを表現します。


## <a name="recursion"></a>再帰

Q # callables は、直接的または間接的に再帰的に許可されています。
つまり、操作または関数はそれ自体を呼び出すことができます。また、呼び出し可能な操作を直接または間接的に呼び出す別の呼び出し元を呼び出すこともできます。

ただし、再帰の使用に関しては、次の2つの重要なコメントがあります。

- 操作で再帰を使用すると、特定の最適化が妨げられる可能性があります。
  この干渉は、アルゴリズムの実行時間に大きな影響を与える可能性があります。
- 実際のクォンタムデバイスで実行されている場合、スタック領域が制限される可能性があるため、詳細な再帰によって実行時エラーが発生する可能性があります。
  特に、Q # コンパイラとランタイムは、末尾の再帰を識別して最適化しません。

## <a name="next-steps"></a>次の手順

Q # の[変数](xref:microsoft.quantum.guide.variables)について説明します。