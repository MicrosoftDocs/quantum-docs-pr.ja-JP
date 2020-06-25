---
title: Microsoft QDK にコードを投稿する
description: サンプルおよびライブラリコードを Microsoft Quantum Development Kit (QDK) に投稿する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.code
ms.openlocfilehash: edc52dc4434e91258bece28812fd76b66329c6f9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275480"
---
# <a name="contributing-code"></a>コードの投稿

問題の報告とドキュメントの改善に加えて、quantum 開発キットへのコードの投稿は、quantum プログラミングコミュニティでの同僚を支援する非常に直接的な方法である可能性があります。
コードを投稿することで、問題の修正、新しい例の提供、既存のライブラリの使いやすさの向上、またはまったく新しい機能の追加を行うことができます。

このガイドでは、プル要求をレビューして、投稿を最大限に活用するために役立つ情報について少し詳しく説明します。

## <a name="what-we-look-for"></a>検索対象

優れたコードの投稿物は、問題の修正、既存の機能の拡張、またはリポジトリのスコープ内にある新機能の追加を行うために、Quantum 開発キットリポジトリの既存の作業に基づいています。
コードの投稿を受け入れると、Quantum 開発キット自体の一部になります。これは、新しい機能がリリースされ、保持され、残りの Quantum 開発キットと同じ方法で開発されるようになります。
このため、投稿物によって追加された機能が十分にテストされ、文書化されている場合に便利です。

### <a name="unit-tests"></a>単体テスト

キャノンなどのライブラリを構成する Q # 関数、操作、およびユーザー定義型は、 [**Microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries/)リポジトリでの開発の一部として自動的にテストされます。
たとえば、新しいプル要求が開かれたときに、 [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/)構成によって、クォンタムプログラミングコミュニティが依存している既存の機能が、プル要求の変更によって中断されていないことが確認されます。

最新の Q # バージョンでは、属性を使用して単体テストが定義され `@Test("QuantumSimulator")` ます。 引数には、"QuantumSimulator"、"ToffoliSimulator"、"TraceSimulator"、または実行ターゲットを指定する完全修飾名のいずれかを指定できます。 さまざまな実行ターゲットを定義するいくつかの属性が、同じ呼び出し可能にアタッチされる場合があります。 一部のテストでは、 [Microsoft.Quantum.Xunit](https://www.nuget.org/packages/Microsoft.Quantum.Xunit/) `Test` [xunit](https://xunit.github.io/)フレームワークに含まれるすべての Q # 関数と操作を公開する、非推奨の Microsoft Quantum パッケージが使用されています。 単体テストを定義するために、このパッケージは不要になりました。 

次の関数は、 <xref:microsoft.quantum.canon.fst> <xref:microsoft.quantum.canon.snd> 関数と関数が両方とも代表的な例で正しい出力を返すようにするために使用されます。
またはの出力が正しくない場合は、ステートメントを使用して `Fst` `Snd` テストが `fail` 失敗します。

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

より複雑な条件を確認するには、「標準ライブラリ」ガイドの[「テスト」セクション](xref:microsoft.quantum.libraries.diagnostics)の手法を使用します。
たとえば、次のテストでは、によって呼び出されたがと同じものであることを確認し `H(q); X(q); H(q);` <xref:microsoft.quantum.canon.applywith> `Z(q)` ます。

```Q#
@Test("QuantumSimulator")
operation TestApplyWith() : Unit {
    let actual = ApplyWith(H, X, _);
    let expected = Z;
    AssertOperationsEqualReferenced(ApplyToEach(actual, _), ApplyToEachA(expected, _), 4);
}
```

新しい機能を追加する場合は、新しいテストを追加して、意図した内容が確実に行われるようにすることをお勧めします。
これにより、コミュニティの他のメンバーが機能を保守および開発できるようになり、特に、機能に依存する可能性があることを他の開発者が知ることができます。

> [!NOTE]
> これも同様に機能します。
> 一部のテストが欠落している既存の機能がある場合は、テストカバレッジの追加を支援することで、コミュニティに大きな貢献をします。

ローカルでは、Visual Studio のテストエクスプローラーまたはコマンドを使用して単体テストを実行でき `dotnet test` ます。これにより、プル要求を開く前に投稿を確認できます。

<!-- TODO:
### Comments and Documentation ###

### Citations and References ### -->


## <a name="when-well-reject-a-pull-request"></a>プル要求を却下する場合

場合によっては、投稿のプル要求を拒否することがあります。
このような状況が発生したとしても、特定の貢献を受け入れることができない理由がいくつかあるので、これは悪いことではありません。
おそらく、多くの場合、クォンタムプログラミングコミュニティに貢献しているのは良い方法ですが、Quantum 開発キットリポジトリは開発に適していません。
このような場合は、独自のリポジトリ---、Quantum 開発キットの強度の一部にすることを強くお勧めします。これは、現在、キャノンおよび化学ライブラリを配布するのと同じ方法で、GitHub と NuGet.org を使用して独自のライブラリを簡単に作成および配布できることです。

それ以外の場合は、管理と開発の準備が整っていないため、適切な投稿を拒否することがあります。
すべてを実行するのは困難な場合があるため、ロードマップとしてどのような機能を使用できるかを計画します。
これは、サードパーティ製のライブラリとして機能をリリースすることによって、非常に意味があります。
または、機能を変更して、最適な作業を行うことができるように、ロードマップに適合するように、機能を変更することをお勧めします。

また、プル要求を使用するのに役立つドキュメントや単体テストが必要な場合、または、ユーザーが機能を見つけるのが困難になるように、他の Q # ライブラリのスタイルとして十分に異なっている場合にも、プル要求の変更を要求します。
このような場合は、投稿を容易にするために追加または変更できるものについて、コードレビューでアドバイスを提供します。

最後に、 [Microsoft オープンソース](https://opensource.microsoft.com/codeofconduct/)倫理規定に記載されているように、クォンタムコンピューティングコミュニティに悪影響を及ぼす投稿を受け入れることはできません。
私たちは、現在のすばらしい多様性の中でも、今後もさらに包括的になるように、共同作業がクォンタムコンピューティングコミュニティ全体に提供されるようにしたいと考えています。
この目標を達成するための支援を歓迎します。

## <a name="next-steps"></a>次の手順

Quantum 開発キットを利用して、quantum プログラミングコミュニティ全体にとって優れたリソースを作成しようとしていただき、誠にありがとうございます。
詳細については、Q # のスタイルに関する次のガイドを参照してください。

> [!div class="nextstepaction"]
> [Q # スタイルのガイドラインについて学習する](xref:microsoft.quantum.contributing.style)

投稿しようとしているコードの種類によっては、投稿を可能な限りコミュニティにとって優れたものにするために役立つ場合があります。

> [!div class="nextstepaction"]
> [貢献するサンプルについて学習する](xref:microsoft.quantum.contributing.samples)
