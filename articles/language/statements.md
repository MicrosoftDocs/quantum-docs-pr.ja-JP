---
title: 'Q# ステートメント'
description: '関数と操作の宣言、変数の宣言と代入、操作の呼び出しなど、Q# でのステートメントの正しい使用方法について説明します。'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e801a5fdd24b973f47d23d2aca6f11bbebf333d4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904674"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="bf409-103">ステートメントとその他の構成体</span><span class="sxs-lookup"><span data-stu-id="bf409-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="bf409-104">コメント</span><span class="sxs-lookup"><span data-stu-id="bf409-104">Comments</span></span>

<span data-ttu-id="bf409-105">コメントは、2つのスラッシュ (`//`) で始まり、行の終わりまで続きます。</span><span class="sxs-lookup"><span data-stu-id="bf409-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="bf409-106">Q# ソースファイル内の任意の場所にコメントが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="bf409-107">ドキュメントのコメント</span><span class="sxs-lookup"><span data-stu-id="bf409-107">Documentation Comments</span></span>

<span data-ttu-id="bf409-108">3つのスラッシュ (`///`) で始まるコメントは、名前空間、操作、特殊化、関数、または型定義の直前に出現するときに、コンパイラによって特別に処理されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="bf409-109">その場合、その内容は、他の .NET 言語と同様に、定義された呼び出し可能またはユーザー定義型のドキュメントとして取得されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="bf409-110">`///` コメントでは、API ドキュメントの一部として表示されるテキストは [Markdown](https://daringfireball.net/projects/markdown/syntax) として書式設定され、ドキュメントのさまざまな部分が特別な名前のヘッダーによって示されています。</span><span class="sxs-lookup"><span data-stu-id="bf409-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="bf409-111">Markdown の拡張機能として、Q# の操作、関数、ユーザー定義型への相互参照は、`@"<ref target>"`を使用して含めることができます。 `<ref target>` は参照されるコードオブジェクトの完全修飾名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="bf409-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="bf409-112">必要に応じて、ドキュメントエンジンで追加の Markdown 拡張機能をサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bf409-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="bf409-113">例 :</span><span class="sxs-lookup"><span data-stu-id="bf409-113">For example:</span></span>

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

<span data-ttu-id="bf409-114">次の名前は、ドキュメントのコメントヘッダーとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="bf409-115">**Summary**: 関数または操作の動作、または型の目的の簡単な概要。</span><span class="sxs-lookup"><span data-stu-id="bf409-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="bf409-116">概要の最初の段落は、ホバー情報に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="bf409-117">プレーンテキストである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-117">It should be plain text.</span></span>
- <span data-ttu-id="bf409-118">**説明**: 関数または操作の動作、または型の目的の説明。</span><span class="sxs-lookup"><span data-stu-id="bf409-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="bf409-119">概要と説明を連結して、関数、操作、または型の生成されたドキュメントファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf409-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="bf409-120">説明には、インラインの LaTeX 形式のシンボルと式を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bf409-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="bf409-121">**入力**: 操作または関数の入力タプルの説明。</span><span class="sxs-lookup"><span data-stu-id="bf409-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="bf409-122">入力タプルの各要素を示す追加の Markdown サブセクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bf409-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="bf409-123">**出力**: 演算または関数によって返される組の説明。</span><span class="sxs-lookup"><span data-stu-id="bf409-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="bf409-124">**型パラメーター**: ジェネリック型パラメーターごとに1つの追加のサブセクションを含む空のセクション。</span><span class="sxs-lookup"><span data-stu-id="bf409-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="bf409-125">**例**: 使用されている操作、関数、または型の簡単な例。</span><span class="sxs-lookup"><span data-stu-id="bf409-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="bf409-126">**解説**: 操作、関数、または型のいくつかの側面を説明するその他の prose。</span><span class="sxs-lookup"><span data-stu-id="bf409-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="bf409-127">関連する関数、操作、またはユーザー定義型を示す完全修飾名の一覧**も参照してください**。</span><span class="sxs-lookup"><span data-stu-id="bf409-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="bf409-128">**参照**: ドキュメント化されている項目の参照および引用の一覧。</span><span class="sxs-lookup"><span data-stu-id="bf409-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="bf409-129">名前空間</span><span class="sxs-lookup"><span data-stu-id="bf409-129">Namespaces</span></span>

<span data-ttu-id="bf409-130">すべての Q# 操作、関数、およびユーザー定義型は、名前空間内で定義されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="bf409-131">Q# は、他の .NET 言語として名前を付ける場合と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="bf409-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="bf409-132">ただし、Q# では名前空間への相対参照はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bf409-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="bf409-133">つまり、名前空間 `a.b` が開かれている場合、操作名への参照 `c.d` は、完全な名前 `a.b.c.d`を持つ操作に解決されません。</span><span class="sxs-lookup"><span data-stu-id="bf409-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="bf409-134">名前空間ブロック内では、`open` ディレクティブを使用して、特定の名前空間で宣言されたすべての型と呼び出し可能な型をインポートし、非修飾名で参照することができます。</span><span class="sxs-lookup"><span data-stu-id="bf409-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="bf409-135">必要に応じて、名前空間のすべての要素が定義された短い名前によって修飾されるように、開いている名前空間の短い名前を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf409-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="bf409-136">`open` ディレクティブは、ファイル内の名前空間ブロック全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="bf409-137">現在の名前空間で開かれていない別の名前空間で定義されている型または呼び出し可能が、完全修飾名で参照されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="bf409-138">たとえば、現在のブロックで `X.Y` 名前空間が開かれていない限り、`X.Y` 名前空間の `Op` という名前の操作は、完全修飾名 `X.Y.Op`によって参照される必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="bf409-139">前述のように、`X` 名前空間が開かれていても、`Y.Op`として操作を参照することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf409-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="bf409-140">名前空間とファイルで `X.Y` の短い名前 `Z` が定義されている場合は、`Op` を `Z.Op`として参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="bf409-141">通常は、`open` ディレクティブを使用して名前空間を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf409-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="bf409-142">2つの名前空間で同じ名前の構造体を定義し、現在のソースが両方のコンストラクトを使用する場合は、完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="bf409-143">書式設定</span><span class="sxs-lookup"><span data-stu-id="bf409-143">Formatting</span></span>

<span data-ttu-id="bf409-144">ほとんどの Q# ステートメントおよびディレクティブは、終端のセミコロンで終わります `;`。</span><span class="sxs-lookup"><span data-stu-id="bf409-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="bf409-145">ステートメントブロックで終わる `for` や `operation` などのステートメントと宣言には、終端のセミコロンは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bf409-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="bf409-146">各ステートメントの説明には、終端のセミコロンが必要かどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="bf409-147">ステートメント (式、宣言、ディレクティブなど) は、複数の行にわたって分割される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="bf409-148">1行に複数のステートメントを記述することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="bf409-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="bf409-149">ステートメントブロック</span><span class="sxs-lookup"><span data-stu-id="bf409-149">Statement Blocks</span></span>

<span data-ttu-id="bf409-150">Q# ステートメントは、ステートメントブロックにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="bf409-151">ステートメントブロックが開始 `{` で始まり、終了 `}`で終わります。</span><span class="sxs-lookup"><span data-stu-id="bf409-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="bf409-152">別のブロック内で構文的に囲まれたステートメントブロックは、それを含むブロックのサブブロックと見なされます。コンテナーとサブブロックは、外部ブロックと内部ブロックとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="bf409-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="bf409-153">シンボルのバインドと代入</span><span class="sxs-lookup"><span data-stu-id="bf409-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="bf409-154">Q# は、変更可能なシンボルと変更できないシンボルを区別します。</span><span class="sxs-lookup"><span data-stu-id="bf409-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="bf409-155">一般に、変更できないシンボルを使用することをお勧めします。これにより、コンパイラはより多くの最適化を実行できるためです。</span><span class="sxs-lookup"><span data-stu-id="bf409-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="bf409-156">バインディングの左側は、記号の組と式の右辺で構成されています。</span><span class="sxs-lookup"><span data-stu-id="bf409-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="bf409-157">すべての Q# 型は値型であるため、qubits が多少特別なロールを使用すると、値がシンボルにバインドされたとき、またはシンボルが再バインドされるときに "コピー" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="bf409-158">つまり、Q# の動作は、割り当て時にコピーが作成された場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="bf409-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="bf409-159">これには、配列も含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf409-159">This in particular also includes arrays.</span></span> <span data-ttu-id="bf409-160">もちろん、実際には、関連する部分のみが必要に応じて再作成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="bf409-161">タプル分解</span><span class="sxs-lookup"><span data-stu-id="bf409-161">Tuple Deconstruction</span></span>

<span data-ttu-id="bf409-162">バインドの右側がタプルの場合、そのタプルは代入時に分解される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="bf409-163">このような deconstructions には、入れ子になった組が含まれる場合があります。また、右辺の組の構造がシンボルの組の形状と互換性がある限り、完全または部分的な分解は有効です。</span><span class="sxs-lookup"><span data-stu-id="bf409-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="bf409-164">分解 `=` の右辺がタプル値式の場合にも、タプルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="bf409-165">変更できないシンボル</span><span class="sxs-lookup"><span data-stu-id="bf409-165">Immutable Symbols</span></span>

<span data-ttu-id="bf409-166">変更できないシンボルは、`let` ステートメントを使用してバインドされます。</span><span class="sxs-lookup"><span data-stu-id="bf409-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="bf409-167">これは、などC#の言語での変数宣言および初期化とほぼ同じですが、Q# 記号はバインドされると変更されない可能性がある点が異なります。`let` バインドは変更できません。</span><span class="sxs-lookup"><span data-stu-id="bf409-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="bf409-168">変更できないバインドは、キーワード `let`、その後にシンボルまたは記号の組、等号 `=`、記号をバインドする式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="bf409-169">バインドされたシンボルの型は、右側の式に基づいて推論されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="bf409-170">変更可能なシンボル</span><span class="sxs-lookup"><span data-stu-id="bf409-170">Mutable Symbols</span></span>

<span data-ttu-id="bf409-171">変更可能なシンボルは、`mutable` ステートメントを使用して定義および初期化します。</span><span class="sxs-lookup"><span data-stu-id="bf409-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="bf409-172">`mutable` ステートメントの一部として宣言およびバインドされたシンボルは、コードの後半で別の値に再バインドされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="bf409-173">変更可能なバインドステートメントは、キーワード `mutable`、その後にシンボルまたは記号の組、等号 `=`、記号をバインドする式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="bf409-174">バインドされたシンボルの型は、右側の式に基づいて推論されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="bf409-175">シンボルが後でコード内で再バインドされる場合、その型は変更されず、バインドされた値はその型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="bf409-176">再バインド (変更可能なシンボルの)</span><span class="sxs-lookup"><span data-stu-id="bf409-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="bf409-177">変更可能な変数は、`set` ステートメントを使用して再バインドすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf409-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="bf409-178">このような再バインドは、キーワード `set`、その後にシンボルまたは記号の組、等号 `=`、等号を再バインドする式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="bf409-179">値は、バインド先のシンボルの型と互換性がある必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="bf409-180">Apply ステートメントと再割り当てステートメント</span><span class="sxs-lookup"><span data-stu-id="bf409-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="bf409-181">特定の種類のセットステートメントは、適用と再割り当てのステートメントとして参照します。右辺が二項演算子のアプリケーションで構成され、結果が演算子の左辺の引数に再バインドされる場合、連結の便利な方法となります。</span><span class="sxs-lookup"><span data-stu-id="bf409-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="bf409-182">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="bf409-183">`for` ループの各反復処理でカウンター `counter` の値をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="bf409-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="bf409-184">上記のコードは、</span><span class="sxs-lookup"><span data-stu-id="bf409-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="bf409-185">左辺の型が式の型と一致するすべての二項演算子に対して、同様のステートメントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="bf409-186">これにより、たとえば、値を累積する便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="bf409-187">Update および-再割り当てステートメント</span><span class="sxs-lookup"><span data-stu-id="bf409-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="bf409-188">右側にコピーと更新の式がある場合も同様の連結が存在します。</span><span class="sxs-lookup"><span data-stu-id="bf409-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="bf409-189">それに応じて、ユーザー定義型および配列項目の名前付き項目に対して、更新と再割り当てのステートメントが存在します。</span><span class="sxs-lookup"><span data-stu-id="bf409-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

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

<span data-ttu-id="bf409-190">配列の場合、標準ライブラリには、多くの一般的な配列の初期化と操作に必要なツールが含まれているため、最初の場所で配列項目を更新する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="bf409-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="bf409-191">必要に応じて、更新ステートメントと再割り当てステートメントで代替手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="bf409-191">Update-and-reassign statements provide an alternative if needed:</span></span>

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
> <span data-ttu-id="bf409-192"><xref:microsoft.quantum.arrays>に用意されているツールを利用して、更新と再割り当てのステートメントを不要に使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="bf409-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="bf409-193">関数</span><span class="sxs-lookup"><span data-stu-id="bf409-193">The function</span></span>
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
<span data-ttu-id="bf409-194">たとえば、`Microsoft.Quantum.Arrays`の関数 `ConstantArray` を使用して単純化し、コピーと更新の式を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf409-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="bf409-195">スコープのバインド</span><span class="sxs-lookup"><span data-stu-id="bf409-195">Binding Scopes</span></span>

<span data-ttu-id="bf409-196">一般に、シンボルバインドはスコープ外に出、ステートメントブロックの最後では動作しなくなります。</span><span class="sxs-lookup"><span data-stu-id="bf409-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="bf409-197">このルールには次の 2 つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="bf409-198">`for` ループのループ変数のバインドは、for ループの本体のスコープ内にありますが、ループの終了後には適用されません。</span><span class="sxs-lookup"><span data-stu-id="bf409-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="bf409-199">`repeat`/`until` ループ (本文、テスト、および修正) の3つの部分はすべて1つのスコープとして扱われるので、本文にバインドされているシンボルはテストとフィックスアップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="bf409-200">両方の種類のループでは、ループの各パスが独自のスコープ内で実行されるため、以前のパスからのバインドは、後のパスでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="bf409-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="bf409-201">外部ブロックからのシンボルバインディングは、内部ブロックによって継承されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="bf409-202">シンボルをバインドできるのは、ブロックごとに1回だけです。スコープ内にある別のシンボルと同じ名前のシンボルを定義することはできません ("シャドウ" はありません)。</span><span class="sxs-lookup"><span data-stu-id="bf409-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="bf409-203">有効なシーケンスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bf409-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="bf409-204">and</span><span class="sxs-lookup"><span data-stu-id="bf409-204">and</span></span>

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

<span data-ttu-id="bf409-205">ただし、これは無効になります。</span><span class="sxs-lookup"><span data-stu-id="bf409-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="bf409-206">次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bf409-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="bf409-207">制御フロー</span><span class="sxs-lookup"><span data-stu-id="bf409-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="bf409-208">For ループ</span><span class="sxs-lookup"><span data-stu-id="bf409-208">For Loop</span></span>

<span data-ttu-id="bf409-209">`for` ステートメントは、整数範囲または配列に対する反復処理をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="bf409-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="bf409-210">ステートメントは、キーワード `for`、始めかっこ `(`、シンボルまたは記号の組、キーワード `in`、`Range` または配列型の式、終わりかっこ `)`、およびステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="bf409-211">ステートメントブロック (ループの本体) は、範囲または配列の各値にバインドされたシンボル (ループ変数) を使用して繰り返し実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="bf409-212">範囲式が空の範囲または配列に評価される場合、本文はまったく実行されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf409-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="bf409-213">式はループに入る前に完全に評価され、ループの実行中は変更されません。</span><span class="sxs-lookup"><span data-stu-id="bf409-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="bf409-214">宣言されたシンボルのバインドは不変であり、他の変数バインドと同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="bf409-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="bf409-215">特に、ループ変数への代入時に配列に対する反復処理の配列項目などを破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="bf409-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="bf409-216">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-216">For example,</span></span>

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

<span data-ttu-id="bf409-217">ループ変数は、ループ本体の各入口でバインドされ、本文の最後にバインド解除されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="bf409-218">特に、ループ変数は for ループの完了後にバインドされません。</span><span class="sxs-lookup"><span data-stu-id="bf409-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="bf409-219">繰り返し-成功ループ</span><span class="sxs-lookup"><span data-stu-id="bf409-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="bf409-220">`repeat` ステートメントでは、"成功までの繰り返し" パターンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf409-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="bf409-221">これは、キーワード `repeat`、ステートメントブロック (_ループ_本体)、キーワード `until`、ブール式、終了セミコロンまたはキーワード `fixup` の後に別のステートメントブロック ( _fixup_) が続きます。</span><span class="sxs-lookup"><span data-stu-id="bf409-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="bf409-222">ループ本体、条件、および修正はすべて1つのスコープであると見なされるため、本文にバインドされているシンボルは、条件と修正に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

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

<span data-ttu-id="bf409-223">ループの本体が実行され、条件が評価されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="bf409-224">条件が true の場合、ステートメントは完了します。それ以外の場合は、fixup が実行され、ループ本体からステートメントが再実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="bf409-225">修正の実行を完了すると、ステートメントのスコープが終了します。これにより、本体またはフィックスアップ中に作成されたシンボルバインドは、後続の繰り返しでは使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bf409-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="bf409-226">たとえば、次のコードは、Hadamard と T ゲートを使用して、重要な回転ゲート $V (& 3)、(確率論的 + 2 i Z)/\ sqrt{5}$ を実装する、中心となる回路です。</span><span class="sxs-lookup"><span data-stu-id="bf409-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="bf409-227">ループは $-frac{8}で終了し、平均で $ 繰り返し {5}ます。</span><span class="sxs-lookup"><span data-stu-id="bf409-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="bf409-228">詳細については、「繰り返し-成功するまで」を参照してください。 [*1 つの qubit unitaries 非決定的分解*](https://arxiv.org/abs/1311.1074)(paetznick と svore 2014) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf409-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

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
> <span data-ttu-id="bf409-229">関数内での繰り返しの成功ループの使用は避けてください。</span><span class="sxs-lookup"><span data-stu-id="bf409-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="bf409-230">対応する機能は、関数の while ループによって提供されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="bf409-231">While ループ</span><span class="sxs-lookup"><span data-stu-id="bf409-231">While Loop</span></span>

<span data-ttu-id="bf409-232">繰り返し-成功パターンには、クォンタム固有の connotation があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="bf409-233">これらは、特定のクラスのクォンタムアルゴリズムで広く使用されているため、Q# の専用言語構成要素です。</span><span class="sxs-lookup"><span data-stu-id="bf409-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="bf409-234">ただし、条件に基づいて中断されるループでは、実行の長さがコンパイル時に不明であるため、クォンタムランタイムでは特に注意して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="bf409-235">一方、関数内での使用は、従来の (非クォンタム) ハードウェアで実行されるコードのみを含むため、問題はありません。</span><span class="sxs-lookup"><span data-stu-id="bf409-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="bf409-236">そのため、Q# では、関数内でのみ while ループを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="bf409-237">`while` ステートメントは、キーワード `while`、開いているかっこ `(`、条件 (ブール式)、終わりかっこ `)`、およびステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="bf409-238">ステートメントブロック (ループの本体) は、条件が `true`に評価される限り実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="bf409-239">条件付きステートメント</span><span class="sxs-lookup"><span data-stu-id="bf409-239">Conditional Statement</span></span>

<span data-ttu-id="bf409-240">`if` ステートメントでは、条件付き実行がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf409-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="bf409-241">これは、キーワード `if`、始めかっこ `(`、ブール式、終わりかっこ `)`、およびステートメントブロック ( _then_ブロック) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="bf409-242">その後には、任意の数の else if 句を指定できます。これらは、それぞれキーワード `elif`、始めかっこ `(`、ブール式、終わりかっこ `)`、およびステートメントブロック ( _else_ブロック) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="bf409-243">最後に、ステートメントは、キーワード `else` の後に別のステートメントブロック ( _else_ブロック) が続く else 句を使用して終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf409-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="bf409-244">条件が評価され、true の場合は then ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="bf409-245">条件が false の場合、最初の else if 条件が評価されます。true の場合は、それ以外の場合は if ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="bf409-246">それ以外の場合は、2番目の else-if ブロックがテストされ、3番目以降の場合は、true 条件を持つ句が検出されるか、それ以上の else if 句が存在しなくなるまで続きます。</span><span class="sxs-lookup"><span data-stu-id="bf409-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="bf409-247">元の if 条件とすべての else-if 句が false と評価された場合、else ブロックが指定されていると、else ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="bf409-248">実行されるブロックはいずれも、それ自体のスコープ内で実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf409-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="bf409-249">Then、else、または else ブロック内で行われたバインディングは、if ステートメントの終了後には参照できません。</span><span class="sxs-lookup"><span data-stu-id="bf409-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="bf409-250">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="bf409-251">or</span><span class="sxs-lookup"><span data-stu-id="bf409-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="bf409-252">戻り値</span><span class="sxs-lookup"><span data-stu-id="bf409-252">Return</span></span>

<span data-ttu-id="bf409-253">Return ステートメントは、操作または関数の実行を終了し、呼び出し元に値を返します。</span><span class="sxs-lookup"><span data-stu-id="bf409-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="bf409-254">これは、キーワード `return`、適切な型の式、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="bf409-255">空のタプルを返す呼び出し可能 `()`には、return ステートメントは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bf409-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="bf409-256">早期終了が必要な場合は、この場合に `return ()` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="bf409-257">他の型を返す呼び出しを行うには、最終的な return ステートメントが必要です。</span><span class="sxs-lookup"><span data-stu-id="bf409-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="bf409-258">操作内に return ステートメントの最大数がありません。</span><span class="sxs-lookup"><span data-stu-id="bf409-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="bf409-259">ステートメントがブロック内の return ステートメントに続く場合、コンパイラは警告を生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf409-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="bf409-260">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="bf409-261">or</span><span class="sxs-lookup"><span data-stu-id="bf409-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="bf409-262">or</span><span class="sxs-lookup"><span data-stu-id="bf409-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="bf409-263">失敗</span><span class="sxs-lookup"><span data-stu-id="bf409-263">Fail</span></span>

<span data-ttu-id="bf409-264">Fail ステートメントは、操作の実行を終了し、呼び出し元にエラー値を返します。</span><span class="sxs-lookup"><span data-stu-id="bf409-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="bf409-265">これは、キーワード `fail`と、その後に続く文字列と終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="bf409-266">文字列は、エラーメッセージとしてクラシックドライバーに返されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="bf409-267">操作内の fail ステートメントの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="bf409-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="bf409-268">ステートメントがブロック内の fail ステートメントに続く場合、コンパイラは警告を生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf409-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="bf409-269">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="bf409-270">or</span><span class="sxs-lookup"><span data-stu-id="bf409-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="bf409-271">Qubit 管理</span><span class="sxs-lookup"><span data-stu-id="bf409-271">Qubit Management</span></span>

<span data-ttu-id="bf409-272">関数の本体内では、これらのステートメントを使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bf409-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="bf409-273">これらは、操作内でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="bf409-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="bf409-274">Clean Qubits</span><span class="sxs-lookup"><span data-stu-id="bf409-274">Clean Qubits</span></span>

<span data-ttu-id="bf409-275">`using` ステートメントは、ステートメントブロック中に使用する新しい qubits を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="bf409-276">Qubits は、計算 `Zero` 状態に初期化されることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="bf409-277">Qubits は、ステートメントブロックの最後にある計算 `Zero` 状態である必要があります。シミュレーターでは、これを強制することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf409-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="bf409-278">このステートメントは、キーワード `using`で構成され、始めかっこ `(`、バインド、終わりかっこ `)`、および qubits が使用可能になるステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="bf409-279">バインディングは、`let` ステートメントと同じパターンに従います。1つのシンボルまたはシンボルのタプルの後に等号 `=`、1つの値、または初期化子の一致するタプルのいずれかを指定します。</span><span class="sxs-lookup"><span data-stu-id="bf409-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="bf409-280">初期化子は、1つの qubit、`Qubit()`として示されるか、`Qubit[`、`Int` 式、および `]`によって示される qubit の配列で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="bf409-281">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="bf409-282">借りた Qubits</span><span class="sxs-lookup"><span data-stu-id="bf409-282">Borrowed Qubits</span></span>

<span data-ttu-id="bf409-283">`borrowing` ステートメントは、一時的な使用のために qubits を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="bf409-284">このステートメントは、キーワード `borrowing`で構成され、始めかっこ `(`、バインド、終わりかっこ `)`、および qubits が使用可能になるステートメントブロックで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="bf409-285">バインディングは、`using` ステートメントと同じパターンおよび規則に従います。</span><span class="sxs-lookup"><span data-stu-id="bf409-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="bf409-286">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="bf409-287">借用した qubits は不明な状態であり、ステートメントブロックの最後でスコープ外に出ます。</span><span class="sxs-lookup"><span data-stu-id="bf409-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="bf409-288">借り手は、貸し出しされたときと同じ状態に qubits を残すことをコミットします。つまり、ステートメントブロックの先頭と末尾の状態は同じであると想定されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="bf409-289">特に、この状態は必ずしも古典的な状態ではありません。ほとんどの場合、借りているスコープには測定値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="bf409-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="bf409-290">借り qubits の使用例については、「 [*2n + 2 qubits と Toffoli ベースのモジュール乗算 2017 (ベースのモジュール型乗算) を使用したファクタリング*](https://arxiv.org/abs/1611.07995)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf409-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="bf409-291">Qubits を借りている場合、システムはまず、使用中であるが、`borrowing` ステートメントの本体ではアクセスされない qubits から要求を入力しようとします。</span><span class="sxs-lookup"><span data-stu-id="bf409-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="bf409-292">このような qubits が不足している場合は、要求を完了するために新しい qubits が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bf409-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="bf409-293">活用</span><span class="sxs-lookup"><span data-stu-id="bf409-293">Conjugations</span></span>

<span data-ttu-id="bf409-294">従来のビットとは対照的に、qubits を再設定すると、qubits の差が大きくなっても残りの計算には望ましくない影響が生じる可能性があるため、量子メモリの解放は若干複雑になります。</span><span class="sxs-lookup"><span data-stu-id="bf409-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="bf409-295">これは、メモリを解放する前に、実行された計算を適切に "元に戻す" ことで回避できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="bf409-296">クォンタムコンピューティングの一般的なパターンは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bf409-296">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="bf409-297">: 新規: 0.9 リリース以降では、上記の変換を実装する活用形ステートメントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bf409-297">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="bf409-298">このステートメントを使用すると、次のように操作 `ApplyWith` を実装できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="bf409-299">このような活用形ステートメントは、外部と内部の変換を操作として簡単に利用できず、複数のステートメントで構成されるブロックで記述する方が便利な場合に、はるかに便利になります。</span><span class="sxs-lookup"><span data-stu-id="bf409-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="bf409-300">内部ブロックで定義されたステートメントの逆変換は、コンパイラによって自動的に生成され、適用ブロックの完了後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="bf409-301">内部ブロックの一部として使用される変更可能な変数は、適用ブロックで再バインドできないため、生成された変換は、ブロック内の計算の adjoint であることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="bf409-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="bf409-302">式の評価ステートメント</span><span class="sxs-lookup"><span data-stu-id="bf409-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="bf409-303">`Unit` 型の任意の呼び出し式は、ステートメントとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf409-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="bf409-304">これは主に、`Unit` を返す qubits で操作を呼び出すときに使用されます。これは、ステートメントの目的が暗黙的なクォンタムの状態を変更するためです。</span><span class="sxs-lookup"><span data-stu-id="bf409-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="bf409-305">式の評価ステートメントでは、セミコロンを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf409-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="bf409-306">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="bf409-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
