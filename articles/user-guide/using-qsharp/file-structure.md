---
title: Q# ファイル構造
description: ファイルの構造と構文について説明し Q# ます。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833308"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="5528a-103">Q# ファイル構造</span><span class="sxs-lookup"><span data-stu-id="5528a-103">Q# File Structure</span></span>

<span data-ttu-id="5528a-104">ファイルは、一連の Q# *名前空間宣言*で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="5528a-105">各名前空間宣言には、ユーザー定義型、操作、および関数の宣言が含まれており、任意の数の宣言を任意の順序で含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5528a-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="5528a-106">名前空間内の宣言の詳細については、「 [ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)、 [操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)、および [関数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5528a-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="5528a-107">名前空間の宣言の外側に表示されるテキストは、コメントだけです。</span><span class="sxs-lookup"><span data-stu-id="5528a-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="5528a-108">特に、名前空間のドキュメントコメントは、宣言の前に記述します。</span><span class="sxs-lookup"><span data-stu-id="5528a-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="5528a-109">詳細については、この記事の [ドキュメントコメント](#documentation-comments) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5528a-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="5528a-110">名前空間の宣言</span><span class="sxs-lookup"><span data-stu-id="5528a-110">Namespace Declarations</span></span>

<span data-ttu-id="5528a-111">Q#通常、ファイルには名前空間宣言が1つしかありませんが、none を指定したり、空にしたり、コメントを含めたりすることができます。また、複数の名前空間を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5528a-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="5528a-112">名前空間宣言を入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5528a-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="5528a-113">同じ Q# 名前を持つ型、操作、または関数の宣言がない限り、同時にコンパイルされた複数のファイルで同じ名前空間を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="5528a-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="5528a-114">特に、宣言が同一であっても、複数のファイルの同じ名前空間で同じ型を定義することは無効です。</span><span class="sxs-lookup"><span data-stu-id="5528a-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="5528a-115">名前空間の宣言は、キーワード、 `namespace` その後に名前空間の名前、および中かっこで囲まれた名前空間に含まれる宣言で構成され `{ }` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="5528a-116">名前空間名は、ピリオドで区切られた1つまたは複数の有効な記号のシーケンスの .NET パターンに従い `.` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="5528a-117">たとえば、 `MyQuantumStuff` と `Microsoft.Quantum.Intrinsic` は有効な名前空間名です。</span><span class="sxs-lookup"><span data-stu-id="5528a-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="5528a-118">規則により、名前空間の名前の記号を大文字にします。ただし、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="5528a-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="5528a-119">ファイル内でさらに下に宣言されている型または呼び出し方向への参照は、適切に解決されます。型、操作、または関数の宣言を参照の前に記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5528a-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="5528a-120">オープンディレクティブ</span><span class="sxs-lookup"><span data-stu-id="5528a-120">Open Directives</span></span>

<span data-ttu-id="5528a-121">名前空間ブロック内では、ディレクティブを使用して、 `open` 特定の名前空間で宣言されたすべての型と呼び出し許容型をインポートし、非修飾名で参照します。</span><span class="sxs-lookup"><span data-stu-id="5528a-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="5528a-122">このようなディレクティブは、キーワードと、 `open` `open` その後に開く名前空間、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="5528a-123">すべて `open` のディレクティブは `function` 、 `operation` `newtype` 名前空間ブロック内の、、または宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5528a-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="5528a-124">必要に応じて、開いている名前空間の短い名前を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5528a-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="5528a-125">短い名前が定義されている場合は、定義された短い名前を使用して、その名前空間のすべての要素を修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5528a-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="5528a-126">たとえば、次の名前空間宣言とオープンディレクティブがあるとします。</span><span class="sxs-lookup"><span data-stu-id="5528a-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="5528a-127">宣言された操作がからの操作を使用する場合は `Op` `Microsoft.Quantum.Intrinsic` 、単にを使用して呼び出し `Op` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="5528a-128">ただし、から特定の関数を呼び出すには、 `Fn` `Microsoft.Quantum.Math` を使用してそれを呼び出す必要があり `Math.Fn` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="5528a-129">ディレクティブは、 `open` ファイル内の名前空間ブロック全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="5528a-130">このため、前と同じファイルに追加の名前空間を定義した場合、 Q# `NS` 2 番目の名前空間で定義されている操作/関数/型は、その中に open ディレクティブを繰り返していない限り、またはにアクセスできません `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 。</span><span class="sxs-lookup"><span data-stu-id="5528a-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="5528a-131">現在の名前空間で開かれて *いない* 別の名前空間で定義されている型または呼び出し可能を参照するには、完全修飾名で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5528a-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="5528a-132">たとえば、名前空間からという名前の操作を指定した場合は、 `Op` `X.Y` 次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5528a-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="5528a-133">`X.Y.Op` `X.Y` 現在のブロックで名前空間が既に開かれている場合を除き、完全修飾名で参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5528a-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="5528a-134">名前空間が開かれている場合でも、 `X` として操作を参照することはできません `Y.Op` 。</span><span class="sxs-lookup"><span data-stu-id="5528a-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="5528a-135">の名前空間とファイルに短い名前を定義した場合は `Z` `X.Y` 、をとして参照する必要があり `Op` `Z.Op` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="5528a-136">通常は、ディレクティブを使用して名前空間を含めることをお勧め `open` します。</span><span class="sxs-lookup"><span data-stu-id="5528a-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="5528a-137">2つの名前空間で同じ名前の構造体を定義し、現在のソースが両方のコンストラクトを使用する場合は、完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5528a-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="5528a-138">Q# は、他の .NET 言語として名前を付ける場合と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="5528a-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="5528a-139">ただし、で Q# は、名前空間への相対参照はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5528a-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="5528a-140">たとえば、名前空間が開いている場合、 `a.b` という名前の操作への参照は、 `c.d` 完全名を持つ操作に解決 *されません* `a.b.c.d` 。</span><span class="sxs-lookup"><span data-stu-id="5528a-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="5528a-141">書式設定</span><span class="sxs-lookup"><span data-stu-id="5528a-141">Formatting</span></span>

<span data-ttu-id="5528a-142">ほとんどの Q# ステートメントおよびディレクティブは、終端のセミコロンで終わり `;` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="5528a-143">`for`ステートメントブロックで終了するやなどのステートメントや宣言 `operation` (次のセクションを参照) では、末尾にセミコロンを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5528a-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="5528a-144">各ステートメントの説明には、終端のセミコロンが必要かどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="5528a-145">ステートメント (式、宣言、ディレクティブなど) は、複数の行にわたって分割できます。</span><span class="sxs-lookup"><span data-stu-id="5528a-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="5528a-146">1行に複数のステートメントを配置することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="5528a-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="5528a-147">ステートメントブロック</span><span class="sxs-lookup"><span data-stu-id="5528a-147">Statement Blocks</span></span>

<span data-ttu-id="5528a-148">Q# ステートメントは、中かっこで囲まれたステートメントブロックにグループ化され `{ }` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="5528a-149">ステートメントブロックは、開始位置で始まり、 `{` 終わりで終わり `}` ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="5528a-150">別のブロック内で構文的に囲まれたステートメントブロックは、それを含むブロックのサブブロックと見なされます。コンテナーとサブブロックは、外部ブロックと内部ブロックとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5528a-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="5528a-151">コメント</span><span class="sxs-lookup"><span data-stu-id="5528a-151">Comments</span></span>

<span data-ttu-id="5528a-152">コメントは、2つのスラッシュ (,) で始まり、 `//` 行の終わりまで続きます。</span><span class="sxs-lookup"><span data-stu-id="5528a-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="5528a-153">コメントは、ソースファイル内の任意の場所に置くことができ Q# ます。</span><span class="sxs-lookup"><span data-stu-id="5528a-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="5528a-154">ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="5528a-154">Documentation Comments</span></span>

<span data-ttu-id="5528a-155">3つのスラッシュで始まるコメント `///` は、名前空間、操作、特殊化、関数、または型定義の直前に出現するときに、コンパイラによって特別に処理されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="5528a-156">その場合、コンパイラは、定義されている呼び出し可能またはユーザー定義型のドキュメントとして、他の .NET 言語と同じように扱います。</span><span class="sxs-lookup"><span data-stu-id="5528a-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="5528a-157">コメント内で `///` は、API ドキュメントの一部として表示されるテキストは [Markdown](https://daringfireball.net/projects/markdown/syntax)として書式設定され、ドキュメントのさまざまな部分が特別な名前付きヘッダーによって示されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="5528a-158">Markdown では、拡張機能を使用して、 `@"<ref target>"` での操作、関数、およびユーザー定義型の相互参照を Q# 行います。</span><span class="sxs-lookup"><span data-stu-id="5528a-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="5528a-159">`<ref target>`参照先のコードオブジェクトの完全修飾名で置き換えます。</span><span class="sxs-lookup"><span data-stu-id="5528a-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="5528a-160">ドキュメントエンジンによっては、追加の Markdown 拡張機能がサポートされている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5528a-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="5528a-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5528a-161">For example:</span></span>

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

<span data-ttu-id="5528a-162">次の名前は、ドキュメントのコメントヘッダーとして有効です。</span><span class="sxs-lookup"><span data-stu-id="5528a-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="5528a-163">**Summary**: 関数または操作の動作、または型の目的の簡単な概要。</span><span class="sxs-lookup"><span data-stu-id="5528a-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="5528a-164">概要の最初の段落は、ホバー情報に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="5528a-165">プレーンテキストである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5528a-165">It should be plain text.</span></span>
- <span data-ttu-id="5528a-166">**説明**: 関数または操作の動作、または型の目的を説明します。</span><span class="sxs-lookup"><span data-stu-id="5528a-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="5528a-167">概要と説明を一緒に使用すると、関数、操作、または型の生成されたドキュメントファイルが形成されます。</span><span class="sxs-lookup"><span data-stu-id="5528a-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="5528a-168">この説明では、インラインの LaTeX 形式のシンボルおよび式がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5528a-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="5528a-169">**入力**: 操作または関数の入力タプルの説明。</span><span class="sxs-lookup"><span data-stu-id="5528a-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="5528a-170">には、入力タプルの各要素を示す追加の Markdown サブセクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5528a-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="5528a-171">**出力**: 演算または関数によって返される組の説明。</span><span class="sxs-lookup"><span data-stu-id="5528a-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="5528a-172">**型パラメーター**: ジェネリック型パラメーターごとに1つの追加のサブセクションを含む空のセクション。</span><span class="sxs-lookup"><span data-stu-id="5528a-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="5528a-173">**例**: 使用されている操作、関数、または型の短い例。</span><span class="sxs-lookup"><span data-stu-id="5528a-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="5528a-174">**解説**: 操作、関数、または型のいくつかの側面を説明するその他の prose。</span><span class="sxs-lookup"><span data-stu-id="5528a-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="5528a-175">関連する関数、操作、またはユーザー定義型を示す完全修飾名の一覧**も参照してください**。</span><span class="sxs-lookup"><span data-stu-id="5528a-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="5528a-176">**参照**: 文書化された項目の参照および引用の一覧。</span><span class="sxs-lookup"><span data-stu-id="5528a-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5528a-177">次のステップ</span><span class="sxs-lookup"><span data-stu-id="5528a-177">Next steps</span></span>

<span data-ttu-id="5528a-178">の [操作と関数](xref:microsoft.quantum.guide.operationsfunctions) について説明 Q# します。</span><span class="sxs-lookup"><span data-stu-id="5528a-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>