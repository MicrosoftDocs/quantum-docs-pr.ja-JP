---
title: 'Q # の手法-さらに進める |Microsoft Docs'
description: 'Q # の手法-詳細'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: c079364f8808304e0132fa2a4226cd6400e81339
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863148"
---
# <a name="going-further"></a><span data-ttu-id="620b1-103">追加情報</span><span class="sxs-lookup"><span data-stu-id="620b1-103">Going Further</span></span> #

<span data-ttu-id="620b1-104">ここでは、興味深いクォンタムプログラムを Q # で記述する方法について説明しました。このセクションでは、さらに高度なトピックをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="620b1-104">Now that you've seen how to write interesting quantum programs in Q#, this section goes further by introducing a few more advanced topics that should prove useful going forward.</span></span>


## <a name="generic-operations-and-functions"></a><span data-ttu-id="620b1-105">一般的な操作と関数</span><span class="sxs-lookup"><span data-stu-id="620b1-105">Generic Operations and Functions</span></span> ##

> [!TIP]
> <span data-ttu-id="620b1-106">このセクションでは、の[ジェネリックC# ](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics) [、 F#のジェネリック、 ](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/) [ C++テンプレート](https://docs.microsoft.com/cpp/cpp/templates-cpp)、または他の言語のメタプログラミングに関する同様のアプローチに関する基本的な知識を前提としています。</span><span class="sxs-lookup"><span data-stu-id="620b1-106">This section assumes some basic familiarity with [generics in C#](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics), [generics in F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/), [C++ templates](https://docs.microsoft.com/cpp/cpp/templates-cpp), or similar approaches to metaprogramming in other languages.</span></span>

<span data-ttu-id="620b1-107">定義する関数や操作の多くは、実際には入力の型にあまり依存していませんが、他の関数や演算を介して暗黙的に型を使用するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="620b1-107">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="620b1-108">たとえば、多くの関数言語に共通する*マップ*の概念を考えてみます。関数 $f (x) $ および値のコレクション $\{x_1、x_2、\ ドット、x_n\}$ を指定すると、map は新しいコレクション $\{f (x_1)、f (x_2)、\ ドット、f (x_n)\}$ を返します。</span><span class="sxs-lookup"><span data-stu-id="620b1-108">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="620b1-109">これを Q # に実装するには、その関数を最初のクラスとして利用できます。</span><span class="sxs-lookup"><span data-stu-id="620b1-109">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="620b1-110">ここでは、★をプレースホルダーとして使用し、必要な型を確認しながら、`Map`の簡単な例を記述します。</span><span class="sxs-lookup"><span data-stu-id="620b1-110">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="620b1-111">注この関数は、どのような実際の型を置き換えるかに関係なく、非常によく似ています。</span><span class="sxs-lookup"><span data-stu-id="620b1-111">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="620b1-112">たとえば、整数から Paulis へのマップは、浮動小数点数から文字列へのマップとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="620b1-112">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="620b1-113">原則として、発生した型のペアごとに1つのバージョンの `Map` を記述できますが、これには多くの問題が伴います。</span><span class="sxs-lookup"><span data-stu-id="620b1-113">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="620b1-114">たとえば、`Map`でバグが見つかった場合は、すべてのバージョンの `Map`で修正が一様に適用されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="620b1-114">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="620b1-115">さらに、新しい組または UDT を構築する場合は、新しい型と共に新しい `Map` を作成する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="620b1-115">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="620b1-116">これは、このような関数の少数の扱いですが、`Map`と同じ形式の関数をさらに多く収集するので、新しい型の導入にかかるコストは非常に短い順序で大きくなります。</span><span class="sxs-lookup"><span data-stu-id="620b1-116">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="620b1-117">しかし、このような問題の多くは、コンパイラによって異なるバージョンの `Map` がどのように関連付けられているかを認識するために必要な情報をコンパイラに与えていないからです。</span><span class="sxs-lookup"><span data-stu-id="620b1-117">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="620b1-118">実際には、コンパイラは `Map` を Q #*型*から q # 関数に対して何らかの種類の数学関数として扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="620b1-118">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>
<span data-ttu-id="620b1-119">この概念は、関数と操作が*型パラメーター*を持ち、その通常のタプルパラメーターを持つことができるようにすることで形式化されています。</span><span class="sxs-lookup"><span data-stu-id="620b1-119">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="620b1-120">上記の例では、最初のケースでは型パラメーター `Int, Pauli`、2番目のケースでは `Double, String` として `Map` を考えます。</span><span class="sxs-lookup"><span data-stu-id="620b1-120">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="620b1-121">ほとんどの場合、これらの型パラメーターは通常の型のように使用できます。型パラメーターの値を使用して、配列と組を作成し、関数と演算を呼び出し、通常の変数または変更可能な変数に代入します。</span><span class="sxs-lookup"><span data-stu-id="620b1-121">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="620b1-122">間接的な依存関係の最も極端な例として、qubits の場合があります。この場合、Q # プログラムは `Qubit` 型の構造に直接依存することはできませんが、そのような型を他の操作や関数に渡す**必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="620b1-122">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="620b1-123">上記の例に戻ると、型パラメーターを持つ `Map` が必要であることがわかります。1つは `fn` への入力を表し、もう1つは `fn`からの出力を表します。</span><span class="sxs-lookup"><span data-stu-id="620b1-123">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="620b1-124">Q # では、宣言内の関数または操作の名前の後に山かっこ (brakets $ \braket{}$! ではなく `<>`) を追加し、それぞれの型パラメーターを一覧表示することによって記述されます。</span><span class="sxs-lookup"><span data-stu-id="620b1-124">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="620b1-125">各型パラメーターの名前は、ティック `'`で始める必要があります。これは、型パラメーターであり、通常の型 (*具象*型とも呼ばれます) ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="620b1-125">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="620b1-126">`Map`には、次のように記述します。</span><span class="sxs-lookup"><span data-stu-id="620b1-126">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="620b1-127">`Map<'Input, 'Output>` の定義は、前に記述したバージョンと非常によく似ていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="620b1-127">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="620b1-128">唯一の違いは、コンパイラに対して、`'Input` と `'Output` に直接依存せず、`fn`を通じて間接的に使用することで、任意の2つの型に対して機能 `Map` することを明示的に通知したことです。</span><span class="sxs-lookup"><span data-stu-id="620b1-128">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="620b1-129">この方法で `Map<'Input, 'Output>` を定義したら、通常の関数と同じように呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="620b1-129">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="620b1-130">ジェネリック関数と操作の記述は、"組イン組アウト" が Q # の関数と演算について考える非常に便利な方法である1つの場所です。</span><span class="sxs-lookup"><span data-stu-id="620b1-130">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="620b1-131">すべての関数は1つの入力を受け取り、ただ1つの出力を返すため、`'T -> 'U` 型の入力は、どの Q # 関数と*も*一致します。</span><span class="sxs-lookup"><span data-stu-id="620b1-131">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="620b1-132">同様に、任意の操作を `'T => 'U`型の入力に渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="620b1-132">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="620b1-133">2番目の例として、次の2つの関数の合成を返す関数を記述するという課題を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="620b1-133">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="620b1-134">ここでは、`A`、`B`、および `C` を正確に指定して、新しい `Compose` 関数のユーティリティを大幅に制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="620b1-134">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="620b1-135">結局のところ、`Compose` は `innerFn` と `outerFn`を*使用*して `A`、`B`、および `C` にのみ依存しています。</span><span class="sxs-lookup"><span data-stu-id="620b1-135">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="620b1-136">別の方法として、`Compose` に型パラメーターを追加して、`A`、`B`、および `C`で動作することを示すことができます。ただし、*これらのパラメーター*が `innerFn` と `outerFn`によって想定されているものと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="620b1-136">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="620b1-137">Q # 標準ライブラリは、このような種類のパラメーター化された操作と関数の範囲を提供して、上位の制御フローを簡単に表現できるようにします。</span><span class="sxs-lookup"><span data-stu-id="620b1-137">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="620b1-138">これらの詳細については、「 [Q # 標準ライブラリ」ガイド](xref:microsoft.quantum.libraries.standard.intro)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="620b1-138">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>

## <a name="borrowing-qubits"></a><span data-ttu-id="620b1-139">借りた Qubits</span><span class="sxs-lookup"><span data-stu-id="620b1-139">Borrowing Qubits</span></span> ##

<span data-ttu-id="620b1-140">借用機構を使用すると、計算中にスクラッチ領域として使用できる qubits を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="620b1-140">The borrowing mechanism allows the allocation of qubits that can be used as scratch space during a computation.</span></span> <span data-ttu-id="620b1-141">通常、これらの qubits はクリーンな状態ではありません。つまり、$ \ket{0}$ などの既知の状態で初期化されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="620b1-141">These qubits are generally not in a clean state, i.e., they are not necessarily initialized in a known state such as $\ket{0}$.</span></span> <span data-ttu-id="620b1-142">また、状態が不明であり、quantum コンピューターのメモリの他の部分でも使用できるようになったため、"ダーティ" な qubits もあります。</span><span class="sxs-lookup"><span data-stu-id="620b1-142">One also speaks of "dirty" qubits as their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span> <span data-ttu-id="620b1-143">ダーティ qubits の既知のユースケースの中では、incrementers の少数の qubits と実装のみを必要とする、マルチ制御の CNOT ゲートの実装があります。</span><span class="sxs-lookup"><span data-stu-id="620b1-143">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>

<span data-ttu-id="620b1-144">キャノンには、`borrowing` キーワードを使用する例が用意されています。たとえば、次のように定義されている関数 `MultiControlledXBorrow` ます。</span><span class="sxs-lookup"><span data-stu-id="620b1-144">In the canon there are examples that use the `borrowing` keyword, for instance the function `MultiControlledXBorrow` defined below.</span></span>
<span data-ttu-id="620b1-145">`controls` が `X` 操作に追加する必要があるコントロール qubits を表している場合は、この実装によって `Length(controls)-2` 多くのダーティ ancillas が追加されます。</span><span class="sxs-lookup"><span data-stu-id="620b1-145">If `controls` denotes the control qubits that should be added to an `X` operation, then an overall of `Length(controls)-2` many dirty ancillas will be added by this implementation.</span></span>

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

<span data-ttu-id="620b1-146">`With` 連結子は、adjoint をサポートする操作に適用できる形式で---連結されていることに注意してください。つまり、この例では `WithA`---は、内部操作に対して制御を伝達するだけである構造 `With` 体にコントロールを追加するのが適切なプログラミングスタイルです。</span><span class="sxs-lookup"><span data-stu-id="620b1-146">Note that extensive use of the `With` combinator---in its form that is applicable for operations that support adjoint, i.e., `WithA`---was made in this example which is good programming style as adding control to structures involving `With` only propagates control to the inner operation.</span></span> <span data-ttu-id="620b1-147">また、ここでは、操作の `body` に加えて、`controlled auto` ステートメントを実行するのではなく、操作の `controlled` 本体の実装が明示的に指定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="620b1-147">Further note that here in addition to the `body` of the operation an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span> <span data-ttu-id="620b1-148">その理由は、サーキットの構造からわかるということです。これは、`body`内の各ゲートにコントロールを追加することに比べて、役に立つコントロールを簡単に追加する方法です。</span><span class="sxs-lookup"><span data-stu-id="620b1-148">The reason for this is that we know from the structure of the circuit how to easily add further controls which is beneficial compared to adding control to each and every individual gate in the `body`.</span></span> 

<span data-ttu-id="620b1-149">このコードを別のキャノン `MultiControlledXClean` 関数と比較することができます。これは、`using` メカニズムを使用していくつかの clean qubits を使用する、乗算制御 `X` 演算を実装するのと同じ目標を達成します。</span><span class="sxs-lookup"><span data-stu-id="620b1-149">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 
