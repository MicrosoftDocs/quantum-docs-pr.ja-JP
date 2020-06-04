---
title: 'Q # ファイル構造'
description: 'Q # ファイルの構造と構文について説明します。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327460"
---
# <a name="q-file-structure"></a><span data-ttu-id="74e6f-103">Q # ファイル構造</span><span class="sxs-lookup"><span data-stu-id="74e6f-103">Q# File Structure</span></span>

<span data-ttu-id="74e6f-104">すべての Q # 操作、関数、およびユーザー定義型は、名前空間内で定義されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="74e6f-105">Q # ファイルは、一連の*名前空間宣言*で構成されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="74e6f-106">各名前空間の宣言には、ユーザー定義型、操作、および関数の宣言が含まれています。</span><span class="sxs-lookup"><span data-stu-id="74e6f-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="74e6f-107">名前空間宣言には、任意の数の宣言を任意の順序で含めることができます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="74e6f-108">名前空間内の[ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)、[操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)、および[関数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)の宣言の詳細については、次のリンク先を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74e6f-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="74e6f-109">名前空間の宣言の外側に表示されるテキストは、コメントだけです。</span><span class="sxs-lookup"><span data-stu-id="74e6f-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="74e6f-110">特に、名前空間については、宣言の前にドキュメントコメント (下の詳細) を記述します。</span><span class="sxs-lookup"><span data-stu-id="74e6f-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="74e6f-111">名前空間の宣言</span><span class="sxs-lookup"><span data-stu-id="74e6f-111">Namespace Declarations</span></span>

<span data-ttu-id="74e6f-112">Q # ファイルには、通常、名前空間宣言が1つだけ含まれますが、(空またはコメントを含む) は使用できません。また、複数の名前空間を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="74e6f-113">名前空間宣言を入れ子にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="74e6f-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="74e6f-114">同じ名前の型、操作、または関数の宣言がない限り、同じ名前空間を複数の Q # ファイルで宣言することができます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="74e6f-115">特に、宣言が同一であっても、複数のファイルの同じ名前空間で同じ型を定義することは無効です。</span><span class="sxs-lookup"><span data-stu-id="74e6f-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="74e6f-116">名前空間宣言は、キーワード、名前 `namespace` 空間の名前、始めかっこ `{` 、名前空間に含まれる宣言、および終わりかっこで構成され `}` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="74e6f-117">名前空間名は、ピリオドで区切られた1つまたは複数の有効な記号のシーケンスの .NET パターンに従い `.` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="74e6f-118">たとえば、 `MyQuantumStuff` と `Microsoft.Quantum.Intrinsic` は有効な名前空間名です。</span><span class="sxs-lookup"><span data-stu-id="74e6f-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="74e6f-119">慣例により、名前空間名に含まれる記号は大文字になりますが、これは必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="74e6f-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="74e6f-120">ファイル内でさらに下に宣言されている型または呼び出し方向への参照は、適切に解決されます。型、操作、または関数の宣言を参照の前に記述する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74e6f-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="74e6f-121">オープンディレクティブ</span><span class="sxs-lookup"><span data-stu-id="74e6f-121">Open Directives</span></span>

<span data-ttu-id="74e6f-122">名前空間ブロック内では、ディレクティブを使用して、 `open` 特定の名前空間で宣言されたすべての型と呼び出し可能な型をインポートし、非修飾名で参照することができます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="74e6f-123">このようなディレクティブは、キーワードと、 `open` `open` その後に開く名前空間、および終端のセミコロンで構成されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="74e6f-124">すべて `open` のディレクティブは `function` 、 `operation` `newtype` 名前空間ブロック内の、、または宣言の前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e6f-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="74e6f-125">必要に応じて、名前空間のすべての要素が定義された短い名前によって修飾されるように、開いている名前空間の短い名前を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="74e6f-126">たとえば、次の名前空間宣言とオープンディレクティブがあるとします。</span><span class="sxs-lookup"><span data-stu-id="74e6f-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="74e6f-127">宣言する操作でからの操作が使用されている場合は `Op` `Microsoft.Quantum.Intrinsic` 、単にを使用してそれを呼び出し `Op` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="74e6f-128">ただし、から特定の関数を呼び出したい場合は、 `Fn` `Microsoft.Quantum.Math` を使用して呼び出す必要があり `Math.Fn` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="74e6f-129">ディレクティブは、 `open` ファイル内の名前空間ブロック全体に適用されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="74e6f-130">このため、上記と同じ Q # ファイルに追加の名前空間を定義した場合、 `NS` 2 番目の名前空間で定義されているすべての操作/関数/型は、開いているディレクティブを繰り返していない限り、またはにアクセスできません `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 。</span><span class="sxs-lookup"><span data-stu-id="74e6f-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="74e6f-131">現在の名前空間で開かれて*いない*別の名前空間で定義されている型または呼び出し可能が、完全修飾名で参照されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e6f-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="74e6f-132">たとえば、現在のブロックで名前空間が既に開かれている場合を除き、名前空間からのという名前の操作は、 `Op` `X.Y` 完全修飾名によって参照される必要があり `X.Y.Op` `X.Y` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="74e6f-133">前述のように、名前空間が開かれている場合でも、 `X` として操作を参照することはできません `Y.Op` 。</span><span class="sxs-lookup"><span data-stu-id="74e6f-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="74e6f-134">の短い名前 `Z` `X.Y` がその名前空間とファイルで定義されている場合は、を `Op` として参照する必要があり `Z.Op` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="74e6f-135">通常は、ディレクティブを使用して名前空間を含めることをお勧め `open` します。</span><span class="sxs-lookup"><span data-stu-id="74e6f-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="74e6f-136">2つの名前空間で同じ名前の構造体を定義し、現在のソースが両方のコンストラクトを使用する場合は、完全修飾名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e6f-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="74e6f-137">Q # は、他の .NET 言語として名前を付ける場合と同じ規則に従います。</span><span class="sxs-lookup"><span data-stu-id="74e6f-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="74e6f-138">ただし、Q # では名前空間への相対参照はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="74e6f-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="74e6f-139">つまり、名前空間が開かれている場合、という名前の操作への参照は、 `a.b` `c.d` 完全名を持つ操作に対して解決され*ません* `a.b.c.d` 。</span><span class="sxs-lookup"><span data-stu-id="74e6f-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="74e6f-140">書式設定</span><span class="sxs-lookup"><span data-stu-id="74e6f-140">Formatting</span></span>

<span data-ttu-id="74e6f-141">ほとんどの Q # ステートメントとディレクティブは、終端のセミコロンで終わり `;` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="74e6f-142">`for` `operation` ステートメントブロック (下記参照) で終わるやなどのステートメントと宣言では、末尾にセミコロンを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="74e6f-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="74e6f-143">各ステートメントの説明には、終端のセミコロンが必要かどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="74e6f-144">ステートメント (式、宣言、ディレクティブなど) は、複数の行にわたって分割される場合があります。</span><span class="sxs-lookup"><span data-stu-id="74e6f-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="74e6f-145">1行に複数のステートメントを記述することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="74e6f-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="74e6f-146">ステートメントブロック</span><span class="sxs-lookup"><span data-stu-id="74e6f-146">Statement Blocks</span></span>

<span data-ttu-id="74e6f-147">Q # ステートメントは、ステートメントブロックにグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="74e6f-148">ステートメントブロックは、開始位置で始まり、 `{` 終わりで終わり `}` ます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="74e6f-149">別のブロック内で構文的に囲まれたステートメントブロックは、それを含むブロックのサブブロックと見なされます。コンテナーとサブブロックは、外部ブロックと内部ブロックとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="74e6f-150">コメント</span><span class="sxs-lookup"><span data-stu-id="74e6f-150">Comments</span></span>

<span data-ttu-id="74e6f-151">コメントは、2つのスラッシュ (,) で始まり、 `//` 行の終わりまで続きます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="74e6f-152">Q # ソースファイル内の任意の場所にコメントが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="74e6f-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="74e6f-153">ドキュメント コメント</span><span class="sxs-lookup"><span data-stu-id="74e6f-153">Documentation Comments</span></span>

<span data-ttu-id="74e6f-154">3つのスラッシュで始まるコメント `///` は、名前空間、操作、特殊化、関数、または型定義の直前に出現するときに、コンパイラによって特別に処理されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="74e6f-155">その場合、その内容は、他の .NET 言語と同様に、定義された呼び出し可能またはユーザー定義型のドキュメントとして取得されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="74e6f-156">コメント内で `///` は、API ドキュメントの一部として表示されるテキストは[Markdown](https://daringfireball.net/projects/markdown/syntax)として書式設定され、ドキュメントのさまざまな部分が特別な名前のヘッダーによって示されています。</span><span class="sxs-lookup"><span data-stu-id="74e6f-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="74e6f-157">Markdown の拡張機能として、Q # の操作、関数、ユーザー定義型への相互参照は、を使用して含めることができます `@"<ref target>"` 。ここで、 `<ref target>` は参照されるコードオブジェクトの完全修飾名に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="74e6f-158">必要に応じて、ドキュメントエンジンで追加の Markdown 拡張機能をサポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="74e6f-159">例:</span><span class="sxs-lookup"><span data-stu-id="74e6f-159">For example:</span></span>

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

<span data-ttu-id="74e6f-160">次の名前は、ドキュメントのコメントヘッダーとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="74e6f-161">**Summary**: 関数または操作の動作、または型の目的の簡単な概要。</span><span class="sxs-lookup"><span data-stu-id="74e6f-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="74e6f-162">概要の最初の段落は、ホバー情報に使用されます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="74e6f-163">プレーンテキストである必要があります。</span><span class="sxs-lookup"><span data-stu-id="74e6f-163">It should be plain text.</span></span>
- <span data-ttu-id="74e6f-164">**説明**: 関数または操作の動作、または型の目的の説明。</span><span class="sxs-lookup"><span data-stu-id="74e6f-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="74e6f-165">概要と説明を連結して、関数、操作、または型の生成されたドキュメントファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="74e6f-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="74e6f-166">説明には、インラインの LaTeX 形式のシンボルと式を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="74e6f-167">**入力**: 操作または関数の入力タプルの説明。</span><span class="sxs-lookup"><span data-stu-id="74e6f-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="74e6f-168">入力タプルの各要素を示す追加の Markdown サブセクションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="74e6f-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="74e6f-169">**出力**: 演算または関数によって返される組の説明。</span><span class="sxs-lookup"><span data-stu-id="74e6f-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="74e6f-170">**型パラメーター**: ジェネリック型パラメーターごとに1つの追加のサブセクションを含む空のセクション。</span><span class="sxs-lookup"><span data-stu-id="74e6f-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="74e6f-171">**例**: 使用されている操作、関数、または型の簡単な例。</span><span class="sxs-lookup"><span data-stu-id="74e6f-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="74e6f-172">**解説**: 操作、関数、または型のいくつかの側面を説明するその他の prose。</span><span class="sxs-lookup"><span data-stu-id="74e6f-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="74e6f-173">関連する関数、操作、またはユーザー定義型を示す完全修飾名の一覧**も参照してください**。</span><span class="sxs-lookup"><span data-stu-id="74e6f-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="74e6f-174">**参照**: ドキュメント化されている項目の参照および引用の一覧。</span><span class="sxs-lookup"><span data-stu-id="74e6f-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74e6f-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="74e6f-175">Next steps</span></span>

<span data-ttu-id="74e6f-176">Q # の[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)について説明します。</span><span class="sxs-lookup"><span data-stu-id="74e6f-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>