---
title: 貢献資料 |Microsoft Docs
description: ドキュメントの投稿
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
ms.openlocfilehash: 1e24dd859c0b75a161f4f3c7151e2eec227075a2
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183677"
---
# <a name="improving-documentation"></a><span data-ttu-id="43284-103">ドキュメントの改善</span><span class="sxs-lookup"><span data-stu-id="43284-103">Improving Documentation</span></span> #

<span data-ttu-id="43284-104">Quantum 開発キットのドキュメントでは、さまざまな形式を採用しています。これは、クォンタム開発者が情報をすぐに利用できるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="43284-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="43284-105">[コードとしてのドキュメント](https://www.writethedocs.org/guide/docs-as-code/)の原則に従うと、すべての Quantum 開発キットのドキュメントはコードとして書式設定され、Quantum 開発キットの構築に使用されるソースコードと同じ方法で Git を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="43284-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="43284-106">ほとんどの場合、コードのバッキングドキュメントは、さまざまな形式の[Markdown](https://daringfireball.net/projects/markdown/)で構成されています。これは、高度な書式が設定されたテキストを、コマンドライン、ide、ソース管理で簡単に使用できるプレーンテキスト形式で記述するための言語です。</span><span class="sxs-lookup"><span data-stu-id="43284-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="43284-107">同様に、以下で詳しく説明するように、 [MathJax](https://www.mathjax.org/)ライブラリを使用して、LaTeX 言語を使用したドキュメントの数値演算を可能にします。</span><span class="sxs-lookup"><span data-stu-id="43284-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="43284-108">ただし、ドキュメントの各形式は、詳細によって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="43284-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="43284-109">**概念説明のドキュメント**は、 https://docs.microsoft.com/quantum に公開されている一連の記事で構成されています。このドキュメントでは、クォンタムコンピューティングの基礎から、インターチェンジ形式の技術仕様までのすべてを説明しています。</span><span class="sxs-lookup"><span data-stu-id="43284-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="43284-110">これらの記事は[Docfx-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)で記述されています。これは、豊富なドキュメントセットの作成に使用される Markdown バリアントです。</span><span class="sxs-lookup"><span data-stu-id="43284-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="43284-111">**API リファレンス**は、各 Q # 関数、操作、およびユーザー定義型のページのセットであり、 https://docs.microsoft.com/qsharp/api/ に発行されます。</span><span class="sxs-lookup"><span data-stu-id="43284-111">The **API reference** is a set of pages for each Q# function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="43284-112">これらのページでは、それぞれの呼び出しに対する入力と操作、および例と詳細情報へのリンクが文書化されています。</span><span class="sxs-lookup"><span data-stu-id="43284-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="43284-113">API リファレンスは、各リリースの一部として Q # ソースコードの小規模な DFM ドキュメントから自動的に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="43284-113">The API reference is automatically extracted from small DFM documents in Q# source code as a part of each release.</span></span>
- <span data-ttu-id="43284-114">各サンプルに含まれている**README<!---->の md**ファイルと kata は、そのサンプルまたは kata の使用方法、使用方法、およびその他の Quantum 開発キットにどのように関連しているかを説明しています。</span><span class="sxs-lookup"><span data-stu-id="43284-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="43284-115">これらのファイルは、 [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/)を使用して記述されています。これは、コードリポジトリに直接ドキュメントを添付する場合によく使用される dfm に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="43284-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="43284-116">概念説明のドキュメントに貢献する</span><span class="sxs-lookup"><span data-stu-id="43284-116">Contributing to the Conceptual Documentation</span></span> ##

<span data-ttu-id="43284-117">概念説明または README ドキュメントの改善に寄与するために、は、必要に応じて、microsoft [**docs/QuantumKatas-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/quantum**](https://github.com/Microsoft/Quantum)、または[**microsoft/** ](https://github.com/Microsoft/QuantumKatas)にプル要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="43284-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="43284-118">ここでは、以下のプル要求について詳しく説明しますが、ここでは、ドキュメントを改善するために注意が必要ないくつかの点について説明します。</span><span class="sxs-lookup"><span data-stu-id="43284-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="43284-119">閲覧者は、さまざまな背景から Quantum 開発キットのドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="43284-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="43284-120">高校をはじめとする学生の方は、在籍期間の教職員を対象にして、quantum コンピューティングの研究を実行するすべての人が、ドキュメントを読むことができます。</span><span class="sxs-lookup"><span data-stu-id="43284-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="43284-121">可能な限り、閲覧者の一部に関する豊富な知識を前提としてはなりません。わかりやすい説明を入力したり、他のリソースへのリンクを提供して詳細を参照したりできる場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43284-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="43284-122">ドキュメントセットが書籍や論文のようにレイアウトされていないので、読者は "中間" のように見えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="43284-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="43284-123">たとえば、検索エンジンによってインデックスが提案されない場合や、友人がリンクを送信したことがある場合は、それを解決することができます。常に明確なコンテキストを提供し、必要に応じてリンクを提供することで、読者の支援を試みます。</span><span class="sxs-lookup"><span data-stu-id="43284-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="43284-124">一部のリーダーは抽象的なステートメントと定義を最も役に立ちますが、他のリーダーは具体的な例から推定することで最適に動作します。</span><span class="sxs-lookup"><span data-stu-id="43284-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="43284-125">一般的なケースと特定の例を両方とも指定すると、両方の読者がクォンタムプログラミングを最大限に活用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43284-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="43284-126">特に、ドキュメント化されているコードを記述している場合は、読者にとって明らかではないことが明らかな場合があります。</span><span class="sxs-lookup"><span data-stu-id="43284-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="43284-127">プログラミングには1つの一意の最善の方法はありません。そのため、どのような方法でリーダーが使用されているかにかかわらず、コードでアイデアを表現するために最も役に立つ設計パターンを推測することはできません。</span><span class="sxs-lookup"><span data-stu-id="43284-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="43284-128">読者がコードをどのように使用するかを明確にすることは、そのコンテキストを提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43284-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="43284-129">Quantum プログラミングコミュニティの多くのメンバーは、学術研究者であり、主にコミュニティへの投稿のために引用文献を通じて認識されています。</span><span class="sxs-lookup"><span data-stu-id="43284-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="43284-130">読者が追加の資料を見つけられるようにするだけでなく、論文、講演、ブログの投稿、ソフトウェアツールなどの教育機関の出力を適切に提案することで、教育者はコミュニティの向上に最適な作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="43284-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="43284-131">Quantum プログラミングコミュニティは、広範でて多様なコミュニティです。</span><span class="sxs-lookup"><span data-stu-id="43284-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="43284-132">サードパーティの例では、gendered 代名詞を使用します (例: "user..........................." など)。</span><span class="sxs-lookup"><span data-stu-id="43284-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="43284-133">引用とリンクに含まれる人々の名前が cognizant されていて、非 ASCII 文字を正しく含めることにより、メンバーに対してコミュニティの多様性を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="43284-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="43284-134">同様に、英語の単語の多くは、技術的なドキュメントでの使用によって、個々の閲覧者とコミュニティの両方に害を及ぼす可能性があるため、hateful よって使用されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="43284-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="43284-135">API リファレンスへの貢献</span><span class="sxs-lookup"><span data-stu-id="43284-135">Contributing to the API References</span></span> ##

<span data-ttu-id="43284-136">API 参照の向上を促進するために、ドキュメントに記載されているコードでプル要求を直接開くと最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43284-136">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="43284-137">各関数、操作、またはユーザー定義型は、ドキュメントコメントをサポートしています (`//`ではなく `///` で示されています)。</span><span class="sxs-lookup"><span data-stu-id="43284-137">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="43284-138">Quantum 開発キットの各リリースをコンパイルするときに、これらのコメントを使用して https://docs.microsoft.com/qsharp/api/ で API 参照を生成します。これには、各呼び出し元からの入力と出力の詳細、呼び出し元ごとの前提条件、およびそれらの使用方法の例が含まれます。</span><span class="sxs-lookup"><span data-stu-id="43284-138">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="43284-139">生成された API ドキュメントを手動で編集しないようにしてください。これらのファイルは、新しいリリースごとに上書きされます。</span><span class="sxs-lookup"><span data-stu-id="43284-139">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="43284-140">コミュニティへの貢献度を設定し、リリース後もユーザーが確実にリリースできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="43284-140">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="43284-141">たとえば、`PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`操作について考えてみます。</span><span class="sxs-lookup"><span data-stu-id="43284-141">For example, consider an operation `PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`.</span></span>
<span data-ttu-id="43284-142">ドキュメントコメントは、ユーザーが `angles`を解釈する方法、`register`の初期状態を操作が想定していること、`register` に及ぼす影響などを理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43284-142">A documentation comment should help a user learn how to interpret `angles`, what the operation assumes about the initial state of `register`, what the effect on `register` is, and so forth.</span></span>
<span data-ttu-id="43284-143">これらのさまざまな情報は、ドキュメントコメント内の特別に名前が付けられた Markdown セクションによって、Q # コンパイラに提供できます。</span><span class="sxs-lookup"><span data-stu-id="43284-143">Each of these different pieces of information can be provided to the Q# compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="43284-144">`PrepareTrialState`の例では、次のようなコードを記述することがあります。</span><span class="sxs-lookup"><span data-stu-id="43284-144">For the example of `PrepareTrialState`, we might write something like the following:</span></span>

```qsharp
/// # Summary
/// Given a register of qubits, prepares them in a trial state by rotating each
/// independently.
///
/// # Description
/// This operation prepares the input register by performing a
/// $Y$ rotation on each qubit by an angle given in `angles`.
///
/// # Input
/// ## angles
/// An array of parameters
/// ## register
/// A register of qubits initially in the $\ket{00\cdots0}$ state.
///
/// # Example
/// To prepare an equal superposition $\ket{++\cdots+}$ over all input qubits:
/// ```qsharp
/// PrepareTrialState(ConstantArray(Length(register), PI() / 2.0), register);
/// ```
///
/// # Remarks
/// This operation is generally useful in the inner loop of an optimization
/// algorithm.
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.Ry
operation PrepareTrialState(angles : Double[], register : Qubit[]) : Unit {
    // ...
}
```

<span data-ttu-id="43284-145">ドキュメント作成の一般的なプラクティスに加えて、API ドキュメントのコメントを記述する際には、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="43284-145">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="43284-146">各ドキュメントコメントの形式は、Q # コンパイラがドキュメントを正しく表示するために必要なものと一致させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="43284-146">The format of each documentation comment has to match what the Q# compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="43284-147">`/// # Remarks` などの一部のセクションでは自由形式のコンテンツを使用できますが、`/// # See Also` セクションなどのセクションの方が制限されています。</span><span class="sxs-lookup"><span data-stu-id="43284-147">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="43284-148">リーダーは、メインの API 参照サイトで API ドキュメントを読み取ることができます。また、各名前空間の概要についても、ホバー情報を使用して IDE 内からも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="43284-148">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="43284-149">`/// # Summary` が文の長さを超えていないことを確認すると、リーダーは、さらに読む必要があるか、他の場所を参照する必要があるかをすばやく確認でき、名前空間の概要をすばやくスキャンするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="43284-149">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="43284-150">ドキュメントはコード自体よりもかなり長くなる可能性がありますが、これで問題はありません。</span><span class="sxs-lookup"><span data-stu-id="43284-150">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="43284-151">コードの小さな部分でも、そのコードが存在するコンテキストがわからないユーザーには予期しない影響が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43284-151">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="43284-152">具体的な例を提供し、説明を明確にすることで、ユーザーが使用できるコードを最適に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="43284-152">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
