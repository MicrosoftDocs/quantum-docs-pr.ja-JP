---
title: 'Q # ファイル構造'
description: '名前空間、操作、関数、およびユーザー定義型の宣言を Q # のプログラムとライブラリで構造化する方法について説明します。'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320765"
---
# <a name="file-structure"></a>ファイル構造

Q # ファイルは、一連の名前空間宣言で構成されます。
各名前空間の宣言には、ユーザー定義型、操作、および関数の宣言が含まれています。
名前空間宣言には、任意の数の宣言を任意の順序で含めることができます。
名前空間の宣言の外側に表示されるテキストは、コメントだけです。
特に、名前空間のドキュメントコメントは、宣言の前に記述します。

## <a name="namespace-declarations"></a>名前空間の宣言

Q # ファイルには、通常、名前空間宣言が1つだけ含まれますが、(空またはコメントを含む) は使用できません。また、複数の名前空間を含めることもできます。
名前空間宣言を入れ子にすることはできません。

同じ名前の型、操作、または関数の宣言がない限り、同じ名前空間を複数の Q # ファイルで宣言することができます。
特に、宣言が同一であっても、複数のファイルの同じ名前空間で同じ型を定義することは無効です。

名前空間宣言は、キーワード `namespace`、名前空間の名前、始めかっこ `{`、名前空間に含まれる宣言、および終わりかっこ `}`で構成されます。
名前空間名は、`.`ピリオドで区切られた1つまたは複数の有効な記号のシーケンスの .NET パターンに従います。
たとえば、`MyQuantumStuff` と `Microsoft.Quantum.Canon` は有効な名前空間名です。
慣例により、名前空間名に含まれる記号は大文字になりますが、これは必須ではありません。

宣言は、名前空間の宣言内で任意の順序で記述できます。
ファイル内でさらに下に宣言されている型または呼び出し方向への参照は、適切に解決されます。型、操作、または関数の宣言を参照の前に記述する必要はありません。

## <a name="open-directives"></a>オープンディレクティブ

名前空間ブロック内では、`open` ディレクティブを使用して、特定の名前空間で定義されているすべての型と呼び出し可能な型をインポートし、非修飾名で参照することができます。 

このような `open` ディレクティブは、`open` キーワードで構成され、その後に、名前空間が開かれ、セミコロンが終了します。

たとえば、

```qsharp
open Microsoft.Quantum.Canon;
```

必要に応じて、名前空間のすべての要素が定義された短い名前によって修飾されるように、開いている名前空間の短い名前を定義することもできます。 この短い名前は、キーワード `as` の後に、必要な短い名前をセミコロンの前に `open` ディレクティブで追加することによって定義されます。

```qsharp
open Microsoft.Quantum.Math as Math;
```

すべての `open` ディレクティブは、namespace ブロック内の `function`、`operation`、または `newtype` 宣言の前に記述する必要があります。
`open` ディレクティブは、ファイル内の名前空間ブロック全体に適用されます。

## <a name="user-defined-type-declarations"></a>ユーザー定義型の宣言

Q # は、ユーザーが新しいユーザー定義型を宣言する方法を提供します。詳細については、「 [q # type model](xref:microsoft.quantum.language.type-model) 」セクションを参照してください。
基本型が同一の場合でも、ユーザー定義型は区別されます。
特に、基になる型が同一であっても、2つのユーザー定義型の値を自動的に変換することはできません。

ユーザー定義型の宣言は、キーワード `newtype`で構成され、その後にユーザー定義型の名前、`=`、有効な型指定、および終端のセミコロンが続きます。

次に例を示します。

```qsharp
newtype PairOfInts = (Int, Int);
```

各 Q # ソースファイルは、任意の数のユーザー定義型を宣言できます。
型名は名前空間内で一意である必要があり、操作名および関数名と競合しない可能性があります。

ユーザー定義型の間に循環依存関係を定義することはできません。 このため、Q # では再帰型を使用できません。

## <a name="operation-declarations"></a>操作の宣言

操作は Q # の中核であり、他の言語の関数とほぼ同じです。
各 Q # ソースファイルでは、任意の数の操作を定義できます。

操作名は名前空間内で一意である必要があり、型および関数名と競合しない可能性があります。

操作の宣言は、キーワード `operation`、その後に操作の名前であるシンボル、操作の引数を定義する型指定された識別子のタプル、コロン `:`、操作の結果の型を記述する型の注釈、オプションで、操作の特性、始めかっこ `{`、操作宣言の本体、および最後の右中かっこ `}`で構成されます。

操作宣言の本体は、既定の実装または特殊化のリストのいずれかで構成されます。
既定の本体の特殊化の実装のみを明示的に指定する必要がある場合は、既定の実装を宣言内で直接指定できます。
この場合、宣言の操作特性を持つ注釈を使用すると、コンパイラが既定の実装に基づいて他の特殊化を自動生成するのに役立ちます。 

次に例を示します。 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

操作特性は、宣言された操作に適用できる機能の種類と、その効果を定義します。 操作で、 *adjointed*または*制御*されている場合の操作の動作を定義できます。
これらの特殊化の存在は、操作シグネチャの一部として宣言できます。 そのような暗黙的に宣言された各特殊化の対応する実装が、コンパイラによって生成されます。 上の例では、adjoint、制御された、および制御された adjoint 特殊化がコンパイラによって生成されます。 

実装がコンパイラによって生成されない場合は、明示的に指定できます。 このような明示的な特殊化宣言は、特定の特殊化を構築する方法を明確にする適切なジェネレーションディレクティブ、またはユーザー定義の実装で構成できます。 たとえば、上記の `PrepareEntangledPair` のコードは、明示的な特殊化宣言を含む次のコードと同じです。 

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
より正確な生成ディレクティブではなく、特定の特殊化の実装をコンパイラが生成できない場合、またはより効率的な実装を指定できる場合は、実装を手動で定義することもできます。

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

`Adjoint` または `Controlled` ファンクタのアプリケーションをサポートする操作の場合、その戻り値の型を必ず `Unit`する必要があります。 


### <a name="explicit-specialization-declarations"></a>明示的特殊化の宣言

Q # 操作には、次の明示的特殊化宣言を含めることができます。

- `body` 特殊化は、動作が適用されていない操作の実装を指定します。
- `adjoint` 特殊化は、`Adjoint` のファンクタが適用された操作の実装を指定します。
- `controlled` 特殊化は、`Controlled` のファンクタが適用された操作の実装を指定します。
- `controlled adjoint` 特殊化は、`Adjoint` と `Controlled` の両方のファンクターが適用された操作の実装を指定します。
  この特殊化は、2つの commute があるため、`adjoint controlled`という名前にすることもできます。


操作の特殊化は、特殊化タグ (例: `body`、`adjoint`など) で構成され、その後に次のいずれかが続きます。

- 明示的な宣言。以下に説明します。
- 特殊化を生成する方法をコンパイラに指示するディレクティブ。次のいずれかになります。
  - `intrinsic`。ターゲットコンピューターによって特殊化が提供されることを示します。
  - `distribute`。 `controlled` および `controlled adjoint` の特殊化と共に使用できます。
    `controlled`と共に使用すると、コンパイラは `body`内のすべての操作に `Controlled` を適用することによって、特殊化を計算する必要があることを示します。
    `controlled adjoint`と共に使用する場合、`adjoint` 特殊化のすべての操作に `Controlled` を適用することによって、コンパイラが特殊化を計算する必要があることを示します。
  - `invert`は、コンパイラが `body`を反転させることによって `adjoint` 特殊化を計算する必要があることを示します。つまり、操作の順序を逆にして、それぞれに adjoint を適用します。
    `adjoint controlled`と共に使用すると、コンパイラは特殊化 `controlled` を反転させることにより、特殊化を計算する必要があることを示します。
  - `self`、adjoint の特殊化が `body` 特殊化と同じであることを示します。
    これは、`adjoint` と `adjoint controlled` 特殊化に対して有効です。
    `adjoint controlled`の場合、`self` は `adjoint controlled` 特殊化が `controlled` 特殊化と同じであることを意味します。
  - `auto`、コンパイラが適切なディレクティブを選択して適用する必要があることを示します。
    `auto` は、`body` 特殊化には使用できません。

ディレクティブと `auto` すべてには、末尾にセミコロン `;`を付ける必要があります。
`body` の明示的な宣言が指定されている場合、`auto` ディレクティブは次のジェネレーションディレクティブに解決されます。

- `adjoint` 特殊化は、ディレクティブ `invert`に基づいて生成されます。
- `controlled` 特殊化は、ディレクティブ `distribute`に基づいて生成されます。
- `controlled` の明示的な宣言が指定されていても `adjoint`にはない場合は、ディレクティブ `invert` に従って `adjoint controlled` 特殊化が生成され、それ以外の場合は `distribute` ます。

> [!TIP]   
> 操作が自己 adjoint の場合、コンパイラが最適化のためにその情報を使用できるようにするには、明示的に adjoint または制御されている adjoint の特殊化を生成ディレクティブ `self` 経由で指定します。

ユーザー定義の実装を含む特殊化宣言は、引数の組の後に、特殊化を実装する Q # コードを持つステートメントブロックで構成されます。
引数リストでは、`...` を使用して、操作全体に対して宣言された引数を表します。
`body` と `adjoint`では、引数リストは常に `(...)`である必要があります。`controlled` と `adjoint controlled`の場合、引数リストは、コントロールの qubits の配列を表すシンボルで、その後にかっこで囲まれた `...`が続く必要があります。たとえば、`(controls,...)`のようにします。

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

### <a name="adjoint"></a>Adjoint

操作の adjoint は、操作の複雑な共役の置換を実装する方法を指定します。つまり、"逆順で実行する" 操作がどのように動作するかを指定します。
Adjoint なしで操作を指定することはできます。たとえば、測定操作は反転できるではないため、adjoint を持ちません。
操作は、宣言に adjoint 特殊化の暗黙的または明示的な宣言が含まれている場合、`Adjoint` のファンクタをサポートします。
明示的に宣言された制御済み adjoint 特殊化は、adjoint の特殊化が存在することを意味します。 

操作に対して、繰り返しのループ、set ステートメント、測定、return ステートメント、または `Adjoint` ファンクタをサポートしていないその他の操作への呼び出しが含まれている操作の場合、`invert` または `auto` ディレクティブの後に adjoint の特殊化を自動生成することはできません。

### <a name="controlled"></a>た

操作の制御されたバージョンは、クォンタムによって制御されるバージョンの操作を実装する方法を指定します。つまり、クォンタムレジスタの状態に対して条件を適用した場合、操作がどのように動作するかを指定します。
詳細な説明については、「[制御](xref:microsoft.quantum.language.type-model#controlled)」セクションを参照してください。

制御されていないバージョンの操作を指定することはできます。たとえば、測定操作は制御できないので、制御されたバージョンではありません。
操作は、制御された特殊化の暗黙的または明示的な宣言が宣言に含まれている場合にのみ、`Controlled` ファンクタをサポートします。
明示的に宣言された制御済み adjoint 特殊化は、制御された特殊化が存在することを意味します。 

`Controlled` ファンクタをサポートしていないその他の操作への呼び出しが本文に含まれている操作の場合、`distribute` または `auto` ディレクティブの後に制御される特殊化を自動生成することはできません。

### <a name="controlled-adjoint"></a>制御された Adjoint

操作の制御された adjoint バージョンは、操作のクォンタム制御バージョンを実装する方法を指定します。
制御されていない adjoint バージョンを持つ操作を指定することはできます。たとえば、測定操作には制御できない、または反転できるではないため、adjoint バージョンは制御されません。

操作の制御された adjoint 特殊化は、adjoint と制御対象の両方の特殊化が存在する場合にのみ存在する必要があります。 この場合、制御された adjoint 特殊化の存在が推論され、明示的に定義された実装がない場合は、コンパイラによって適切な特殊化が生成されます。 

制御された adjoint バージョンを持たない他の操作への呼び出しが本文に含まれている操作の場合、`distribute` または `auto` ディレクティブに `invert`続く adjoint の特殊化を自動生成することはできません。


### <a name="examples"></a>例

操作の宣言は、次のように単純なものにすることができます。これにより、プリミティブな P# li X 操作が定義されます。

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

次の例では、テレポート操作を定義しています。

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>関数の宣言

関数は、Q # の純粋な古典ルーチンです。
各 Q # ソースファイルでは、任意の数の関数を定義できます。

関数宣言は、キーワード `function`、その後に関数の名前、型指定された識別子の組、関数の戻り値の型を記述する型の注釈、および関数の実装を記述するステートメントブロックで構成されます。

関数を定義するステートメントブロックは `{` で囲み、他のステートメントブロックと同様に `}` する必要があります。

関数名は名前空間内で一意である必要があり、操作と型名と競合しない可能性があります。
関数は、qubits の割り当てや借用、操作の呼び出しを行うことはできません。 操作を部分的に適用するか、操作の型指定された値をラップすることは問題ありません。

たとえば、次のように入力します。

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


## <a name="internal-declarations"></a>内部宣言

ユーザー定義型、操作、および関数を*内部*として宣言することもできます。
これは、宣言されている Q # プロジェクト内からのみアクセスできることを意味します。
プロジェクトが参照として使用されている場合、そのすべての*パブリック*(内部ではない) 宣言は使用できるようになりますが、別のプロジェクトから内部宣言を使用しようとするとエラーが発生します。
内部宣言は、プロジェクトの他の部分で再利用できるモジュールコードを記述する場合に役立ちますが、後で変更しても、依存する他のプロジェクトには影響しません。

内部ユーザー定義型、操作、または関数は、宣言の先頭に `internal` を追加するだけで宣言できます。
たとえば、次のように入力します。

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> 内部ユーザー定義型は、対応する呼び出し元またはユーザー定義型も内部である場合にのみ、シグネチャまたは基になる型で使用できます。
> たとえば、`internal` キーワードで宣言されたユーザー定義型 `InternalOptions` がある場合、次の宣言によってエラーが発生します。
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```
