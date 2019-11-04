---
title: 'Q # スタイルガイド |Microsoft Docs'
description: 'Q # スタイルガイド'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: 56455e9d5cd452b8620ee794f40563d1d3040193
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183847"
---
# <a name="q-style-guide"></a><span data-ttu-id="20210-103">Q # スタイルガイド</span><span class="sxs-lookup"><span data-stu-id="20210-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="20210-104">一般的な規則</span><span class="sxs-lookup"><span data-stu-id="20210-104">General Conventions</span></span> ##

<span data-ttu-id="20210-105">このガイドで推奨されている規則は、Q&a で記述されたプログラムやライブラリを読みやすく理解しやすくすることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="20210-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-106">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-106">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-107">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-107">We suggest:</span></span>

- <span data-ttu-id="20210-108">より読みやすくわかりやすいコードをユーザーに提供するために意図的に作成しない限り、規則を無視しないでください。</span><span class="sxs-lookup"><span data-stu-id="20210-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-109">例</span><span class="sxs-lookup"><span data-stu-id="20210-109">Examples</span></span>](#tab/examples)

***

## <a name="naming-conventions"></a><span data-ttu-id="20210-110">名前付け規則</span><span class="sxs-lookup"><span data-stu-id="20210-110">Naming Conventions</span></span> ##

<span data-ttu-id="20210-111">Quantum 開発キットの提供では、quantum 開発者が簡単に読むことができ、驚くほど簡単なプログラムを作成するのに役立つ関数名と操作名に努めています。</span><span class="sxs-lookup"><span data-stu-id="20210-111">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="20210-112">ここで重要なのは、関数、操作、および型の名前を選択するときに、プログラマがクォンタムの概念を表現するために使用する*ボキャブラリ*を確立することです。お客様が選択した内容を明確に伝えることができます。</span><span class="sxs-lookup"><span data-stu-id="20210-112">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="20210-113">これにより、導入された名前が隠すのではなく、明確になるようにする責任があります。</span><span class="sxs-lookup"><span data-stu-id="20210-113">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="20210-114">このセクションでは、Q # 開発コミュニティで最高の機能を実現するための明示的なガイダンスという観点から、この義務を満たす方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="20210-114">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="20210-115">操作と関数</span><span class="sxs-lookup"><span data-stu-id="20210-115">Operations and Functions</span></span> ###

<span data-ttu-id="20210-116">名前によって最初に確立されるものの1つは、特定のシンボルが関数または操作を表すかどうかです。</span><span class="sxs-lookup"><span data-stu-id="20210-116">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="20210-117">関数と演算の違いは、コードブロックの動作を理解するために重要です。</span><span class="sxs-lookup"><span data-stu-id="20210-117">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="20210-118">関数と操作の区別をユーザーに伝えるために、副作用を使用して、その Q&a モデルのクォンタム操作に依存しています。</span><span class="sxs-lookup"><span data-stu-id="20210-118">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="20210-119">つまり、操作は何らかの処理*を行います*。</span><span class="sxs-lookup"><span data-stu-id="20210-119">That is, an operation *does* something.</span></span>

<span data-ttu-id="20210-120">一方、関数は、データ間の数学的な関係を記述します。</span><span class="sxs-lookup"><span data-stu-id="20210-120">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="20210-121">式 `Sin(PI() / 2.0)`*は*`1.0`であり、プログラムの状態またはその qubits を意味するものではありません。</span><span class="sxs-lookup"><span data-stu-id="20210-121">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="20210-122">要約すると、操作は関数を処理するときに処理を行います。</span><span class="sxs-lookup"><span data-stu-id="20210-122">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="20210-123">この区別は、動詞と関数として名詞として名前が付けられることを示しています。</span><span class="sxs-lookup"><span data-stu-id="20210-123">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="20210-124">ユーザー定義型を宣言すると、その型のインスタンスを構築する新しい関数が暗黙的に同時に定義されます。</span><span class="sxs-lookup"><span data-stu-id="20210-124">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="20210-125">その観点からは、ユーザー定義型に名詞という名前を付けて、型自体とコンストラクター関数の名前が一貫している必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-125">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="20210-126">適切であれば、操作の名前は、操作によって行われた効果を明確に示す動詞で始まることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="20210-126">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="20210-127">例えば次が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="20210-127">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="20210-128">特に特別な意味があるケースの1つは、操作が別の操作を入力として受け取り、それを呼び出すときです。</span><span class="sxs-lookup"><span data-stu-id="20210-128">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="20210-129">このような場合、外部操作が定義されているときに、入力操作によって実行されるアクションが明確にはなりません。そのため、右の動詞はすぐにはクリアされません。</span><span class="sxs-lookup"><span data-stu-id="20210-129">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="20210-130">`ApplyIf`、`ApplyToEach`、`ApplyToFirst`のように、動詞 `Apply`をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-130">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="20210-131">この場合、`IterateThroughCartesianPower`のように、他の動詞も便利です。</span><span class="sxs-lookup"><span data-stu-id="20210-131">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="20210-132">動詞</span><span class="sxs-lookup"><span data-stu-id="20210-132">Verb</span></span> | <span data-ttu-id="20210-133">期待される効果</span><span class="sxs-lookup"><span data-stu-id="20210-133">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="20210-134">適用</span><span class="sxs-lookup"><span data-stu-id="20210-134">Apply</span></span> | <span data-ttu-id="20210-135">入力として指定された操作が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="20210-135">An operation provided as input is called</span></span> |
| <span data-ttu-id="20210-136">アサート</span><span class="sxs-lookup"><span data-stu-id="20210-136">Assert</span></span> | <span data-ttu-id="20210-137">シミュレーターによって実行されるクォンタム測定の結果に関する仮説</span><span class="sxs-lookup"><span data-stu-id="20210-137">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="20210-138">見積もり</span><span class="sxs-lookup"><span data-stu-id="20210-138">Estimate</span></span> | <span data-ttu-id="20210-139">1つ以上の測定値からの推定値を表す、古典的な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="20210-139">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="20210-140">計測</span><span class="sxs-lookup"><span data-stu-id="20210-140">Measure</span></span> | <span data-ttu-id="20210-141">クォンタム測定が実行され、その結果がユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="20210-141">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="20210-142">準備</span><span class="sxs-lookup"><span data-stu-id="20210-142">Prepare</span></span> | <span data-ttu-id="20210-143">指定された qubits のレジスタは、特定の状態に初期化されます</span><span class="sxs-lookup"><span data-stu-id="20210-143">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="20210-144">サンプル (英語)</span><span class="sxs-lookup"><span data-stu-id="20210-144">Sample</span></span> | <span data-ttu-id="20210-145">古典的な値は、ある分布からランダムに返されます。</span><span class="sxs-lookup"><span data-stu-id="20210-145">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="20210-146">関数の場合は、一般的な名詞を優先して動詞を使用しないことをお勧めします (以下の適切な名詞に関するガイダンスを参照してください)。または形容詞:</span><span class="sxs-lookup"><span data-stu-id="20210-146">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="20210-147">特に、ほとんどの場合は、必要に応じて過去の participles を使用することをお勧めします。これは、関数名が、クォンタムプログラム内の別の場所にあるアクションや副作用に強い接続されていることを示すためです。</span><span class="sxs-lookup"><span data-stu-id="20210-147">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="20210-148">たとえば、`ControlledOnInt` は動詞 "control" の part 分詞形式を使用して、関数が引数を変更するための形容詞として機能することを示します。</span><span class="sxs-lookup"><span data-stu-id="20210-148">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="20210-149">この名前には、以下で説明するように、組み込みの `Controlled` ファンクタのセマンティクスと照合するという追加の利点があります。</span><span class="sxs-lookup"><span data-stu-id="20210-149">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="20210-150">同様に、_エージェント名詞_を使用して、`Encode`に厳密に関連付けられた UDT の名前 `Encoder` の場合のように、操作名から関数名や UDT 名を作成できます。</span><span class="sxs-lookup"><span data-stu-id="20210-150">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-151">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-151">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-152">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-152">We suggest:</span></span>

- <span data-ttu-id="20210-153">操作名には動詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-153">Use verbs for operation names.</span></span>
- <span data-ttu-id="20210-154">関数名には名詞または形容詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-154">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="20210-155">ユーザー定義型および属性に対して名詞を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-155">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="20210-156">すべての呼び出し可能な名前については、`pascalCase`、`snake_case`、または `ANGRY_CASE`に `CamelCase` を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-156">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="20210-157">特に、呼び出し可能な名前が大文字で始まることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20210-157">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="20210-158">すべてのローカル変数に対して、`CamelCase`、`snake_case`、または `ANGRY_CASE`に `pascalCase` を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-158">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="20210-159">特に、ローカル変数の先頭が小文字であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20210-159">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="20210-160">関数名と操作名にアンダースコア `_` を使用しないようにします。階層の追加レベルが必要な場合は、名前空間と名前空間のエイリアスを使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-160">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-161">例</span><span class="sxs-lookup"><span data-stu-id="20210-161">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="20210-162">EnableAdfsAuthentication</span><span class="sxs-lookup"><span data-stu-id="20210-162">Name</span></span> | <span data-ttu-id="20210-163">description</span><span class="sxs-lookup"><span data-stu-id="20210-163">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="20210-164">☑</span><span class="sxs-lookup"><span data-stu-id="20210-164">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="20210-165">操作の効果を示すには、動詞 ("リフレクト") の使用をクリアします。</span><span class="sxs-lookup"><span data-stu-id="20210-165">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="20210-166">☒</span><span class="sxs-lookup"><span data-stu-id="20210-166">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="20210-167">名詞句の使用は、操作ではなく、関数を提案します。</span><span class="sxs-lookup"><span data-stu-id="20210-167">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="20210-168">☒</span><span class="sxs-lookup"><span data-stu-id="20210-168">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="20210-169">`snake_case` contravenes Q # 表記の使用。</span><span class="sxs-lookup"><span data-stu-id="20210-169">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="20210-170">☒</span><span class="sxs-lookup"><span data-stu-id="20210-170">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="20210-171">操作名の内部でのアンダースコアの使用 contravenes Q # 表記。</span><span class="sxs-lookup"><span data-stu-id="20210-171">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="20210-172">☑</span><span class="sxs-lookup"><span data-stu-id="20210-172">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="20210-173">名詞句を使用すると、関数が操作を返すことがわかります。</span><span class="sxs-lookup"><span data-stu-id="20210-173">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="20210-174">☑</span><span class="sxs-lookup"><span data-stu-id="20210-174">☑</span></span> | `function EqualityFact` | <span data-ttu-id="20210-175">名詞 ("fact") の使用をクリアし、これが関数であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="20210-175">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="20210-176">☒</span><span class="sxs-lookup"><span data-stu-id="20210-176">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="20210-177">動詞 ("get") を使用すると、これが操作であることが提案されます。</span><span class="sxs-lookup"><span data-stu-id="20210-177">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="20210-178">☑</span><span class="sxs-lookup"><span data-stu-id="20210-178">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="20210-179">名詞句の使用は、UDT コンストラクターを呼び出した結果を明確に表します。</span><span class="sxs-lookup"><span data-stu-id="20210-179">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="20210-180">☒</span><span class="sxs-lookup"><span data-stu-id="20210-180">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="20210-181">動詞句を使用すると、UDT コンストラクターが操作であることがわかります。</span><span class="sxs-lookup"><span data-stu-id="20210-181">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="20210-182">☑</span><span class="sxs-lookup"><span data-stu-id="20210-182">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="20210-183">名詞句を使用すると、属性の使用が伝えます。</span><span class="sxs-lookup"><span data-stu-id="20210-183">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="20210-184">ショートハンドと省略形</span><span class="sxs-lookup"><span data-stu-id="20210-184">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="20210-185">上記のアドバイスには、多くの形式があります。これは、クォンタムコンピューティングに共通し、広く使用されています。</span><span class="sxs-lookup"><span data-stu-id="20210-185">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="20210-186">特にターゲットコンピューターの操作に固有の操作については、既存の一般的なショートハンドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-186">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="20210-187">たとえば、`ApplyX`ではなく名前 `X` を選択し、`RotateAboutZ`ではなく `Rz` します。</span><span class="sxs-lookup"><span data-stu-id="20210-187">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="20210-188">この短縮形を使用する場合、操作名はすべて大文字にする必要があります (例: `MAJ`)。</span><span class="sxs-lookup"><span data-stu-id="20210-188">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="20210-189">一般的に使用されている頭字語と頭字語 ("quantum フーリエ変換" など) の場合は、この規則を適用するときに注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="20210-189">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="20210-190">頭字語と頭字語を完全な名前で使用するための一般的な .NET 表記規則に従うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-190">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="20210-191">2文字の頭字語と頭字語は大文字で名前が付けられます (例: "ビッグエンディアン" の場合は `BE`)。</span><span class="sxs-lookup"><span data-stu-id="20210-191">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="20210-192">すべての長い頭字語と頭字語は、`CamelCase` (例: "クォンタムフーリエ変換" の `Qft`) に名前が付けられています。</span><span class="sxs-lookup"><span data-stu-id="20210-192">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="20210-193">このため、QFT を実装する操作は、ショート `QFT` として、または `ApplyQft`として書き出すことができます。</span><span class="sxs-lookup"><span data-stu-id="20210-193">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="20210-194">特に一般的に使用される操作と関数では、より長い形式の_別名_として短縮名を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-194">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-195">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-195">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-196">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-196">We suggest:</span></span>

- <span data-ttu-id="20210-197">必要に応じて、一般的に受け入れられ、広く使用されている短縮形を検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-197">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="20210-198">省略形には大文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-198">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="20210-199">短い (2 文字) 頭字語と頭字語には大文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-199">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="20210-200">`CamelCase` は、頭字語と頭字語を長く (3 文字以上) 使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-200">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-201">例</span><span class="sxs-lookup"><span data-stu-id="20210-201">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="20210-202">EnableAdfsAuthentication</span><span class="sxs-lookup"><span data-stu-id="20210-202">Name</span></span> | <span data-ttu-id="20210-203">description</span><span class="sxs-lookup"><span data-stu-id="20210-203">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="20210-204">☑</span><span class="sxs-lookup"><span data-stu-id="20210-204">☑</span></span> | `X` | <span data-ttu-id="20210-205">「$X $ transformation の適用」の短縮形</span><span class="sxs-lookup"><span data-stu-id="20210-205">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="20210-206">☑</span><span class="sxs-lookup"><span data-stu-id="20210-206">☑</span></span> | `CNOT` | <span data-ttu-id="20210-207">"制御された-NOT" の短縮形</span><span class="sxs-lookup"><span data-stu-id="20210-207">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="20210-208">☒</span><span class="sxs-lookup"><span data-stu-id="20210-208">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="20210-209">短縮形を `CamelCase`にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="20210-209">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="20210-210">☑</span><span class="sxs-lookup"><span data-stu-id="20210-210">☑</span></span> | `ApplyQft` | <span data-ttu-id="20210-211">一般的な initialism "QFT" は、長い形式の名前の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="20210-211">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="20210-212">☑</span><span class="sxs-lookup"><span data-stu-id="20210-212">☑</span></span> | `QFT` | <span data-ttu-id="20210-213">一般的な initialism "QFT" は、短縮名の一部として表示されます。</span><span class="sxs-lookup"><span data-stu-id="20210-213">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="20210-214">名前の正しい名詞</span><span class="sxs-lookup"><span data-stu-id="20210-214">Proper Nouns in Names</span></span> ###

<span data-ttu-id="20210-215">物理的には、最初に発行する人の後に名前が付けられることがよくありますが、ほとんどのまずでは、すべての人の名前とすべての履歴を理解することはできません。</span><span class="sxs-lookup"><span data-stu-id="20210-215">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="20210-216">物理的な名前付け規則に頼ると、その他の背景からのユーザーは一般的な操作と概念を使用するために、一見見えにくい名前の多くを学習する必要があるため、エントリに大きなバリアが生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="20210-216">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="20210-217">このため、概念の発行履歴を記述する適切な名詞に対して、概念を説明する一般的な名詞を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-217">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="20210-218">具体的な例として、1つの制御されていないスワップとダブル制御されていない操作は、教育機関の資料では "Fredkin" および "Toffoli" 操作と呼ばれますが、主に Q # では `CSWAP` と `CCNOT`として識別されます。</span><span class="sxs-lookup"><span data-stu-id="20210-218">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="20210-219">どちらの場合も、API ドキュメントコメントは、適切な名詞に基づいて、適切なすべての引用文と同義の名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="20210-219">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="20210-220">この設定は、適切な名詞の一部の使用が常に必要であるという点で特に重要です。 Q # は、多くの従来の言語で設定されているようになります。また、はブール型のロジックへの参照で `Bool` 型を表します。(ジョージ Boole)</span><span class="sxs-lookup"><span data-stu-id="20210-220">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="20210-221">同様に、いくつかのクォンタムの概念も同様の方法で名前が付けられます。これには、Q # 言語に組み込まれている `Pauli` 型も含まれます。</span><span class="sxs-lookup"><span data-stu-id="20210-221">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="20210-222">適切な名詞の使用を最小限に抑えて、そのような用途が重要ではない場合は、適切な名詞があまり避けられないような影響を軽減します。</span><span class="sxs-lookup"><span data-stu-id="20210-222">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-223">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-223">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="20210-224">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-224">We suggest:</span></span>

- <span data-ttu-id="20210-225">名前には適切な名詞を使用しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="20210-225">Avoid the use of proper nouns in names.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-226">例</span><span class="sxs-lookup"><span data-stu-id="20210-226">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="20210-227">型変換</span><span class="sxs-lookup"><span data-stu-id="20210-227">Type Conversions</span></span> ###

<span data-ttu-id="20210-228">Q # は厳密かつ厳密に型指定された言語であるため、1つの型の値は、型変換関数への明示的な呼び出しを使用して、別の型の値としてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="20210-228">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="20210-229">これは、値が暗黙的に型を変更できるようにする言語 (例: 型の上位変換)、またはキャストを使用した場合とは対照的です。</span><span class="sxs-lookup"><span data-stu-id="20210-229">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="20210-230">その結果、型変換関数は、Q # ライブラリ開発で重要な役割を果たし、名前付けに関してよく発生する決定の1つを構成します。</span><span class="sxs-lookup"><span data-stu-id="20210-230">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="20210-231">ただし、型変換は常に_決定的_であるため、関数として記述することができます。そのため、上記のアドバイスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="20210-231">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="20210-232">具体的には、型変換関数を動詞 (例: `ConvertToX`) または副詞 prepositional フレーズ (`ToX`) として指定しないことをお勧めしますが、変換元と変換先の型を示す形容詞 prepositional 指定語句として名前を付けることをお勧めします (`XAsY`)。</span><span class="sxs-lookup"><span data-stu-id="20210-232">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="20210-233">型変換関数の名前で配列の型を一覧表示する場合は、短縮 `Arr`をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-233">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="20210-234">例外的な状況を発生させないように、すべての型変換関数には `As` を使用して名前を付け、迅速に識別できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-234">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-235">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-235">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-236">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-236">We suggest:</span></span>

- <span data-ttu-id="20210-237">関数が `X` 型の値を `Y`型の値に変換する場合は、`AsY` または `XAsY`のいずれかの名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-237">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-238">例</span><span class="sxs-lookup"><span data-stu-id="20210-238">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="20210-239">EnableAdfsAuthentication</span><span class="sxs-lookup"><span data-stu-id="20210-239">Name</span></span> | <span data-ttu-id="20210-240">description</span><span class="sxs-lookup"><span data-stu-id="20210-240">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="20210-241">☒</span><span class="sxs-lookup"><span data-stu-id="20210-241">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="20210-242">前置詞 "to" は、関数ではなく操作を示す動詞句を生成します。</span><span class="sxs-lookup"><span data-stu-id="20210-242">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="20210-243">☒</span><span class="sxs-lookup"><span data-stu-id="20210-243">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="20210-244">入力の型は、関数名からは明確ではありません。</span><span class="sxs-lookup"><span data-stu-id="20210-244">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="20210-245">☒</span><span class="sxs-lookup"><span data-stu-id="20210-245">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="20210-246">入力と出力の型が間違った順序で表示されています。</span><span class="sxs-lookup"><span data-stu-id="20210-246">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="20210-247">☑</span><span class="sxs-lookup"><span data-stu-id="20210-247">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="20210-248">入力型と出力型はどちらも明確です。</span><span class="sxs-lookup"><span data-stu-id="20210-248">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="20210-249">プライベートまたは内部名</span><span class="sxs-lookup"><span data-stu-id="20210-249">Private or Internal Names</span></span> ###

<span data-ttu-id="20210-250">多くの場合、名前はライブラリまたはプロジェクトの内部での使用を目的としたものであり、ライブラリによって提供される API の保証された部分ではありません。</span><span class="sxs-lookup"><span data-stu-id="20210-250">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="20210-251">関数や操作に名前を付けて、内部のみのコードに誤った依存関係が明らかになるようにする場合は、このことを明確に示すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-251">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="20210-252">操作または関数が直接使用するためのものではなく、部分的なアプリケーションによって動作する一致する呼び出し元によって使用される必要がある場合は、部分的に適用される呼び出し可能な `_` で始まる名前を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-252">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with `_` for the callable that is partially applied.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-253">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-253">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-254">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-254">We suggest:</span></span>

- <span data-ttu-id="20210-255">関数、操作、またはユーザー定義型が Q # ライブラリまたはプログラムのパブリック API の一部ではない場合は、その名前が先頭のアンダースコア (`_`) で始まることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20210-255">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that its name begins with a leading underscore (`_`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-256">例</span><span class="sxs-lookup"><span data-stu-id="20210-256">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="20210-257">EnableAdfsAuthentication</span><span class="sxs-lookup"><span data-stu-id="20210-257">Name</span></span> | <span data-ttu-id="20210-258">description</span><span class="sxs-lookup"><span data-stu-id="20210-258">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="20210-259">☒</span><span class="sxs-lookup"><span data-stu-id="20210-259">☒</span></span> | <s>`ApplyDecomposedOperation_`</s> | <span data-ttu-id="20210-260">アンダースコア `_` は、名前の末尾には記述できません。</span><span class="sxs-lookup"><span data-stu-id="20210-260">The underscore `_` should not appear at the end of the name.</span></span> |
| <span data-ttu-id="20210-261">☑</span><span class="sxs-lookup"><span data-stu-id="20210-261">☑</span></span> | `_ApplyDecomposedOperation` | <span data-ttu-id="20210-262">先頭にあるアンダースコア `_` は、この操作が内部でのみ使用されることを明確に示しています。</span><span class="sxs-lookup"><span data-stu-id="20210-262">The underscore `_` at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***

### <a name="variants"></a><span data-ttu-id="20210-263">△</span><span class="sxs-lookup"><span data-stu-id="20210-263">Variants</span></span> ###

<span data-ttu-id="20210-264">この制限は、Q # の将来のバージョンでは保持されない場合がありますが、現在のところ、関連する操作のグループ、またはその入力がサポートしている機能や、引数の具象型によって区別される関数のグループが存在することがあります。</span><span class="sxs-lookup"><span data-stu-id="20210-264">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="20210-265">これらのグループは、同じルート名を使用し、そのバリアントを示す 1 ~ 2 文字で区別できます。</span><span class="sxs-lookup"><span data-stu-id="20210-265">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="20210-266">サフィックス</span><span class="sxs-lookup"><span data-stu-id="20210-266">Suffix</span></span> | <span data-ttu-id="20210-267">意味</span><span class="sxs-lookup"><span data-stu-id="20210-267">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="20210-268">`Adjoint` をサポートするために必要な入力</span><span class="sxs-lookup"><span data-stu-id="20210-268">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="20210-269">`Controlled` をサポートするために必要な入力</span><span class="sxs-lookup"><span data-stu-id="20210-269">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="20210-270">`Controlled` と `Adjoint` をサポートするために必要な入力</span><span class="sxs-lookup"><span data-stu-id="20210-270">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="20210-271">入力または入力の型が `Int`</span><span class="sxs-lookup"><span data-stu-id="20210-271">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="20210-272">入力または入力の型が `Double`</span><span class="sxs-lookup"><span data-stu-id="20210-272">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="20210-273">入力または入力の型が `BigInt`</span><span class="sxs-lookup"><span data-stu-id="20210-273">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-274">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-274">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-275">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-275">We suggest:</span></span>

- <span data-ttu-id="20210-276">関数または演算が、入力の型およびファンクタのサポートによって類似の関数や操作に関連付けられていない場合は、サフィックスを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="20210-276">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="20210-277">関数または演算が、入力の型およびファンクタのサポートによって類似の関数または演算に関連付けられている場合は、上記の表のようにサフィックスを使用して、バリアントを区別します。</span><span class="sxs-lookup"><span data-stu-id="20210-277">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-278">例</span><span class="sxs-lookup"><span data-stu-id="20210-278">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="20210-279">引数と変数</span><span class="sxs-lookup"><span data-stu-id="20210-279">Arguments and Variables</span></span> ###

<span data-ttu-id="20210-280">関数または操作の Q # コードの主な目的は、簡単に読み取り、理解できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="20210-280">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="20210-281">同様に、入力と型引数の名前は、指定された関数または引数の使用方法を伝達する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-281">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-282">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-282">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-283">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-283">We suggest:</span></span>

- <span data-ttu-id="20210-284">すべての変数と入力の名前については、`CamelCase`、`snake_case`、または `ANGRY_CASE`に `pascalCase` を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-284">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="20210-285">入力名はわかりやすい名前にする必要があります。可能な限り、1文字または2文字の名前は避けてください。</span><span class="sxs-lookup"><span data-stu-id="20210-285">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="20210-286">型引数を1つだけ受け取る演算と関数は、そのロールが明確である場合に `T` によってその型引数を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-286">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="20210-287">関数または操作が複数の型引数を受け取る場合、または1つの型引数の役割が明確でない場合は、型ごとに `T` で始まる短い大文字の単語 (例: `TOutput`) を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-287">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="20210-288">引数と変数名に型名を含めないでください。この情報は、開発環境によって提供されることがあります。</span><span class="sxs-lookup"><span data-stu-id="20210-288">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="20210-289">スカラー型をリテラル名 (`flagQubit`) で表し、配列型を複数形 (`measResults`) で表します。</span><span class="sxs-lookup"><span data-stu-id="20210-289">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="20210-290">特に qubits の配列の場合は、何らかの方法で密接に関連付けられている qubits のシーケンスを名前が参照する `Register` によって、このような型を指定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-290">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="20210-291">配列へのインデックスとして使用される変数は `idx` で始まり、単数形にする必要があります (例: `things[idxThing]`)。</span><span class="sxs-lookup"><span data-stu-id="20210-291">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="20210-292">特に、1文字の変数名をインデックスとして使用するのは避けてください。少なくとも `idx` を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-292">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="20210-293">配列の長さを保持するために使用される変数は `n` で始まる必要があります (例: `nThings`)。</span><span class="sxs-lookup"><span data-stu-id="20210-293">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-294">例</span><span class="sxs-lookup"><span data-stu-id="20210-294">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="20210-295">ユーザー定義型の名前付き項目</span><span class="sxs-lookup"><span data-stu-id="20210-295">User Defined Type Named Items</span></span> ###

<span data-ttu-id="20210-296">ユーザー定義型の名前付き項目には、UDT コンストラクターへの入力でも `CamelCase`として名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-296">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="20210-297">これは、アクセサー表記 (例: `callable::Apply`) やコピーと更新の表記 (`set arr w/= Data <- newData`) を使用する場合に、名前付き項目をローカルスコープ変数への参照から明確に分離するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20210-297">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-298">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-298">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-299">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-299">We suggest:</span></span>

- <span data-ttu-id="20210-300">UDT コンストラクターの名前付き項目には、`CamelCase`という名前を付ける必要があります。つまり、先頭は大文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-300">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="20210-301">操作に解決される名前付き項目は、動詞フェーズとして名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-301">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="20210-302">操作に解決されない名前付きの項目には、名詞句として名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-302">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="20210-303">操作をラップする Udt の場合は、`Apply` という名前の単一の項目を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-303">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-304">例</span><span class="sxs-lookup"><span data-stu-id="20210-304">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="20210-305">短い</span><span class="sxs-lookup"><span data-stu-id="20210-305">Snippet</span></span> | <span data-ttu-id="20210-306">description</span><span class="sxs-lookup"><span data-stu-id="20210-306">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="20210-307">☑</span><span class="sxs-lookup"><span data-stu-id="20210-307">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="20210-308">名前 `Apply` は、名前付きの項目が操作であることを示す、`CamelCase`形式の動詞の語句です。</span><span class="sxs-lookup"><span data-stu-id="20210-308">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="20210-309">☒</span><span class="sxs-lookup"><span data-stu-id="20210-309">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="20210-310">名前付き項目の先頭は大文字である必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-310">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="20210-311">☒</span><span class="sxs-lookup"><span data-stu-id="20210-311">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="20210-312">関数に解決される名前付きの項目は、動詞句としてではなく、名詞句として名前を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-312">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="20210-313">入力規則</span><span class="sxs-lookup"><span data-stu-id="20210-313">Input Conventions</span></span> ##

<span data-ttu-id="20210-314">開発者が操作または関数を呼び出すときは、その操作または関数に対するさまざまな入力を特定の順序で指定する必要があります。これにより、開発者がライブラリを利用するために直面する認識負荷を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="20210-314">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="20210-315">具体的には、多くの場合、入力順序を記憶するタスクは、「クォンタムアルゴリズムの実装のプログラミング」の作業には煩わされません。</span><span class="sxs-lookup"><span data-stu-id="20210-315">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="20210-316">豊富な IDE サポートではこれを大きな範囲に抑えることができますが、一般的な規則の設計と準拠が優れているため、API による認識の負荷を最小限に抑えることもできます。</span><span class="sxs-lookup"><span data-stu-id="20210-316">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="20210-317">可能な場合は、操作または関数によって期待される入力の数を減らすことが役に立つことがあります。これにより、各入力のロールが、その操作や関数を呼び出す開発者と、後でそのコードを読み取っている開発者の両方にとってより明確になります。</span><span class="sxs-lookup"><span data-stu-id="20210-317">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="20210-318">特に、操作または関数の引数の数を減らすことができない場合、または適切でない場合は、入力の順序を予測するときにユーザーが直面する驚きを最小限にするために、一貫した順序を付けることが重要です。</span><span class="sxs-lookup"><span data-stu-id="20210-318">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="20210-319">カリー化 f (x, y) ≡ f (x) (y) の汎化として部分的なアプリケーションを考えることから、多くの場合、入力の順序付け規則をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-319">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="20210-320">したがって、最初の引数を部分的に適用すると、適切な場合は常に独自の権限を持つ呼び出し可能になります。</span><span class="sxs-lookup"><span data-stu-id="20210-320">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="20210-321">この原則に従うと、次の引数の順序を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-321">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="20210-322">角度、累乗のベクトルなど、従来の呼び出し不可能な引数。</span><span class="sxs-lookup"><span data-stu-id="20210-322">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="20210-323">呼び出し可能な引数 (関数と引数)。</span><span class="sxs-lookup"><span data-stu-id="20210-323">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="20210-324">関数と演算の両方を引数として使用する場合は、関数の後に操作を配置することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="20210-324">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="20210-325">呼び出し可能な引数によって処理されるコレクションは、`Map`、`Iter`、`Enumerate`、および `Fold`の場合と同様の方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="20210-325">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="20210-326">コントロールとして使用される qubit 引数。</span><span class="sxs-lookup"><span data-stu-id="20210-326">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="20210-327">ターゲットとして使用される qubit 引数。</span><span class="sxs-lookup"><span data-stu-id="20210-327">Qubit arguments used as targets.</span></span>

<span data-ttu-id="20210-328">操作 `ApplyPhaseEstimationIteration` を検討してください。これは、角度と oracle を使用するフェーズ推定で使用し、さまざまなスケールファクターの配列によって変更された `Rz` に角度を渡して、oracle のアプリケーションを制御します。</span><span class="sxs-lookup"><span data-stu-id="20210-328">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="20210-329">次のように、入力を `ApplyPhaseEstimationIteration` に順序付けます。</span><span class="sxs-lookup"><span data-stu-id="20210-329">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="20210-330">意外なことを最小限に抑えるための特別なケースとして、一部の関数と操作は、`Adjoint` 組み込みの関数と `Controlled`の動作を模倣しています。</span><span class="sxs-lookup"><span data-stu-id="20210-330">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="20210-331">たとえば、`ControlledOnInt<'T>` の型が `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`の場合、`ControlledOnInt<Qubit[]>(5, _)` は `Controlled` のファンクタと同じように動作しますが、コントロールレジスタが state $ \ket{5} = \ket{101}$ を表しているという条件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="20210-331">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="20210-332">したがって、開発者は、呼び出し可能なが最後に変換されるように `ControlledOnInt` 入力を要求し、結果として得られる操作は、`Controlled` のファンクタの出力の後に入力 `(Qubit[], 'T)` と同じ順序で---する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-332">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-333">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-333">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-334">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-334">We suggest:</span></span>

- <span data-ttu-id="20210-335">部分アプリケーションの使用と一貫性のある入力順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-335">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="20210-336">組み込みのファンクターと一貫性のある入力順序を使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-336">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="20210-337">すべての古典入力をクォンタム入力の前に配置します。</span><span class="sxs-lookup"><span data-stu-id="20210-337">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-338">例</span><span class="sxs-lookup"><span data-stu-id="20210-338">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="20210-339">ドキュメントの表記規則</span><span class="sxs-lookup"><span data-stu-id="20210-339">Documentation Conventions</span></span> ##

<span data-ttu-id="20210-340">Q # 言語では、特別に書式設定されたドキュメントコメントを使用して、操作、関数、およびユーザー定義型にドキュメントを添付できます。</span><span class="sxs-lookup"><span data-stu-id="20210-340">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="20210-341">これらのドキュメントコメントは、3つのスラッシュ (`///`) で表され、各操作、関数、およびユーザー定義型の目的、それぞれに必要な入力、およびなどを記述するために使用できる小さな[Docfx-Flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="20210-341">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="20210-342">Quantum Development Kit に用意されているコンパイラは、これらのコメントを抽出し、それらのコメントを使用して、 https://docs.microsoft.com/quantum 時と同様の横組みドキュメントを作成します。</span><span class="sxs-lookup"><span data-stu-id="20210-342">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="20210-343">同様に、Quantum 開発キットで提供されている言語サーバーは、これらのコメントを使用して、ユーザーが Q # コード内のシンボルにマウスポインターを置いたときにヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="20210-343">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="20210-344">ドキュメントコメントを使用すると、このドキュメントの他の規則を使用して簡単には表現できない詳細情報を提供することで、ユーザーがコードを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20210-344">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="20210-345">
    [ドキュメントコメント構文のリファレンス](xref:microsoft.quantum.language.statements#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="20210-345">
    [Documentation comment syntax reference](xref:microsoft.quantum.language.statements#documentation-comments)
</span></span></div>

<span data-ttu-id="20210-346">この機能を効果的に使用してユーザーを支援するには、ドキュメントコメントを記述する際に注意することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-346">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-347">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-347">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="20210-348">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-348">We suggest:</span></span>

- <span data-ttu-id="20210-349">各パブリック関数、操作、およびユーザー定義型は、ドキュメントコメントの直前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-349">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="20210-350">各ドキュメントコメントには、少なくとも次のセクションが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-350">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="20210-351">Summary</span><span class="sxs-lookup"><span data-stu-id="20210-351">Summary</span></span>
    - <span data-ttu-id="20210-352">Input (入力)</span><span class="sxs-lookup"><span data-stu-id="20210-352">Input</span></span>
    - <span data-ttu-id="20210-353">出力 (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="20210-353">Output (if applicable)</span></span>
- <span data-ttu-id="20210-354">すべての概要が2文以下であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="20210-354">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="20210-355">より多くの領域が必要な場合は、`# Summary` の直後に `# Description` のセクションを入力します。詳細については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20210-355">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="20210-356">すべてのクライアントが概要で TeX 表記をサポートするわけではないため、適切な場合は、集計に数値を含めないでください。</span><span class="sxs-lookup"><span data-stu-id="20210-356">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="20210-357">Prose ドキュメント (TeX や Markdown など) を書き込む場合は、長い行の長さを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-357">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="20210-358">`# Description` セクションで、関連するすべての数値式を指定します。</span><span class="sxs-lookup"><span data-stu-id="20210-358">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="20210-359">入力を記述するときは、コンパイラによって推論される可能性があるため、各入力の型を繰り返さないでください。</span><span class="sxs-lookup"><span data-stu-id="20210-359">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="20210-360">必要に応じて、それぞれ独自の `# Example` セクションに例を入力します。</span><span class="sxs-lookup"><span data-stu-id="20210-360">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="20210-361">コードを一覧表示する前に、各例を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="20210-361">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="20210-362">関連するすべての教育機関向けの出版物 (例: 論文、手続き、ブログ投稿、および代替の実装) については、リンクの箇条書きリストとして、`# References` セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="20210-362">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="20210-363">可能であれば、すべての引用リンクが永続的で不変の識別子になるようにしてください (DOIs またはバージョン管理された arXiv の番号)。</span><span class="sxs-lookup"><span data-stu-id="20210-363">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="20210-364">演算または関数が、ファンクタバリアントによって他の操作や関数に関連付けられている場合は、[`# See Also`] セクションで他のバリアントを箇条書きとして一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="20210-364">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="20210-365">レベル 1 (`/// #`) のセクション間に空白のコメント行を残しておきますが、レベル 2 (`/// ##`) のセクションの間に空白行を入れないでください。</span><span class="sxs-lookup"><span data-stu-id="20210-365">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-366">例</span><span class="sxs-lookup"><span data-stu-id="20210-366">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="20210-367">☑</span><span class="sxs-lookup"><span data-stu-id="20210-367">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="20210-368">書式設定の規則</span><span class="sxs-lookup"><span data-stu-id="20210-368">Formatting Conventions</span></span> ##

<span data-ttu-id="20210-369">前述の提案に加えて、一貫性のある書式設定規則を使用するためにコードをできるだけ読みやすくするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="20210-369">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="20210-370">このような書式設定規則は、本質的にはやや自由で、個人的には見栄えがよくなります。</span><span class="sxs-lookup"><span data-stu-id="20210-370">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="20210-371">それでも、コラボレーターのグループ内では一貫した書式指定規則を維持することをお勧めします。また、Quantum 開発キット自体などの大規模な Q # プロジェクトの場合は特にそうです。</span><span class="sxs-lookup"><span data-stu-id="20210-371">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="20210-372">これらの規則は、Q # コンパイラと統合された書式設定ツールを使用して自動的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="20210-372">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidancetabguidance"></a>[<span data-ttu-id="20210-373">ガイダンス</span><span class="sxs-lookup"><span data-stu-id="20210-373">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="20210-374">次のことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20210-374">We suggest:</span></span>

- <span data-ttu-id="20210-375">移植性を確保するには、タブの代わりに4つのスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-375">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="20210-376">たとえば、VS Code では次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20210-376">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="20210-377">79文字の行が適切な位置に折り返されます。</span><span class="sxs-lookup"><span data-stu-id="20210-377">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="20210-378">バイナリ演算子の前後にスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-378">Use spaces around binary operators.</span></span>
- <span data-ttu-id="20210-379">型の注釈に使用されるコロンの両側でスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-379">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="20210-380">配列と組リテラルで使用するコンマの後に1つのスペースを使用します (例: 関数と操作への入力で)。</span><span class="sxs-lookup"><span data-stu-id="20210-380">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="20210-381">関数、操作、または UDT の名前の後、または属性宣言の `@` 後にスペースを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="20210-381">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="20210-382">各属性の宣言は、独自の行に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20210-382">Each attribute declaration should be on its own line.</span></span>

# <a name="examplestabexamples"></a>[<span data-ttu-id="20210-383">例</span><span class="sxs-lookup"><span data-stu-id="20210-383">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="20210-384">短い</span><span class="sxs-lookup"><span data-stu-id="20210-384">Snippet</span></span> | <span data-ttu-id="20210-385">description</span><span class="sxs-lookup"><span data-stu-id="20210-385">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="20210-386">☒</span><span class="sxs-lookup"><span data-stu-id="20210-386">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="20210-387">バイナリ演算子の前後にスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-387">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="20210-388">☒</span><span class="sxs-lookup"><span data-stu-id="20210-388">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="20210-389">注釈のコロンを囲むにはスペースを使用します。</span><span class="sxs-lookup"><span data-stu-id="20210-389">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="20210-390">☑</span><span class="sxs-lookup"><span data-stu-id="20210-390">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="20210-391">入力タプル内の項目は、読みやすくするために適切に配置されています。</span><span class="sxs-lookup"><span data-stu-id="20210-391">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="20210-392">☒</span><span class="sxs-lookup"><span data-stu-id="20210-392">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="20210-393">関数、操作、または UDT の名前の後にスペースは表示されません。</span><span class="sxs-lookup"><span data-stu-id="20210-393">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***

