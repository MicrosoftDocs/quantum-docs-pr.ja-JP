---
title: 'ローカル変数- Q# の手法'
description: 'Q# でローカル変数を定義して操作する方法について説明します。'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906867"
---
# <a name="local-variables"></a><span data-ttu-id="2bc14-103">ローカル変数</span><span class="sxs-lookup"><span data-stu-id="2bc14-103">Local Variables</span></span> #

<span data-ttu-id="2bc14-104">Q# の任意の型の値を変数に代入して、`let` キーワードを使用して操作または関数内で再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="2bc14-105">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2bc14-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="2bc14-106">これにより、`measurementOperator`と呼ばれる変数に、特定の一連の P# li 演算子が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="2bc14-107">`let` ステートメントの右辺の式は明確で、型はコンパイラによって推論されるため、新しい変数の型を明示的に指定する必要がないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="2bc14-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="2bc14-108">Q# の変数は*変更*できません。つまり、変数がこのように定義されると、どのような方法でも変更することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="2bc14-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="2bc14-109">これにより、操作の `Adjoint` バリアントを適用するために、変数に対して動作する古典的なロジックの最適化など、いくつかの有益な最適化を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="2bc14-110">上記の `let` バインディングを使用して定義された変数は、操作の本体や `for` ループの内容など、特定のスコープに対してローカルです。</span><span class="sxs-lookup"><span data-stu-id="2bc14-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="2bc14-111">可能性</span><span class="sxs-lookup"><span data-stu-id="2bc14-111">Mutability</span></span> ##

<span data-ttu-id="2bc14-112">`let`で変数を作成する代わりに、`mutable` キーワードを使用して、`set` キーワードを使用して最初に作成した後に再バインドできる特別な変更可能な変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="2bc14-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="2bc14-113">Q# のすべての型 (配列を含む) は、値のセマンティクスに従います。</span><span class="sxs-lookup"><span data-stu-id="2bc14-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="2bc14-114">特に、配列項目を更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="2bc14-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="2bc14-115">既存の配列を変更するには、のレコードの場合と同じように、コピーと更新F#のメカニズムを利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bc14-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="2bc14-116">[`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays)に用意されている配列にライブラリツールを使用すると、たとえば、インデックス `i` の PPaulis li が指定された値を取得し、その他のすべてのエントリが id である、などの配列を返す関数を簡単に定義できます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="2bc14-117">ここでは、Q# のステートメントと式について説明するときに、配列の操作方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2bc14-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="2bc14-118">Q# 内の可変性は、型または値ではなく*シンボル*に適用される概念です。</span><span class="sxs-lookup"><span data-stu-id="2bc14-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="2bc14-119">具体的には、型システム内の表現が暗黙的または明示的に指定されておらず、バインディングが変更可能かどうか (`mutable` キーワードによって示されます)、または (`let`によって示されるように) 不変であるかどうかは、バインドされた変数の型を変更しません。</span><span class="sxs-lookup"><span data-stu-id="2bc14-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="2bc14-120">これは、特殊な関数と操作の中で、可能性を分離するための重要な方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="2bc14-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="2bc14-121">特に、変更可能な変数を使用する操作に対する adjoint の特殊化が自動生成されない場合でも、自動生成は、変更性を使用する関数を呼び出す操作に対しては正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="2bc14-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="2bc14-122">このため、可能な限り短い変更性を使用する関数と操作を作成することをお勧めします。これにより、残りのクォンタムプログラムは、通常の不変変数を使用して書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="2bc14-123">分解</span><span class="sxs-lookup"><span data-stu-id="2bc14-123">Deconstruction</span></span> ##

<span data-ttu-id="2bc14-124">1つの変数を割り当てるだけでなく、`let` キーワードと `mutable` キーワード (実際にはその他のバインドコンストラクト) を割り当てることに加えて、[タプル型](xref:microsoft.quantum.language.type-model#tuple-types)の内容を展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="2bc14-125">このフォームの割り当ては、そのタプルの要素を*分解*と言います。</span><span class="sxs-lookup"><span data-stu-id="2bc14-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="2bc14-126">たとえば、タプルによって Hamiltonian 内の用語をモデル化する場合、分解を使用して、その用語でシミュレートする必要があるさまざまなデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2bc14-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


