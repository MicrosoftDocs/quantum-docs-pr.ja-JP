---
title: 'Q # の手法-さらに進める |Microsoft Docs'
description: 'Q # の手法-詳細'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183303"
---
# <a name="going-further"></a>さらに進める #

ここでは、興味深いクォンタムプログラムを Q # で記述する方法について説明しました。このセクションでは、さらに高度なトピックをいくつか紹介します。

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a>一般的な操作と関数 ##

> [!TIP]
> このセクションでは、の[ジェネリックC# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [、 F#のジェネリック、 ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++テンプレート](https://docs.microsoft.com/cpp/cpp/templates-cpp)、または他の言語のメタプログラミングに関する同様のアプローチに関する基本的な知識を前提としています。

定義する関数や操作の多くは、実際には入力の型にあまり依存していませんが、他の関数や演算を介して暗黙的に型を使用するだけではありません。
たとえば、多くの関数言語に共通する*マップ*の概念を考えてみます。関数 $f (x) $ と値 $\{x_1、x_2、\ ドット、x_n\}$ のコレクションが指定されている場合、map は新しいコレクション $\{f (x_1)、f (x_2)、\ ドット、f (x_n)\}$ を返します。
これを Q # に実装するには、その関数を最初のクラスとして利用できます。
ここでは、★をプレースホルダーとして使用し、必要な型を確認しながら、`Map`の簡単な例を記述します。

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

注この関数は、どのような実際の型を置き換えるかに関係なく、非常によく似ています。
たとえば、整数から Paulis へのマップは、浮動小数点数から文字列へのマップとほぼ同じです。

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

原則として、発生した型のペアごとに1つのバージョンの `Map` を記述できますが、これには多くの問題が伴います。
たとえば、`Map`でバグが見つかった場合は、すべてのバージョンの `Map`で修正が一様に適用されていることを確認する必要があります。
さらに、新しい組または UDT を構築する場合は、新しい型と共に新しい `Map` を作成する必要もあります。
これは、このような関数の少数の扱いですが、`Map`と同じ形式の関数をさらに多く収集するので、新しい型の導入にかかるコストは非常に短い順序で大きくなります。

しかし、このような問題の多くは、コンパイラによって異なるバージョンの `Map` がどのように関連付けられているかを認識するために必要な情報をコンパイラに与えていないからです。
実際には、コンパイラは `Map` を Q #*型*から q # 関数に対して何らかの種類の数学関数として扱う必要があります。
この概念は、関数と操作が*型パラメーター*を持ち、その通常のタプルパラメーターを持つことができるようにすることで形式化されています。
上記の例では、最初のケースでは型パラメーター `Int, Pauli`、2番目のケースでは `Double, String` として `Map` を考えます。
ほとんどの場合、これらの型パラメーターは通常の型のように使用できます。型パラメーターの値を使用して、配列と組を作成し、関数と演算を呼び出し、通常の変数または変更可能な変数に代入します。

> [!NOTE]
> 間接的な依存関係の最も極端な例として、qubits の場合があります。この場合、Q # プログラムは `Qubit` 型の構造に直接依存することはできませんが、そのような型を他の操作や関数に渡す**必要があり**ます。

上記の例に戻ると、型パラメーターを持つ `Map` が必要であることがわかります。1つは `fn` への入力を表し、もう1つは `fn`からの出力を表します。
Q # では、宣言内の関数または操作の名前の後に山かっこ (brakets $ \braket{}$! ではなく `<>`) を追加し、それぞれの型パラメーターを一覧表示することによって記述されます。
各型パラメーターの名前は、ティック `'`で始める必要があります。これは、型パラメーターであり、通常の型 (*具象*型とも呼ばれます) ではないことを示します。
`Map`には、次のように記述します。

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

`Map<'Input, 'Output>` の定義は、前に記述したバージョンと非常によく似ていることに注意してください。
唯一の違いは、コンパイラに対して、`'Input` と `'Output` に直接依存せず、`fn`を通じて間接的に使用することで、任意の2つの型に対して機能 `Map` することを明示的に通知したことです。
この方法で `Map<'Input, 'Output>` を定義したら、通常の関数と同じように呼び出すことができます。

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> ジェネリック関数と操作の記述は、"組イン組アウト" が Q # の関数と演算について考える非常に便利な方法である1つの場所です。
> すべての関数は1つの入力を受け取り、ただ1つの出力を返すため、`'T -> 'U` 型の入力は、どの Q # 関数と*も*一致します。
> 同様に、任意の操作を `'T => 'U`型の入力に渡すこともできます。

2番目の例として、次の2つの関数の合成を返す関数を記述するという課題を考えてみます。

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

ここでは、`A`、`B`、および `C` を正確に指定して、新しい `Compose` 関数のユーティリティを大幅に制限する必要があります。
結局のところ、`Compose` は `innerFn` と `outerFn`を*使用*して `A`、`B`、および `C` にのみ依存しています。
別の方法として、`Compose` に型パラメーターを追加して、`A`、`B`、および `C`で動作することを示すことができます。ただし、*これらのパラメーター*が `innerFn` によって想定されているものと一致している必要があり `outerFn`:

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

## <a name="borrowing-qubits"></a>借りた Qubits ##

借用機構を使用すると、計算中にスクラッチ領域として使用できる qubits を割り当てることができます。 通常、これらの qubits はクリーンな状態ではありません。つまり、$ \ket{0}$ などの既知の状態で初期化されるとは限りません。 また、状態が不明であり、quantum コンピューターのメモリの他の部分でも使用できるようになったため、"ダーティ" な qubits もあります。 ダーティ qubits の既知のユースケースの中では、incrementers の少数の qubits と実装のみを必要とする、マルチ制御の CNOT ゲートの実装があります。

キャノンには、`borrowing` キーワードを使用する例が用意されています。たとえば、次のように定義されている関数 `MultiControlledXBorrow` ます。
`controls` が `X` 操作に追加する必要があるコントロール qubits を表している場合は、この実装によって `Length(controls)-2` 多くのダーティ ancillas が追加されます。

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

`With` 連結子は、adjoint をサポートする操作に適用される形式で---連結されていることに注意してください。つまり、この例では `WithA`---、`With` を含む構造体にコントロールを追加するのに適したプログラミングスタイルです。コントロールを内部操作に伝達します。 また、ここでは、操作の `body` に加えて、`controlled auto` ステートメントを実行するのではなく、操作の `controlled` 本体の実装が明示的に指定されていることに注意してください。 その理由は、サーキットの構造からわかるということです。これは、`body`内の各ゲートにコントロールを追加することに比べて、役に立つコントロールを簡単に追加する方法です。 

このコードを別のキャノン `MultiControlledXClean` 関数と比較することができます。これは、`using` メカニズムを使用していくつかの clean qubits を使用する、乗算制御 `X` 演算を実装するのと同じ目標を達成します。 
