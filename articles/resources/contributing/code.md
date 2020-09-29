---
title: Microsoft QDK にコードを投稿する
description: サンプルおよびライブラリコードを Microsoft Quantum Development Kit (QDK) に投稿する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7a258a915a807b8e1ee7c2c9c062017d90f6a454
ms.sourcegitcommit: 685a8ab16d7e6a25e63a168d6e7c385fa6e876cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91489767"
---
# <a name="contributing-code"></a><span data-ttu-id="41f7e-103">コードの投稿</span><span class="sxs-lookup"><span data-stu-id="41f7e-103">Contributing Code</span></span>

<span data-ttu-id="41f7e-104">問題の報告とドキュメントの改善に加えて、quantum 開発キットへのコードの投稿は、quantum プログラミングコミュニティでの同僚を支援する非常に直接的な方法である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-104">In addition to reporting issues and improving documentation, contributing code to the Quantum Development Kit can be a very direct way to help your peers in the quantum programming community.</span></span>
<span data-ttu-id="41f7e-105">コードを投稿することで、問題の修正、新しい例の提供、既存のライブラリの使いやすさの向上、またはまったく新しい機能の追加を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-105">By contributing code, you can help to fix issues, provide new examples, make existing libraries easier to use, or even add entirely new features.</span></span>

<span data-ttu-id="41f7e-106">このガイドでは、プル要求をレビューして、投稿を最大限に活用するために役立つ情報について少し詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-106">In this guide, we'll detail a bit of what we look for when we review pull requests to help your contribution do the most good.</span></span>

## <a name="what-we-look-for"></a><span data-ttu-id="41f7e-107">検索対象</span><span class="sxs-lookup"><span data-stu-id="41f7e-107">What We Look For</span></span>

<span data-ttu-id="41f7e-108">優れたコードの投稿物は、問題の修正、既存の機能の拡張、またはリポジトリのスコープ内にある新機能の追加を行うために、Quantum 開発キットリポジトリの既存の作業に基づいています。</span><span class="sxs-lookup"><span data-stu-id="41f7e-108">An ideal code contribution builds on the existing work in a Quantum Development Kit repository to fix issues, expand existing features, or to add new features that are within the scope of a repository.</span></span>
<span data-ttu-id="41f7e-109">コードの投稿を受け入れると、Quantum 開発キット自体の一部になります。これは、新しい機能がリリースされ、保持され、残りの Quantum 開発キットと同じ方法で開発されるようになります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-109">When we accept a code contribution, it becomes a part of the Quantum Development Kit itself, such that new features will be released, maintained, and developed in the same way as the rest of the Quantum Development Kit.</span></span>
<span data-ttu-id="41f7e-110">このため、投稿物によって追加された機能が十分にテストされ、文書化されている場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="41f7e-110">Thus, it is helpful when functionality added by a contribution is well-tested and is documented.</span></span>

### <a name="unit-tests"></a><span data-ttu-id="41f7e-111">単体テスト</span><span class="sxs-lookup"><span data-stu-id="41f7e-111">Unit Tests</span></span>

<span data-ttu-id="41f7e-112">キャノンなどの Q# ライブラリを構成する関数、操作、およびユーザー定義型は、 [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) リポジトリでの開発の一部として自動的にテストされます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-112">The Q# functions, operations, and user-defined types that make up libraries such as the canon are automatically tested as a part of development on the [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/) repository.</span></span>
<span data-ttu-id="41f7e-113">たとえば、新しいプル要求が開かれたときに、 [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) 構成によって、クォンタムプログラミングコミュニティが依存している既存の機能が、プル要求の変更によって中断されていないことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-113">When a new pull request is opened, for instance, our [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/) configuration will check that the changes in the pull request do not break any existing functionality that the quantum programming community depends on.</span></span>

<span data-ttu-id="41f7e-114">最新バージョンでは、 Q# 属性を使用して単体テストが定義され `@Test("QuantumSimulator")` ます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-114">With the latest Q# version, unit tests are defined using the `@Test("QuantumSimulator")` attribute.</span></span> <span data-ttu-id="41f7e-115">引数には、"QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"、または実行ターゲットを指定する完全修飾名のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-115">The argument may be either "QuantumSimulator", "ToffoliSimulator", "TraceSimulator", or any fully qualified name specifying the run target.</span></span> <span data-ttu-id="41f7e-116">異なる実行ターゲットを定義するいくつかの属性が、同じ呼び出し可能にアタッチされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-116">Several attributes defining different run targets may be attached to the same callable.</span></span> <span data-ttu-id="41f7e-117">一部のテストでは、で終了[Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/)したすべて Q# の関数と操作を `Test` [xunit](https://xunit.github.io/)フレームワークに公開する、非推奨の Microsoft Quantum パッケージが引き続き使用されます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-117">Some of our tests still use the deprecated [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) package that exposes all Q# functions and operations ending in `Test` to the [xUnit](https://xunit.github.io/) framework.</span></span> <span data-ttu-id="41f7e-118">単体テストを定義するために、このパッケージは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="41f7e-118">This package is no longer needed for defining unit tests.</span></span> 

<span data-ttu-id="41f7e-119">次の関数は、 <xref:microsoft.quantum.canon.fst> <xref:microsoft.quantum.canon.snd> 関数と関数が両方とも代表的な例で正しい出力を返すようにするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-119">The following function is used to ensure that the <xref:microsoft.quantum.canon.fst> and <xref:microsoft.quantum.canon.snd> functions both return the right outputs in a representative example.</span></span>
<span data-ttu-id="41f7e-120">またはの出力が正しくない場合は、ステートメントを使用して `Fst` `Snd` テストが `fail` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-120">If the output of `Fst` or `Snd` is incorrect, the `fail` statement is used to cause the test to fail.</span></span>

```qsharp
@Test("QuantumSimulator")
function PairTest () : Unit {
    let pair = (12, PauliZ);

    if (Fst(pair) != 12) {
        let actual = Fst(pair);
        fail $"Expected 12, actual {actual}.";
    }

    if (Snd(pair) != PauliZ) {
        let actual = Snd(pair);
        fail $"Expected PauliZ, actual {actual}.";
    }
}
```

<span data-ttu-id="41f7e-121">より複雑な条件を確認するには、「標準ライブラリ」ガイドの [「テスト」セクション](xref:microsoft.quantum.libraries.diagnostics) の手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-121">More complicated conditions can be checked using the techniques in the [testing section](xref:microsoft.quantum.libraries.diagnostics) of the standard libraries guide.</span></span>
<span data-ttu-id="41f7e-122">たとえば、次のテストでは、によって呼び出されたがと同じものであることを確認し `H(q); X(q); H(q);` <xref:microsoft.quantum.canon.applywith> `Z(q)` ます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-122">For instance, the following test checks that `H(q); X(q); H(q);` as called by <xref:microsoft.quantum.canon.applywith> does the same thing as `Z(q)`.</span></span>

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

<span data-ttu-id="41f7e-123">新しい機能を追加する場合は、新しいテストを追加して、意図した内容が確実に行われるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41f7e-123">When adding new features, it's a good idea to also add new tests to make sure that your contribution does what it's supposed to.</span></span>
<span data-ttu-id="41f7e-124">これにより、コミュニティの他のメンバーが機能を保守および開発できるようになり、特に、機能に依存する可能性があることを他の開発者が知ることができます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-124">This helps the rest of the community to maintain and develop your feature, and in particular helps other developers know that they can rely on your feature.</span></span>

> [!NOTE]
> <span data-ttu-id="41f7e-125">これも同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-125">This works the other way around, too!</span></span>
> <span data-ttu-id="41f7e-126">一部のテストが欠落している既存の機能がある場合は、テストカバレッジの追加を支援することで、コミュニティに大きな貢献をします。</span><span class="sxs-lookup"><span data-stu-id="41f7e-126">If there's an existing feature that's missing some tests, helping us add test coverage would make a great contribution to the community.</span></span>

<span data-ttu-id="41f7e-127">ローカルでは、Visual Studio のテストエクスプローラーまたはコマンドを使用して単体テストを実行でき `dotnet test` ます。これにより、プル要求を開く前に投稿を確認できます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-127">Locally, unit tests can be run using the Visual Studio Test Explorer or the `dotnet test` command, so that you can check your contribution before opening up a pull request.</span></span>

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->

## <a name="pull-requests"></a><span data-ttu-id="41f7e-128">pull request</span><span class="sxs-lookup"><span data-stu-id="41f7e-128">Pull Requests</span></span>

<span data-ttu-id="41f7e-129">作業内容を投稿する準備ができたら、GitHub 経由で対応するリポジトリにプル要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="41f7e-129">When you are ready to contribute your work, please send a Pull Request via GitHub to the corresponding repository.</span></span>
<span data-ttu-id="41f7e-130">チームは、フィードバックをレビューして提供します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-130">The team will review and provide feedback.</span></span> <span data-ttu-id="41f7e-131">すべてのコメントに応答して解決する必要があります。また、コードを分岐にマージする前に、すべてのチェックに合格する必要があり `main` ます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-131">All comments need to be answered and resolved and all checks need to pass before the code is merged to the `main` branch.</span></span>

## <a name="when-well-reject-a-pull-request"></a><span data-ttu-id="41f7e-132">プル要求を却下する場合</span><span class="sxs-lookup"><span data-stu-id="41f7e-132">When We'll Reject a Pull Request</span></span>

<span data-ttu-id="41f7e-133">場合によっては、投稿のプル要求を拒否することがあります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-133">Sometimes, we'll reject the pull request for a contribution.</span></span>
<span data-ttu-id="41f7e-134">このような状況が発生したとしても、特定の貢献を受け入れることができない理由がいくつかあるので、これは悪いことではありません。</span><span class="sxs-lookup"><span data-stu-id="41f7e-134">If this happens to you, it doesn't mean that it's bad, as there's a number of reasons why we might not be able to accept a particular contribution.</span></span>
<span data-ttu-id="41f7e-135">おそらく、多くの場合、クォンタムプログラミングコミュニティに貢献しているのは良い方法ですが、Quantum 開発キットリポジトリは開発に適していません。</span><span class="sxs-lookup"><span data-stu-id="41f7e-135">Perhaps most commonly, a contribution to the quantum programming community is a really good one, but the Quantum Development Kit repositories aren't the right place to develop it.</span></span>
<span data-ttu-id="41f7e-136">このような場合は、独自のリポジトリ---、Quantum 開発キットの強度の一部にすることを強くお勧めします。これは、現在、キャノンおよび化学ライブラリを配布するのと同じ方法で、GitHub と NuGet.org を使用して独自のライブラリを簡単に作成および配布できることです。</span><span class="sxs-lookup"><span data-stu-id="41f7e-136">In such cases, we strongly encourage you to make your own repository --- part of the strength of the Quantum Development Kit is that it's easy to make and distribute your own libraries using GitHub and NuGet.org, the same way that we distribute the canon and chemistry libraries today.</span></span>

<span data-ttu-id="41f7e-137">それ以外の場合は、管理と開発の準備が整っていないため、適切な投稿を拒否することがあります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-137">At other times, we may reject a good contribution simply because we aren't yet ready to maintain and develop it.</span></span>
<span data-ttu-id="41f7e-138">すべてを実行するのは困難な場合があるため、ロードマップとしてどのような機能を使用できるかを計画します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-138">It can be difficult to do everything, so we plan out what features we're best able to work on as a roadmap.</span></span>
<span data-ttu-id="41f7e-139">これは、サードパーティ製のライブラリとして機能をリリースすることによって、非常に意味があります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-139">This can be another case where releasing a feature as a third-party library can make a lot of sense.</span></span>
<span data-ttu-id="41f7e-140">または、機能を変更して、最適な作業を行うことができるように、ロードマップに適合するように、機能を変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="41f7e-140">Alternatively, we may ask for your help in modifying a feature to better fit into our roadmap so that we can do the best work we can with it.</span></span>

<span data-ttu-id="41f7e-141">また、プル要求を使用するのに役立つドキュメントや単体テストが必要な場合、または、 Q# ユーザーが機能を見つけづらくなることを防ぐために、他のライブラリとは異なるスタイルの変更が必要な場合にも、プル要求の変更を要求します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-141">We'll also ask for changes to a pull request if it requires more documentation or unit tests to help us make use of it, or if it differs enough in style from the rest of the Q# libraries that it will make it harder for users to find your feature.</span></span>
<span data-ttu-id="41f7e-142">このような場合は、投稿を容易にするために追加または変更できるものについて、コードレビューでアドバイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-142">In these cases, we'll try to offer some advice in code reviews about what can be added or changed to make your contribution easier for us to include.</span></span>

<span data-ttu-id="41f7e-143">最後に、 [Microsoft オープンソース](https://opensource.microsoft.com/codeofconduct/)倫理規定に記載されているように、クォンタムコンピューティングコミュニティに悪影響を及ぼす投稿を受け入れることはできません。</span><span class="sxs-lookup"><span data-stu-id="41f7e-143">Finally, we cannot accept contributions that cause harm the quantum computing community, as outlined in the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).</span></span>
<span data-ttu-id="41f7e-144">私たちは、現在のすばらしい多様性の中でも、今後もさらに包括的になるように、共同作業がクォンタムコンピューティングコミュニティ全体に提供されるようにしたいと考えています。</span><span class="sxs-lookup"><span data-stu-id="41f7e-144">We want to ensure that contributions serve the entire quantum computing community, both in its current wonderful diversity, and in the future as it grows to become still more inclusive.</span></span>
<span data-ttu-id="41f7e-145">この目標を達成するための支援を歓迎します。</span><span class="sxs-lookup"><span data-stu-id="41f7e-145">We appreciate your help in realizing this goal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="41f7e-146">次のステップ</span><span class="sxs-lookup"><span data-stu-id="41f7e-146">Next steps</span></span>

<span data-ttu-id="41f7e-147">Quantum 開発キットを利用して、quantum プログラミングコミュニティ全体にとって優れたリソースを作成しようとしていただき、誠にありがとうございます。</span><span class="sxs-lookup"><span data-stu-id="41f7e-147">Thanks for helping to make the Quantum Development Kit a great resource for the entire quantum programming community!</span></span>
<span data-ttu-id="41f7e-148">詳細については、次のスタイルに関するガイドを参照してください Q# 。</span><span class="sxs-lookup"><span data-stu-id="41f7e-148">To learn more, please continue with the following guide on Q# style.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="41f7e-149">スタイルのガイドラインについて学習する Q#</span><span class="sxs-lookup"><span data-stu-id="41f7e-149">Learn about Q# style guidelines</span></span>](xref:microsoft.quantum.contributing.style)

<span data-ttu-id="41f7e-150">投稿しようとしているコードの種類によっては、投稿を可能な限りコミュニティにとって優れたものにするために役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="41f7e-150">Depending on what kind of code you're contributing, there may be additional things to keep in mind that can help you make your contribution do as much good for the community as possible.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="41f7e-151">貢献するサンプルについて学習する</span><span class="sxs-lookup"><span data-stu-id="41f7e-151">Learn about contributing samples</span></span>](xref:microsoft.quantum.contributing.samples)
