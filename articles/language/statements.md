---
title: 'Q # ステートメント |Microsoft Docs'
description: 'Q # ステートメント'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9a6f5d53ec21090d0c13f4369e0270d264cd1e9b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036493"
---
# <a name="statements-and-other-constructs"></a>ステートメントとその他の構成体

## <a name="comments"></a>コメント

コメントは、2つのスラッシュ (`//`) で始まり、行の終わりまで続きます。
Q # ソースファイル内の任意の場所にコメントが表示される場合があります。

### <a name="documentation-comments"></a>ドキュメントのコメント

3つのスラッシュ (`///`) で始まるコメントは、名前空間、操作、特殊化、関数、または型定義の直前に出現するときに、コンパイラによって特別に処理されます。
その場合、その内容は、他の .NET 言語と同様に、定義された呼び出し可能またはユーザー定義型のドキュメントとして取得されます。

`///` コメントでは、API ドキュメントの一部として表示されるテキストは[Markdown](https://daringfireball.net/projects/markdown/syntax)として書式設定され、ドキュメントのさまざまな部分が特別な名前のヘッダーによって示されています。
Markdown の拡張機能として、Q # の操作、関数、ユーザー定義型への相互参照は、`@"<ref target>"`を使用して含めることができます。 `<ref target>` は参照されるコードオブジェクトの完全修飾名に置き換えられます。
必要に応じて、ドキュメントエンジンで追加の Markdown 拡張機能をサポートすることもできます。

例 :

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

次の名前は、ドキュメントのコメントヘッダーとして認識されます。

- **Summary**: 関数または操作の動作、または型の目的の簡単な概要。 概要の最初の段落は、ホバー情報に使用されます。 プレーンテキストである必要があります。
- **説明**: 関数または操作の動作、または型の目的の説明。 概要と説明を連結して、関数、操作、または型の生成されたドキュメントファイルを作成します。
  説明には、インラインの LaTeX 形式のシンボルと式を含めることができます。
- **入力**: 操作または関数の入力タプルの説明。
  入力タプルの各要素を示す追加の Markdown サブセクションを含めることができます。
- **出力**: 演算または関数によって返される組の説明。
- **型パラメーター**: ジェネリック型パラメーターごとに1つの追加のサブセクションを含む空のセクション。
- **例**: 使用されている操作、関数、または型の簡単な例。
- **解説**: 操作、関数、または型のいくつかの側面を説明するその他の prose。
- 関連する関数、操作、またはユーザー定義型を示す完全修飾名の一覧**も参照してください**。
- **参照**: ドキュメント化されている項目の参照および引用の一覧。

## <a name="namespaces"></a>名前空間

すべての Q # 操作、関数、およびユーザー定義型は、名前空間内で定義されます。
Q # は、他の .NET 言語として名前を付ける場合と同じ規則に従います。
ただし、Q # では名前空間への相対参照はサポートされません。
つまり、名前空間 `a.b` が開かれている場合、操作名への参照 `c.d` は、完全な名前 `a.b.c.d`を持つ操作に解決されません。

名前空間ブロック内では、`open` ディレクティブを使用して、特定の名前空間で宣言されたすべての型と呼び出し可能な型をインポートし、非修飾名で参照することができます。 必要に応じて、名前空間のすべての要素が定義された短い名前によって修飾されるように、開いている名前空間の短い名前を定義することもできます。 `open` ディレクティブは、ファイル内の名前空間ブロック全体に適用されます。

現在の名前空間で開かれていない別の名前空間で定義されている型または呼び出し可能が、完全修飾名で参照されている必要があります。
たとえば、現在のブロックで `X.Y` 名前空間が開かれていない限り、`X.Y` 名前空間の `Op` という名前の操作は、完全修飾名 `X.Y.Op`によって参照される必要があります。 前述のように、`X` 名前空間が開かれていても、`Y.Op`として操作を参照することはできません。
名前空間とファイルで `X.Y` の短い名前 `Z` が定義されている場合は、`Op` を `Z.Op`として参照する必要があります。 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

通常は、`open` ディレクティブを使用して名前空間を含めることをお勧めします。
2つの名前空間で同じ名前の構造体を定義し、現在のソースが両方のコンストラクトを使用する場合は、完全修飾名を使用する必要があります。

## <a name="formatting"></a>書式設定

ほとんどの Q # ステートメントおよびディレクティブは、終端のセミコロンで終わります `;`。
ステートメントブロックで終わる `for` や `operation` などのステートメントと宣言には、終端のセミコロンは必要ありません。
各ステートメントの説明には、終端のセミコロンが必要かどうかが示されます。

ステートメント (式、宣言、ディレクティブなど) は、複数の行にわたって分割される場合があります。
1行に複数のステートメントを記述することは避けてください。

## <a name="statement-blocks"></a>ステートメントブロック

Q # ステートメントは、ステートメントブロックにグループ化されます。
ステートメントブロックが開始 `{` で始まり、終了 `}`で終わります。

別のブロック内で構文的に囲まれたステートメントブロックは、それを含むブロックのサブブロックと見なされます。コンテナーとサブブロックは、外部ブロックと内部ブロックとも呼ばれます。

## <a name="symbol-binding-and-assignment"></a>シンボルのバインドと代入

Q # は、変更可能なシンボルと変更できないシンボルを区別します。
一般に、変更できないシンボルを使用することをお勧めします。これにより、コンパイラはより多くの最適化を実行できるためです。

バインディングの左側は、記号の組と式の右辺で構成されています。

すべての Q # 型は値型であるため、qubits が多少特別なロールを使用すると、値がシンボルにバインドされたとき、またはシンボルが再バインドされるときに "コピー" が作成されます。 つまり、Q # の動作は、割り当て時にコピーが作成された場合と同じです。 これには、配列も含まれます。 もちろん、実際には、関連する部分のみが必要に応じて再作成されます。 

### <a name="tuple-deconstruction"></a>タプル分解

バインドの右側がタプルの場合、そのタプルは代入時に分解される可能性があります。
このような deconstructions には、入れ子になった組が含まれる場合があります。また、右辺の組の構造がシンボルの組の形状と互換性がある限り、完全または部分的な分解は有効です。
分解 `=` の右辺がタプル値式の場合にも、タプルを使用できます。

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>変更できないシンボル

変更できないシンボルは、`let` ステートメントを使用してバインドされます。
これは、などC#の言語での変数宣言および初期化とほぼ同じですが、Q # 記号はバインドされると変更されない可能性がある点が異なります。`let` バインドは変更できません。

変更できないバインドは、キーワード `let`、その後にシンボルまたは記号の組、等号 `=`、記号をバインドする式、および終端のセミコロンで構成されます。
バインドされたシンボルの型は、右側の式に基づいて推論されます。

### <a name="mutable-symbols"></a>変更可能なシンボル

変更可能なシンボルは、`mutable` ステートメントを使用して定義および初期化します。
`mutable` ステートメントの一部として宣言およびバインドされたシンボルは、コードの後半で別の値に再バインドされる可能性があります。 

変更可能なバインドステートメントは、キーワード `mutable`、その後にシンボルまたは記号の組、等号 `=`、記号をバインドする式、および終端のセミコロンで構成されます。
バインドされたシンボルの型は、右側の式に基づいて推論されます。 シンボルが後でコード内で再バインドされる場合、その型は変更されず、バインドされた値はその型と互換性がある必要があります。

### <a name="rebinding-of-mutable-symbols"></a>再バインド (変更可能なシンボルの)

変更可能な変数は、`set` ステートメントを使用して再バインドすることができます。
このような再バインドは、キーワード `set`、その後にシンボルまたは記号の組、等号 `=`、等号を再バインドする式、および終端のセミコロンで構成されます。
値は、バインド先のシンボルの型と互換性がある必要があります。

#### <a name="apply-and-reassign-statement"></a>Apply ステートメントと再割り当てステートメント

特定の種類のセットステートメントは、適用と再割り当てのステートメントとして参照します。右辺が二項演算子のアプリケーションで構成され、結果が演算子の左辺の引数に再バインドされる場合、連結の便利な方法となります。 たとえば、次のように入力します。
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
`for` ループの各反復処理でカウンター `counter` の値をインクリメントします。 上記のコードは、 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
左辺の型が式の型と一致するすべての二項演算子に対して、同様のステートメントを使用できます。 これにより、たとえば、値を累積する便利な方法が提供されます。
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Update および-再割り当てステートメント

右側にコピーと更新の式がある場合も同様の連結が存在します。 それに応じて、ユーザー定義型および配列項目の名前付き項目に対して、更新と再割り当てのステートメントが存在します。  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

配列の場合、標準ライブラリには、多くの一般的な配列の初期化と操作に必要なツールが含まれているため、最初の場所で配列項目を更新する必要がなくなります。 必要に応じて、更新ステートメントと再割り当てステートメントで代替手段を提供します。

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <xref:microsoft.quantum.arrays>に用意されているツールを利用して、更新と再割り当てのステートメントを不要に使用しないようにします。

関数
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
たとえば、`Microsoft.Quantum.Arrays`の関数 `ConstantArray` を使用して単純化し、コピーと更新の式を返すことができます。

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>スコープのバインド

一般に、シンボルバインドはスコープ外に出、ステートメントブロックの最後では動作しなくなります。
このルールには次の 2 つの例外があります。

- `for` ループのループ変数のバインドは、for ループの本体のスコープ内にありますが、ループの終了後には適用されません。
- `repeat`/`until` ループ (本文、テスト、および修正) の3つの部分はすべて1つのスコープとして扱われるので、本文にバインドされているシンボルはテストとフィックスアップで使用できます。

両方の種類のループでは、ループの各パスが独自のスコープ内で実行されるため、以前のパスからのバインドは、後のパスでは使用できません。

外部ブロックからのシンボルバインディングは、内部ブロックによって継承されます。
シンボルをバインドできるのは、ブロックごとに1回だけです。スコープ内にある別のシンボルと同じ名前のシンボルを定義することはできません ("シャドウ" はありません)。
有効なシーケンスは次のとおりです。

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

and

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

ただし、これは無効になります。

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

次のようになります。

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>制御フロー

### <a name="for-loop"></a>For ループ

`for` ステートメントは、整数範囲または配列に対する反復処理をサポートしています。
ステートメントは、キーワード `for`、始めかっこ `(`、シンボルまたは記号の組、キーワード `in`、`Range` または配列型の式、終わりかっこ `)`、およびステートメントブロックで構成されます。

ステートメントブロック (ループの本体) は、範囲または配列の各値にバインドされたシンボル (ループ変数) を使用して繰り返し実行されます。
範囲式が空の範囲または配列に評価される場合、本文はまったく実行されないことに注意してください。
式はループに入る前に完全に評価され、ループの実行中は変更されません。

宣言されたシンボルのバインドは不変であり、他の変数バインドと同じ規則に従います。 特に、ループ変数への代入時に配列に対する反復処理の配列項目などを破棄することができます。

たとえば、次のように入力します。

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

ループ変数は、ループ本体の各入口でバインドされ、本文の最後にバインド解除されます。
特に、ループ変数は for ループの完了後にバインドされません。

### <a name="repeat-until-success-loop"></a>繰り返し-成功ループ

`repeat` ステートメントでは、"成功までの繰り返し" パターンがサポートされています。
これは、キーワード `repeat`、ステートメントブロック (_ループ_本体)、キーワード `until`、ブール式、終了セミコロンまたはキーワード `fixup` の後に別のステートメントブロック ( _fixup_) が続きます。
ループ本体、条件、および修正はすべて1つのスコープであると見なされるため、本文にバインドされているシンボルは、条件と修正に使用できます。

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

ループの本体が実行され、条件が評価されます。
条件が true の場合、ステートメントは完了します。それ以外の場合は、fixup が実行され、ループ本体からステートメントが再実行されます。
修正の実行を完了すると、ステートメントのスコープが終了します。これにより、本体またはフィックスアップ中に作成されたシンボルバインドは、後続の繰り返しでは使用できなくなります。

たとえば、次のコードは、Hadamard と T ゲートを使用して、重要な回転ゲート $V (& 3)、(確率論的 + 2 i Z)/\ sqrt{5}$ を実装する、中心となる回路です。
ループは $-frac{8}で終了し、平均で $ 繰り返し {5}ます。
詳細については、「繰り返し-成功するまで」を参照してください。 [*1 つの qubit unitaries 非決定的分解*](https://arxiv.org/abs/1311.1074)(paetznick と svore 2014) を参照してください。

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

> [!TIP]   
> 関数内での繰り返しの成功ループの使用は避けてください。 対応する機能は、関数の while ループによって提供されます。 

### <a name="while-loop"></a>While ループ

繰り返し-成功パターンには、クォンタム固有の connotation があります。 これらは、特定のクラスのクォンタムアルゴリズムで広く使用されているため、Q # の専用言語構成要素です。 ただし、条件に基づいて中断されるループでは、実行の長さがコンパイル時に不明であるため、クォンタムランタイムでは特に注意して処理する必要があります。 一方、関数内での使用は、従来の (非クォンタム) ハードウェアで実行されるコードのみを含むため、問題はありません。 

そのため、Q # では、関数内でのみ while ループを使用できます。 `while` ステートメントは、キーワード `while`、開いているかっこ `(`、条件 (ブール式)、終わりかっこ `)`、およびステートメントブロックで構成されます。
ステートメントブロック (ループの本体) は、条件が `true`に評価される限り実行されます。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>条件付きステートメント

`if` ステートメントでは、条件付き実行がサポートされています。
これは、キーワード `if`、始めかっこ `(`、ブール式、終わりかっこ `)`、およびステートメントブロック ( _then_ブロック) で構成されます。
その後には、任意の数の else if 句を指定できます。これらは、それぞれキーワード `elif`、始めかっこ `(`、ブール式、終わりかっこ `)`、およびステートメントブロック ( _else_ブロック) で構成されます。
最後に、ステートメントは、キーワード `else` の後に別のステートメントブロック ( _else_ブロック) が続く else 句を使用して終了することもできます。
条件が評価され、true の場合は then ブロックが実行されます。
条件が false の場合、最初の else if 条件が評価されます。true の場合は、それ以外の場合は if ブロックが実行されます。
それ以外の場合は、2番目の else-if ブロックがテストされ、3番目以降の場合は、true 条件を持つ句が検出されるか、それ以上の else if 句が存在しなくなるまで続きます。
元の if 条件とすべての else-if 句が false と評価された場合、else ブロックが指定されていると、else ブロックが実行されます。

実行されるブロックはいずれも、それ自体のスコープ内で実行されることに注意してください。
Then、else、または else ブロック内で行われたバインディングは、if ステートメントの終了後には参照できません。

たとえば、次のように入力します。

```qsharp
if (result == One) {
    X(target);
} 
```

or

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>戻り値

Return ステートメントは、操作または関数の実行を終了し、呼び出し元に値を返します。
これは、キーワード `return`、適切な型の式、および終端のセミコロンで構成されます。

空のタプルを返す呼び出し可能 `()`には、return ステートメントは必要ありません。
早期終了が必要な場合は、この場合に `return ()` を使用できます。
他の型を返す呼び出しを行うには、最終的な return ステートメントが必要です。

操作内に return ステートメントの最大数がありません。
ステートメントがブロック内の return ステートメントに続く場合、コンパイラは警告を生成することがあります。

たとえば、次のように入力します。

```qsharp
return 1;
```

or

```qsharp
return ();
```

or

```qsharp
return (results, qubits);
```

### <a name="fail"></a>失敗

Fail ステートメントは、操作の実行を終了し、呼び出し元にエラー値を返します。
これは、キーワード `fail`と、その後に続く文字列と終端のセミコロンで構成されます。
文字列は、エラーメッセージとしてクラシックドライバーに返されます。

操作内の fail ステートメントの数に制限はありません。
ステートメントがブロック内の fail ステートメントに続く場合、コンパイラは警告を生成することがあります。

たとえば、次のように入力します。

```qsharp
fail $"Impossible state reached";
```

or

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Qubit 管理

関数の本体内では、これらのステートメントを使用できないことに注意してください。
これらは、操作内でのみ有効です。

### <a name="clean-qubits"></a>Clean Qubits

`using` ステートメントは、ステートメントブロック中に使用する新しい qubits を取得するために使用されます。
Qubits は、計算 `Zero` 状態に初期化されることが保証されます。
Qubits は、ステートメントブロックの最後にある計算 `Zero` 状態である必要があります。シミュレーターでは、これを強制することをお勧めします。

このステートメントは、キーワード `using`で構成され、始めかっこ `(`、バインド、終わりかっこ `)`、および qubits が使用可能になるステートメントブロックで構成されます。
バインディングは、`let` ステートメントと同じパターンに従います。1つのシンボルまたはシンボルのタプルの後に等号 `=`、1つの値、または初期化子の一致するタプルのいずれかを指定します。
初期化子は、1つの qubit、`Qubit()`として示されるか、`Qubit[`、`Int` 式、および `]`によって示される qubit の配列で使用できます。

たとえば、次のように入力します。

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>借りた Qubits

`borrowing` ステートメントは、一時的な使用のために qubits を取得するために使用されます。 このステートメントは、キーワード `borrowing`で構成され、始めかっこ `(`、バインド、終わりかっこ `)`、および qubits が使用可能になるステートメントブロックで構成されます。
バインディングは、`using` ステートメントと同じパターンおよび規則に従います。

たとえば、次のように入力します。

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

借用した qubits は不明な状態であり、ステートメントブロックの最後でスコープ外に出ます。
借り手は、貸し出しされたときと同じ状態に qubits を残すことをコミットします。つまり、ステートメントブロックの先頭と末尾の状態は同じであると想定されます。
特に、この状態は必ずしも古典的な状態ではありません。ほとんどの場合、借りているスコープには測定値を含めないでください。 

借り qubits の使用例については、「 [*2n + 2 qubits と Toffoli ベースのモジュール乗算 2017 (ベースのモジュール型乗算) を使用したファクタリング*](https://arxiv.org/abs/1611.07995)」を参照してください。

Qubits を借りている場合、システムはまず、使用中であるが、`borrowing` ステートメントの本体ではアクセスされない qubits から要求を入力しようとします。
このような qubits が不足している場合は、要求を完了するために新しい qubits が割り当てられます。

## <a name="conjugations"></a>活用

従来のビットとは対照的に、qubits を再設定すると、qubits の差が大きくなっても残りの計算には望ましくない影響が生じる可能性があるため、量子メモリの解放は若干複雑になります。 これは、メモリを解放する前に、実行された計算を適切に "元に戻す" ことで回避できます。 クォンタムコンピューティングの一般的なパターンは次のようになります。 

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

: 新規: 0.9 リリース以降では、上記の変換を実装する活用形ステートメントがサポートされています。 このステートメントを使用すると、次のように操作 `ApplyWith` を実装できます。

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
このような活用形ステートメントは、外部と内部の変換を操作として簡単に利用できず、複数のステートメントで構成されるブロックで記述する方が便利な場合に、はるかに便利になります。 

内部ブロックで定義されたステートメントの逆変換は、コンパイラによって自動的に生成され、適用ブロックの完了後に実行されます。 内部ブロックの一部として使用される変更可能な変数は、適用ブロックで再バインドできないため、生成された変換は、ブロック内の計算の adjoint であることが保証されます。 

## <a name="expression-evaluation-statements"></a>式の評価ステートメント

`Unit` 型の任意の呼び出し式は、ステートメントとして使用できます。
これは主に、`Unit` を返す qubits で操作を呼び出すときに使用されます。これは、ステートメントの目的が暗黙的なクォンタムの状態を変更するためです。
式の評価ステートメントでは、セミコロンを終了する必要があります。

たとえば、次のように入力します。

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
