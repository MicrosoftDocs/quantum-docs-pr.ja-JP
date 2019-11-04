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
# <a name="improving-documentation"></a>ドキュメントの改善 #

Quantum 開発キットのドキュメントでは、さまざまな形式を採用しています。これは、クォンタム開発者が情報をすぐに利用できるようにするためのものです。

[コードとしてのドキュメント](https://www.writethedocs.org/guide/docs-as-code/)の原則に従うと、すべての Quantum 開発キットのドキュメントはコードとして書式設定され、Quantum 開発キットの構築に使用されるソースコードと同じ方法で Git を使用して管理されます。
ほとんどの場合、コードのバッキングドキュメントは、さまざまな形式の[Markdown](https://daringfireball.net/projects/markdown/)で構成されています。これは、高度な書式が設定されたテキストを、コマンドライン、ide、ソース管理で簡単に使用できるプレーンテキスト形式で記述するための言語です。
同様に、以下で詳しく説明するように、 [MathJax](https://www.mathjax.org/)ライブラリを使用して、LaTeX 言語を使用したドキュメントの数値演算を可能にします。


ただし、ドキュメントの各形式は、詳細によって多少異なります。

- **概念説明のドキュメント**は、 https://docs.microsoft.com/quantum に公開されている一連の記事で構成されています。このドキュメントでは、クォンタムコンピューティングの基礎から、インターチェンジ形式の技術仕様までのすべてを説明しています。 これらの記事は[Docfx-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)で記述されています。これは、豊富なドキュメントセットの作成に使用される Markdown バリアントです。
- **API リファレンス**は、各 Q # 関数、操作、およびユーザー定義型のページのセットであり、 https://docs.microsoft.com/qsharp/api/ に発行されます。 これらのページでは、それぞれの呼び出しに対する入力と操作、および例と詳細情報へのリンクが文書化されています。 API リファレンスは、各リリースの一部として Q # ソースコードの小規模な DFM ドキュメントから自動的に抽出されます。
- 各サンプルに含まれている**README<!---->の md**ファイルと kata は、そのサンプルまたは kata の使用方法、使用方法、およびその他の Quantum 開発キットにどのように関連しているかを説明しています。 これらのファイルは、 [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/)を使用して記述されています。これは、コードリポジトリに直接ドキュメントを添付する場合によく使用される dfm に代わるものです。

## <a name="contributing-to-the-conceptual-documentation"></a>概念説明のドキュメントに貢献する ##

概念説明または README ドキュメントの改善に寄与するために、は、必要に応じて、microsoft [**docs/QuantumKatas-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/quantum**](https://github.com/Microsoft/Quantum)、または[**microsoft/** ](https://github.com/Microsoft/QuantumKatas)にプル要求を開始します。
ここでは、以下のプル要求について詳しく説明しますが、ここでは、ドキュメントを改善するために注意が必要ないくつかの点について説明します。

- 閲覧者は、さまざまな背景から Quantum 開発キットのドキュメントにアクセスできます。 高校をはじめとする学生の方は、在籍期間の教職員を対象にして、quantum コンピューティングの研究を実行するすべての人が、ドキュメントを読むことができます。 可能な限り、閲覧者の一部に関する豊富な知識を前提としてはなりません。わかりやすい説明を入力したり、他のリソースへのリンクを提供して詳細を参照したりできる場合に最も役立ちます。
- ドキュメントセットが書籍や論文のようにレイアウトされていないので、読者は "中間" のように見えるかもしれません。 たとえば、検索エンジンによってインデックスが提案されない場合や、友人がリンクを送信したことがある場合は、それを解決することができます。常に明確なコンテキストを提供し、必要に応じてリンクを提供することで、読者の支援を試みます。
- 一部のリーダーは抽象的なステートメントと定義を最も役に立ちますが、他のリーダーは具体的な例から推定することで最適に動作します。 一般的なケースと特定の例を両方とも指定すると、両方の読者がクォンタムプログラミングを最大限に活用するのに役立ちます。
- 特に、ドキュメント化されているコードを記述している場合は、読者にとって明らかではないことが明らかな場合があります。 プログラミングには1つの一意の最善の方法はありません。そのため、どのような方法でリーダーが使用されているかにかかわらず、コードでアイデアを表現するために最も役に立つ設計パターンを推測することはできません。 読者がコードをどのように使用するかを明確にすることは、そのコンテキストを提供するのに役立ちます。
- Quantum プログラミングコミュニティの多くのメンバーは、学術研究者であり、主にコミュニティへの投稿のために引用文献を通じて認識されています。 読者が追加の資料を見つけられるようにするだけでなく、論文、講演、ブログの投稿、ソフトウェアツールなどの教育機関の出力を適切に提案することで、教育者はコミュニティの向上に最適な作業を行うことができます。
- Quantum プログラミングコミュニティは、広範でて多様なコミュニティです。 サードパーティの例では、gendered 代名詞を使用します (例: "user..........................." など)。 引用とリンクに含まれる人々の名前が cognizant されていて、非 ASCII 文字を正しく含めることにより、メンバーに対してコミュニティの多様性を示すことができます。 同様に、英語の単語の多くは、技術的なドキュメントでの使用によって、個々の閲覧者とコミュニティの両方に害を及ぼす可能性があるため、hateful よって使用されることがよくあります。

## <a name="contributing-to-the-api-references"></a>API リファレンスへの貢献 ##

API 参照の向上を促進するために、ドキュメントに記載されているコードでプル要求を直接開くと最も役立ちます。
各関数、操作、またはユーザー定義型は、ドキュメントコメントをサポートしています (`//`ではなく `///` で示されています)。
Quantum 開発キットの各リリースをコンパイルするときに、これらのコメントを使用して https://docs.microsoft.com/qsharp/api/ で API 参照を生成します。これには、各呼び出し元からの入力と出力の詳細、呼び出し元ごとの前提条件、およびそれらの使用方法の例が含まれます。

> [!IMPORTANT]
> 生成された API ドキュメントを手動で編集しないようにしてください。これらのファイルは、新しいリリースごとに上書きされます。
> コミュニティへの貢献度を設定し、リリース後もユーザーが確実にリリースできるようにすることをお勧めします。

たとえば、`PrepareTrialState(angles : Double[], register : Qubit[]) : Unit`操作について考えてみます。
ドキュメントコメントは、ユーザーが `angles`を解釈する方法、`register`の初期状態を操作が想定していること、`register` に及ぼす影響などを理解するのに役立ちます。
これらのさまざまな情報は、ドキュメントコメント内の特別に名前が付けられた Markdown セクションによって、Q # コンパイラに提供できます。
`PrepareTrialState`の例では、次のようなコードを記述することがあります。

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

ドキュメント作成の一般的なプラクティスに加えて、API ドキュメントのコメントを記述する際には、次の点に注意してください。

- 各ドキュメントコメントの形式は、Q # コンパイラがドキュメントを正しく表示するために必要なものと一致させる必要があります。 `/// # Remarks` などの一部のセクションでは自由形式のコンテンツを使用できますが、`/// # See Also` セクションなどのセクションの方が制限されています。
- リーダーは、メインの API 参照サイトで API ドキュメントを読み取ることができます。また、各名前空間の概要についても、ホバー情報を使用して IDE 内からも読み取ることができます。 `/// # Summary` が文の長さを超えていないことを確認すると、リーダーは、さらに読む必要があるか、他の場所を参照する必要があるかをすばやく確認でき、名前空間の概要をすばやくスキャンするのに役立ちます。
- ドキュメントはコード自体よりもかなり長くなる可能性がありますが、これで問題はありません。 コードの小さな部分でも、そのコードが存在するコンテキストがわからないユーザーには予期しない影響が生じる可能性があります。 具体的な例を提供し、説明を明確にすることで、ユーザーが使用できるコードを最適に使用できるようになります。

<!-- ## LaTeX Formatting ##

**TODO** -->
