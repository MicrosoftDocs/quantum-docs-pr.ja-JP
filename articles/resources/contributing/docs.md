---
title: Microsoft QDK にドキュメントを投稿する
description: Microsoft Quantum ドキュメントセットに概念または API コンテンツを投稿する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 2debef858c38b9a8f11264858130ed7cb41543ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691780"
---
# <a name="improving-documentation"></a><span data-ttu-id="90c66-103">ドキュメントの改善</span><span class="sxs-lookup"><span data-stu-id="90c66-103">Improving Documentation</span></span>

<span data-ttu-id="90c66-104">Quantum 開発キットのドキュメントでは、さまざまな形式を採用しています。これは、クォンタム開発者が情報をすぐに利用できるようにするためのものです。</span><span class="sxs-lookup"><span data-stu-id="90c66-104">The documentation for the Quantum Development Kit takes on several different forms, such that information is readily available to quantum developers.</span></span>

<span data-ttu-id="90c66-105">[コードとしてのドキュメント](https://www.writethedocs.org/guide/docs-as-code/)の原則に従うと、すべての Quantum 開発キットのドキュメントはコードとして書式設定され、Quantum 開発キットの構築に使用されるソースコードと同じ方法で Git を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="90c66-105">Following the principles of [Docs as Code](https://www.writethedocs.org/guide/docs-as-code/), all Quantum Development Kit documentation is formatted as code and is managed using Git in the same way as the source code that is used to build the Quantum Development Kit.</span></span>
<span data-ttu-id="90c66-106">ほとんどの場合、コードのバッキングドキュメントは、さまざまな形式の [Markdown](https://daringfireball.net/projects/markdown/)で構成されています。これは、高度な書式が設定されたテキストを、コマンドライン、ide、ソース管理で簡単に使用できるプレーンテキスト形式で記述するための言語です。</span><span class="sxs-lookup"><span data-stu-id="90c66-106">For the most part, the code backing documentation consists of various forms of [Markdown](https://daringfireball.net/projects/markdown/), a language for writing out richly formatted text in a plain text format that's easy to use at the command line, in IDEs, and with source control.</span></span>
<span data-ttu-id="90c66-107">同様に、以下で詳しく説明するように、 [MathJax](https://www.mathjax.org/) ライブラリを使用して、LaTeX 言語を使用したドキュメントの数値演算を可能にします。</span><span class="sxs-lookup"><span data-stu-id="90c66-107">We similarly adopt the [MathJax](https://www.mathjax.org/) library to allow for formatting mathematics in documentation using the LaTeX language, as detailed further below.</span></span>


<span data-ttu-id="90c66-108">ただし、ドキュメントの各形式は、詳細によって多少異なります。</span><span class="sxs-lookup"><span data-stu-id="90c66-108">That said, each form of documentation does vary somewhat in the details:</span></span>

- <span data-ttu-id="90c66-109">**概念説明のドキュメント** は、に公開されている一連の記事で構成されています。このドキュメントでは、 https://docs.microsoft.com/quantum クォンタムコンピューティングの基本から、インターチェンジ形式の技術仕様までのすべてを説明しています。</span><span class="sxs-lookup"><span data-stu-id="90c66-109">The **conceptual documentation** consists of a set of articles that are published to https://docs.microsoft.com/quantum, and that describe everything from the basics of quantum computing to the technical specifications for interchange formats.</span></span> <span data-ttu-id="90c66-110">これらの記事は [Docfx-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)で記述されています。これは、豊富なドキュメントセットの作成に使用される Markdown バリアントです。</span><span class="sxs-lookup"><span data-stu-id="90c66-110">These articles are written in [DocFX-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html), a Markdown variant used for creating rich documentation sets.</span></span>
- <span data-ttu-id="90c66-111">**API リファレンス** は、にパブリッシュされた各 :::no-loc(Q#)::: 関数、操作、およびユーザー定義型のページのセットです https://docs.microsoft.com/qsharp/api/ 。</span><span class="sxs-lookup"><span data-stu-id="90c66-111">The **API reference** is a set of pages for each :::no-loc(Q#)::: function, operation, and user-defined type, published to https://docs.microsoft.com/qsharp/api/.</span></span> <span data-ttu-id="90c66-112">これらのページでは、それぞれの呼び出しに対する入力と操作、および例と詳細情報へのリンクが文書化されています。</span><span class="sxs-lookup"><span data-stu-id="90c66-112">These pages document the inputs and operations to each callable, along with examples and links to more information.</span></span> <span data-ttu-id="90c66-113">API リファレンスは、 :::no-loc(Q#)::: 各リリースの一部としてソースコードの小さな DFM ドキュメントから自動的に抽出されます。</span><span class="sxs-lookup"><span data-stu-id="90c66-113">The API reference is automatically extracted from small DFM documents in :::no-loc(Q#)::: source code as a part of each release.</span></span>
- <span data-ttu-id="90c66-114">各サンプルに含まれている **readme.txt <!---->** ファイルと kata は、そのサンプルまたは kata の使用方法、使用方法、および Quantum 開発キットの残りの部分にどのように関連しているかを説明しています。</span><span class="sxs-lookup"><span data-stu-id="90c66-114">The **README<!---->.md** files included with each sample and kata describe how to use that sample or kata is used, what it covers, and how it relates to the rest of the Quantum Development Kit.</span></span> <span data-ttu-id="90c66-115">これらのファイルは、 [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/)を使用して記述されています。これは、コードリポジトリに直接ドキュメントを添付する場合によく使用される dfm に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="90c66-115">These files are written using [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/), a more lightweight alternative to DFM that's popular for attaching documentation directly to code repositories.</span></span>

## <a name="contributing-to-the-conceptual-documentation"></a><span data-ttu-id="90c66-116">概念説明のドキュメントに貢献する</span><span class="sxs-lookup"><span data-stu-id="90c66-116">Contributing to the Conceptual Documentation</span></span>

<span data-ttu-id="90c66-117">概念説明または README ドキュメントの改善に寄与するために、は、必要に応じて、microsoft [**docs/QuantumKatas-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/quantum**](https://github.com/Microsoft/Quantum)、または [**microsoft/**](https://github.com/Microsoft/QuantumKatas)にプル要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="90c66-117">To contribute an improvement to the conceptual or README documentation, then, starts with a pull request onto either [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
), [**Microsoft/Quantum**](https://github.com/Microsoft/Quantum), or [**Microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas), as is appropriate.</span></span>
<span data-ttu-id="90c66-118">ここでは、以下のプル要求について詳しく説明しますが、ここでは、ドキュメントを改善するために注意が必要ないくつかの点について説明します。</span><span class="sxs-lookup"><span data-stu-id="90c66-118">We'll describe more about pull requests below, but for now there's a few things that are good to keep in mind as you improve documentation:</span></span>

- <span data-ttu-id="90c66-119">閲覧者は、さまざまな背景から Quantum 開発キットのドキュメントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="90c66-119">Readers come to the Quantum Development Kit documentation from a very wide range of backgrounds.</span></span> <span data-ttu-id="90c66-120">高校をはじめとする学生の方は、在籍期間の教職員を対象にして、quantum コンピューティングの研究を実行するすべての人が、ドキュメントを読むことができます。</span><span class="sxs-lookup"><span data-stu-id="90c66-120">Everyone from high school students looking to learn something new and exciting through to tenured faculty performing quantum computing research should be able to get something out of reading the documentation.</span></span> <span data-ttu-id="90c66-121">可能な限り、閲覧者の一部に関する豊富な知識を前提としてはなりません。わかりやすい説明を入力したり、他のリソースへのリンクを提供して詳細を参照したりできる場合に最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90c66-121">To the extent that's possible, please don't assume extensive knowledge on the part of your readers, as they may just be starting out. It's most helpful if you can provide clear and accessible descriptions, or can provide links to other resources for more information.</span></span>
- <span data-ttu-id="90c66-122">ドキュメントセットが書籍や論文のようにレイアウトされていないので、読者は "中間" のように見えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="90c66-122">Documentation sets aren't laid out like books or papers, in that readers will arrive in what might seem like the "middle."</span></span> <span data-ttu-id="90c66-123">たとえば、検索エンジンによってインデックスが提案されない場合や、友人がリンクを送信したことがある場合は、それを解決することができます。常に明確なコンテキストを提供し、必要に応じてリンクを提供することで、読者の支援を試みます。</span><span class="sxs-lookup"><span data-stu-id="90c66-123">For example, search engines might not suggest the index, or they might have been sent a link by a friend trying to help them out. Try to help your reader by always providing a clear context, along with links where appropriate.</span></span>
- <span data-ttu-id="90c66-124">一部のリーダーは抽象的なステートメントと定義を最も役に立ちますが、他のリーダーは具体的な例から推定することで最適に動作します。</span><span class="sxs-lookup"><span data-stu-id="90c66-124">Some readers will find abstract statements and definitions most helpful, while other readers work best by extrapolating from concrete examples.</span></span> <span data-ttu-id="90c66-125">一般的なケースと特定の例を両方とも指定すると、両方の読者がクォンタムプログラミングを最大限に活用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90c66-125">Providing both the general case and specific examples can help both readers get the most out of quantum programming.</span></span>
- <span data-ttu-id="90c66-126">特に、ドキュメント化されているコードを記述している場合は、読者にとって明らかではないことが明らかな場合があります。</span><span class="sxs-lookup"><span data-stu-id="90c66-126">Especially if you also wrote the code being documented, things may be obvious to you that are not at all obvious to your reader.</span></span> <span data-ttu-id="90c66-127">プログラミングには1つの一意の最善の方法はありません。そのため、どのような方法でリーダーが使用されているかにかかわらず、コードでアイデアを表現するために最も役に立つ設計パターンを推測することはできません。</span><span class="sxs-lookup"><span data-stu-id="90c66-127">There's no one unique best way to program, so no matter how clever or experienced a reader might be, they can't guess at what design patterns you found the most helpful to express your ideas in code.</span></span> <span data-ttu-id="90c66-128">読者がコードをどのように使用するかを明確にすることは、そのコンテキストを提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90c66-128">Being clear about how a reader can expect to make use of your code can help provide that context.</span></span>
- <span data-ttu-id="90c66-129">Quantum プログラミングコミュニティの多くのメンバーは、学術研究者であり、主にコミュニティへの投稿のために引用文献を通じて認識されています。</span><span class="sxs-lookup"><span data-stu-id="90c66-129">Many members of the quantum programming community are academic researchers, and are recognized mainly through citations for their contributions to the community.</span></span> <span data-ttu-id="90c66-130">読者が追加の資料を見つけられるようにするだけでなく、論文、講演、ブログの投稿、ソフトウェアツールなどの教育機関の出力を適切に提案することで、教育者はコミュニティの向上に最適な作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="90c66-130">In addition to helping readers find additional materials, making sure to properly cite academic outputs such as papers, talks, blog posts, and software tools can help academic contributors to keep doing their best work to improve the community.</span></span>
- <span data-ttu-id="90c66-131">Quantum プログラミングコミュニティは、広範でて多様なコミュニティです。</span><span class="sxs-lookup"><span data-stu-id="90c66-131">The quantum programming community is a broad and wonderfully diverse community.</span></span> <span data-ttu-id="90c66-132">サードパーティの例では、gendered 代名詞を使用します (例: "user..........................." など)。</span><span class="sxs-lookup"><span data-stu-id="90c66-132">The use of gendered pronouns in third-person examples (e.g.: "if a user ..., he will ...") can work to exclude rather than include.</span></span> <span data-ttu-id="90c66-133">引用とリンクに含まれる人々の名前が cognizant されていて、非 ASCII 文字を正しく含めることにより、メンバーに対してコミュニティの多様性を示すことができます。</span><span class="sxs-lookup"><span data-stu-id="90c66-133">Being cognizant of people's names in citations and links, and of the correct inclusion of non-ASCII characters can serve the diversity of the community by showing respect to its members.</span></span> <span data-ttu-id="90c66-134">同様に、英語の単語の多くは、技術的なドキュメントでの使用によって、個々の閲覧者とコミュニティの両方に害を及ぼす可能性があるため、hateful よって使用されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="90c66-134">Similarly, many words in the English language are often used in a hateful manner, such that their use in technical documentation can cause harm both to individual readers and to the community at large.</span></span>

### <a name="referencing-sample-code-from-conceptual-articles"></a><span data-ttu-id="90c66-135">概念説明の記事からサンプルコードを参照する</span><span class="sxs-lookup"><span data-stu-id="90c66-135">Referencing Sample Code from Conceptual Articles</span></span>

<span data-ttu-id="90c66-136">[サンプルリポジトリ](https://github.com/Microsoft/Quantum)のコードを追加する場合は、特殊な DocFX-Flavored Markdown コマンドを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="90c66-136">If you want to include code from the [samples repository](https://github.com/Microsoft/Quantum), you can do so using a special DocFX-Flavored Markdown command:</span></span>

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

<span data-ttu-id="90c66-137">このコマンドは、 [ `Game.qs` `chsh-game` サンプルから](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)4 行のファイルをインポートし、 :::no-loc(Q#)::: 構文の強調表示の目的でコードとしてマークします。</span><span class="sxs-lookup"><span data-stu-id="90c66-137">This command will import lines 4 to 8 of the [`Game.qs` file from the `chsh-game` sample](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs), marking them as :::no-loc(Q#)::: code for the purpose of syntax highlighting.</span></span>
<span data-ttu-id="90c66-138">このコマンドを使用すると、概念説明の記事とサンプルリポジトリ間でコードが重複しないようにすることができます。これにより、ドキュメント内のサンプルコードは常に最新の状態になります。</span><span class="sxs-lookup"><span data-stu-id="90c66-138">Using this command, you can avoid duplicating code between conceptual articles and the samples repository, so that sample code in documentation is always as up to date as possible.</span></span>

## <a name="contributing-to-the-api-references"></a><span data-ttu-id="90c66-139">API リファレンスへの貢献</span><span class="sxs-lookup"><span data-stu-id="90c66-139">Contributing to the API References</span></span>

<span data-ttu-id="90c66-140">API 参照の向上を促進するために、ドキュメントに記載されているコードでプル要求を直接開くと最も役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90c66-140">To contribute an improvement to the API references, it's most helpful to open a pull request directly on the code being documented.</span></span>
<span data-ttu-id="90c66-141">各関数、操作、またはユーザー定義型は、ドキュメントコメントをサポートしています (で `///` はなくで示さ `//` れています)。</span><span class="sxs-lookup"><span data-stu-id="90c66-141">Each function, operation, or user-defined type supports a documentation comment (denoted with `///` instead of `//`).</span></span>
<span data-ttu-id="90c66-142">各リリースの Quantum 開発キットをコンパイルするときに、これらのコメントを使用しての API 参照が生成されます。これには https://docs.microsoft.com/qsharp/api/ 、各呼び出し元からの入力と出力の詳細、呼び出し元ごとの前提条件、およびそれらの使用方法の例が含まれます。</span><span class="sxs-lookup"><span data-stu-id="90c66-142">When we compile each release of the Quantum Development Kit, these comments are used to generate the API reference at https://docs.microsoft.com/qsharp/api/, including details about the inputs to and outputs from each callable, the assumptions each callable makes, and examples of how to use them.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90c66-143">生成された API ドキュメントを手動で編集しないようにしてください。これらのファイルは、新しいリリースごとに上書きされます。</span><span class="sxs-lookup"><span data-stu-id="90c66-143">Please make sure to not manually edit the generated API documentation, as these files are overwritten with each new release.</span></span>
> <span data-ttu-id="90c66-144">コミュニティへの貢献度を設定し、リリース後もユーザーが確実にリリースできるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90c66-144">We value your contribution to the community, and want to make sure that your changes continue to help users release after release.</span></span>

<span data-ttu-id="90c66-145">たとえば、関数について考えてみ `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` ます。</span><span class="sxs-lookup"><span data-stu-id="90c66-145">For example, consider the function `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="90c66-146">ドキュメントコメントは、との解釈方法や、関数の用途を理解するのに役立ち `bits` `oracle` ます。</span><span class="sxs-lookup"><span data-stu-id="90c66-146">A documentation comment should help a user learn how to interpret `bits` and `oracle` and what the function is for.</span></span>
<span data-ttu-id="90c66-147">これらのさまざまな情報は、 :::no-loc(Q#)::: ドキュメントコメント内の特別に名前が付けられた Markdown セクションによってコンパイラに提供されます。</span><span class="sxs-lookup"><span data-stu-id="90c66-147">Each of these different pieces of information can be provided to the :::no-loc(Q#)::: compiler by a specially named Markdown section in the documentation comment.</span></span>
<span data-ttu-id="90c66-148">の例では `ControlledOnBitString` 、次のようなコードを記述することがあります。</span><span class="sxs-lookup"><span data-stu-id="90c66-148">For the example of `ControlledOnBitString`, we might write something like the following:</span></span>

```qsharp
 /// # Summary
 /// Returns a unitary operation that applies an oracle on the target register if the 
 /// control register state corresponds to a specified bit mask.
 ///
 /// # Description
 /// The output of this function is an operation that can be represented by a
 /// unitary transformation $U$ such that
 /// \begin{align}
 ///     U \ket{b_0 b_1 \cdots b_{n - 1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_{n-1}} \otimes
 ///     \begin{cases}
 ///         V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_{n - 1}) = \texttt{bits} \\\\
 ///         \ket{\psi} & \textrm{otherwise}
 ///     \end{cases},
 /// \end{align}
 /// where $V$ is a unitary transformation that represents the action of the
 /// `oracle` operation.
 ///
 /// # Input
 /// ## bits
 /// The bit string to control the given unitary operation on.
 /// ## oracle
 /// The unitary operation to be applied on the target register.
 ///
 /// # Output
 /// A unitary operation that applies `oracle` on the target register if the control 
 /// register state corresponds to the bit mask `bits`.
 ///
 /// # Remarks
 /// The length of `bits` and `controlRegister` must be equal.
 ///
 /// Given a Boolean array `bits` and a unitary operation `oracle`, the output of this function
 /// is an operation that performs the following steps:
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits`;
 /// * apply `Controlled oracle` to the control and target registers;
 /// * apply an `X` operation to each qubit of the control register that corresponds to `false` 
 /// element of the `bits` again to return the control register to the original state.
 ///
 /// The output of the `Controlled` functor is a special case of `ControlledOnBitString` where `bits` is equal to `[true, ..., true]`.
 ///
 /// # Example
 /// The following code snippets are equivalent:
 /// ```qsharp
 /// (ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
 /// ```
 /// and
 /// ```qsharp
 /// within {
 ///     ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
 /// } apply {
 ///     Controlled oracle(controlRegister, targetRegister);
 /// }
 /// ```
 ///
 /// The following code prepares a state $\frac{1}{2}(\ket{00} - \ket{01} + \ket{10} + \ket{11})$:
 /// ```qsharp
 /// using (register = Qubit[2]) {
 ///     ApplyToEach(H, register);
 ///     (ControlledOnBitString([false], Z))(register[0..0], register[1]);
 /// }
 /// ```
 function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
 {
     return ControlledOnBitStringImpl(bits, oracle, _, _);
 }
```

<span data-ttu-id="90c66-149">上記のコードの表示されているバージョンは、 [ `ControlledOnBitString` 関数の API ドキュメント](xref:Microsoft.Quantum.Canon.ControlledOnBitString)に表示されます。</span><span class="sxs-lookup"><span data-stu-id="90c66-149">You can see the rendered version of the code above in the [API documentation for the `ControlledOnBitString` function](xref:Microsoft.Quantum.Canon.ControlledOnBitString).</span></span>

<span data-ttu-id="90c66-150">ドキュメント作成の一般的なプラクティスに加えて、API ドキュメントのコメントを記述する際には、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="90c66-150">In addition to the general practice of documentation writing, in writing API documentation comments it helps to keep a few things in mind:</span></span>

- <span data-ttu-id="90c66-151">各ドキュメントコメントの形式は、 :::no-loc(Q#)::: ドキュメントが正しく表示されるためにコンパイラが期待するものと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90c66-151">The format of each documentation comment has to match what the :::no-loc(Q#)::: compiler expects for your documentation to appear correctly.</span></span> <span data-ttu-id="90c66-152">一部のセクション (自由形式のコンテンツを許可するなど) では、セクションなどのセクションの `/// # Remarks` `/// # See Also` 方が制限されています。</span><span class="sxs-lookup"><span data-stu-id="90c66-152">Some sections, such as `/// # Remarks` allow for freeform content, while sections such as `/// # See Also` section are more restrictive.</span></span>
- <span data-ttu-id="90c66-153">リーダーは、メインの API 参照サイトで API ドキュメントを読み取ることができます。また、各名前空間の概要についても、ホバー情報を使用して IDE 内からも読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="90c66-153">A reader may read your API documentation on the main API reference site, on the summary for each namespace, or even from within their IDE through the use of hover information.</span></span> <span data-ttu-id="90c66-154">が `/// # Summary` 文の長さを超えていないことを確認すると、リーダーは、さらに読む必要があるか、他の場所を探す必要があるかをすばやく確認でき、名前空間の概要をすばやくスキャンするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="90c66-154">Making sure that `/// # Summary` isn't longer than about a sentence helps your reader quickly sort out whether they need to read further or look elsewhere, and can help in quickly scanning through namespace summaries.</span></span>
- <span data-ttu-id="90c66-155">ドキュメントはコード自体よりもかなり長くなる可能性がありますが、これで問題はありません。</span><span class="sxs-lookup"><span data-stu-id="90c66-155">Your documentation may well wind up being much longer than the code itself, but that's OK!</span></span> <span data-ttu-id="90c66-156">コードの小さな部分でも、そのコードが存在するコンテキストがわからないユーザーには予期しない影響が生じる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="90c66-156">Even a small piece of code can have unexpected effects to users that don't know the context in which that code exists.</span></span> <span data-ttu-id="90c66-157">具体的な例を提供し、説明を明確にすることで、ユーザーが使用できるコードを最適に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="90c66-157">By providing concrete examples and clear explanations, you can help users make the best use of the code that's available to them.</span></span>

<!-- ## LaTeX Formatting ##

**TODO** -->
