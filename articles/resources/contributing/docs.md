---
title: Microsoft QDK にドキュメントを投稿する
description: Microsoft Quantum ドキュメントセットに概念または API コンテンツを投稿する方法について説明します。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.docs
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2debef858c38b9a8f11264858130ed7cb41543ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691780"
---
# <a name="improving-documentation"></a>ドキュメントの改善

Quantum 開発キットのドキュメントでは、さまざまな形式を採用しています。これは、クォンタム開発者が情報をすぐに利用できるようにするためのものです。

[コードとしてのドキュメント](https://www.writethedocs.org/guide/docs-as-code/)の原則に従うと、すべての Quantum 開発キットのドキュメントはコードとして書式設定され、Quantum 開発キットの構築に使用されるソースコードと同じ方法で Git を使用して管理されます。
ほとんどの場合、コードのバッキングドキュメントは、さまざまな形式の [Markdown](https://daringfireball.net/projects/markdown/)で構成されています。これは、高度な書式が設定されたテキストを、コマンドライン、ide、ソース管理で簡単に使用できるプレーンテキスト形式で記述するための言語です。
同様に、以下で詳しく説明するように、 [MathJax](https://www.mathjax.org/) ライブラリを使用して、LaTeX 言語を使用したドキュメントの数値演算を可能にします。


ただし、ドキュメントの各形式は、詳細によって多少異なります。

- **概念説明のドキュメント** は、に公開されている一連の記事で構成されています。このドキュメントでは、 https://docs.microsoft.com/quantum クォンタムコンピューティングの基本から、インターチェンジ形式の技術仕様までのすべてを説明しています。 これらの記事は [Docfx-Flavored Markdown (DFM)](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)で記述されています。これは、豊富なドキュメントセットの作成に使用される Markdown バリアントです。
- **API リファレンス** は、にパブリッシュされた各 Q# 関数、操作、およびユーザー定義型のページのセットです https://docs.microsoft.com/qsharp/api/ 。 これらのページでは、それぞれの呼び出しに対する入力と操作、および例と詳細情報へのリンクが文書化されています。 API リファレンスは、 Q# 各リリースの一部としてソースコードの小さな DFM ドキュメントから自動的に抽出されます。
- 各サンプルに含まれている **readme.txt <!---->** ファイルと kata は、そのサンプルまたは kata の使用方法、使用方法、および Quantum 開発キットの残りの部分にどのように関連しているかを説明しています。 これらのファイルは、 [GitHub Flavored Markdown (GFM)](https://github.github.com/gfm/)を使用して記述されています。これは、コードリポジトリに直接ドキュメントを添付する場合によく使用される dfm に代わるものです。

## <a name="contributing-to-the-conceptual-documentation"></a>概念説明のドキュメントに貢献する

概念説明または README ドキュメントの改善に寄与するために、は、必要に応じて、microsoft [**docs/QuantumKatas-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr/
)、 [**microsoft/quantum**](https://github.com/Microsoft/Quantum)、または [**microsoft/**](https://github.com/Microsoft/QuantumKatas)にプル要求を開始します。
ここでは、以下のプル要求について詳しく説明しますが、ここでは、ドキュメントを改善するために注意が必要ないくつかの点について説明します。

- 閲覧者は、さまざまな背景から Quantum 開発キットのドキュメントにアクセスできます。 高校をはじめとする学生の方は、在籍期間の教職員を対象にして、quantum コンピューティングの研究を実行するすべての人が、ドキュメントを読むことができます。 可能な限り、閲覧者の一部に関する豊富な知識を前提としてはなりません。わかりやすい説明を入力したり、他のリソースへのリンクを提供して詳細を参照したりできる場合に最も役立ちます。
- ドキュメントセットが書籍や論文のようにレイアウトされていないので、読者は "中間" のように見えるかもしれません。 たとえば、検索エンジンによってインデックスが提案されない場合や、友人がリンクを送信したことがある場合は、それを解決することができます。常に明確なコンテキストを提供し、必要に応じてリンクを提供することで、読者の支援を試みます。
- 一部のリーダーは抽象的なステートメントと定義を最も役に立ちますが、他のリーダーは具体的な例から推定することで最適に動作します。 一般的なケースと特定の例を両方とも指定すると、両方の読者がクォンタムプログラミングを最大限に活用するのに役立ちます。
- 特に、ドキュメント化されているコードを記述している場合は、読者にとって明らかではないことが明らかな場合があります。 プログラミングには1つの一意の最善の方法はありません。そのため、どのような方法でリーダーが使用されているかにかかわらず、コードでアイデアを表現するために最も役に立つ設計パターンを推測することはできません。 読者がコードをどのように使用するかを明確にすることは、そのコンテキストを提供するのに役立ちます。
- Quantum プログラミングコミュニティの多くのメンバーは、学術研究者であり、主にコミュニティへの投稿のために引用文献を通じて認識されています。 読者が追加の資料を見つけられるようにするだけでなく、論文、講演、ブログの投稿、ソフトウェアツールなどの教育機関の出力を適切に提案することで、教育者はコミュニティの向上に最適な作業を行うことができます。
- Quantum プログラミングコミュニティは、広範でて多様なコミュニティです。 サードパーティの例では、gendered 代名詞を使用します (例: "user..........................." など)。 引用とリンクに含まれる人々の名前が cognizant されていて、非 ASCII 文字を正しく含めることにより、メンバーに対してコミュニティの多様性を示すことができます。 同様に、英語の単語の多くは、技術的なドキュメントでの使用によって、個々の閲覧者とコミュニティの両方に害を及ぼす可能性があるため、hateful よって使用されることがよくあります。

### <a name="referencing-sample-code-from-conceptual-articles"></a>概念説明の記事からサンプルコードを参照する

[サンプルリポジトリ](https://github.com/Microsoft/Quantum)のコードを追加する場合は、特殊な DocFX-Flavored Markdown コマンドを使用して実行できます。

```markdown
:::code language="qsharp" source="~/quantum/samples/algorithms/chsh-game/Game.qs" range="4-8":::
```

このコマンドは、 [ `Game.qs` `chsh-game` サンプルから](https://github.com/microsoft/Quantum/blob/main/samples/algorithms/chsh-game/Game.qs)4 行のファイルをインポートし、 Q# 構文の強調表示の目的でコードとしてマークします。
このコマンドを使用すると、概念説明の記事とサンプルリポジトリ間でコードが重複しないようにすることができます。これにより、ドキュメント内のサンプルコードは常に最新の状態になります。

## <a name="contributing-to-the-api-references"></a>API リファレンスへの貢献

API 参照の向上を促進するために、ドキュメントに記載されているコードでプル要求を直接開くと最も役立ちます。
各関数、操作、またはユーザー定義型は、ドキュメントコメントをサポートしています (で `///` はなくで示さ `//` れています)。
各リリースの Quantum 開発キットをコンパイルするときに、これらのコメントを使用しての API 参照が生成されます。これには https://docs.microsoft.com/qsharp/api/ 、各呼び出し元からの入力と出力の詳細、呼び出し元ごとの前提条件、およびそれらの使用方法の例が含まれます。

> [!IMPORTANT]
> 生成された API ドキュメントを手動で編集しないようにしてください。これらのファイルは、新しいリリースごとに上書きされます。
> コミュニティへの貢献度を設定し、リリース後もユーザーが確実にリリースできるようにすることをお勧めします。

たとえば、関数について考えてみ `ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)` ます。
ドキュメントコメントは、との解釈方法や、関数の用途を理解するのに役立ち `bits` `oracle` ます。
これらのさまざまな情報は、 Q# ドキュメントコメント内の特別に名前が付けられた Markdown セクションによってコンパイラに提供されます。
の例では `ControlledOnBitString` 、次のようなコードを記述することがあります。

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

上記のコードの表示されているバージョンは、 [ `ControlledOnBitString` 関数の API ドキュメント](xref:Microsoft.Quantum.Canon.ControlledOnBitString)に表示されます。

ドキュメント作成の一般的なプラクティスに加えて、API ドキュメントのコメントを記述する際には、次の点に注意してください。

- 各ドキュメントコメントの形式は、 Q# ドキュメントが正しく表示されるためにコンパイラが期待するものと一致する必要があります。 一部のセクション (自由形式のコンテンツを許可するなど) では、セクションなどのセクションの `/// # Remarks` `/// # See Also` 方が制限されています。
- リーダーは、メインの API 参照サイトで API ドキュメントを読み取ることができます。また、各名前空間の概要についても、ホバー情報を使用して IDE 内からも読み取ることができます。 が `/// # Summary` 文の長さを超えていないことを確認すると、リーダーは、さらに読む必要があるか、他の場所を探す必要があるかをすばやく確認でき、名前空間の概要をすばやくスキャンするのに役立ちます。
- ドキュメントはコード自体よりもかなり長くなる可能性がありますが、これで問題はありません。 コードの小さな部分でも、そのコードが存在するコンテキストがわからないユーザーには予期しない影響が生じる可能性があります。 具体的な例を提供し、説明を明確にすることで、ユーザーが使用できるコードを最適に使用できるようになります。

<!-- ## LaTeX Formatting ##

**TODO** -->
