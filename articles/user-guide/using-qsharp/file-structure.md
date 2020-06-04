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
# <a name="q-file-structure"></a>Q # ファイル構造

すべての Q # 操作、関数、およびユーザー定義型は、名前空間内で定義されます。

Q # ファイルは、一連の*名前空間宣言*で構成されます。
各名前空間の宣言には、ユーザー定義型、操作、および関数の宣言が含まれています。
名前空間宣言には、任意の数の宣言を任意の順序で含めることができます。
名前空間内の[ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)、[操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)、および[関数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)の宣言の詳細については、次のリンク先を参照してください。

名前空間の宣言の外側に表示されるテキストは、コメントだけです。
特に、名前空間については、宣言の前にドキュメントコメント (下の詳細) を記述します。

## <a name="namespace-declarations"></a>名前空間の宣言

Q # ファイルには、通常、名前空間宣言が1つだけ含まれますが、(空またはコメントを含む) は使用できません。また、複数の名前空間を含めることもできます。
名前空間宣言を入れ子にすることはできません。

同じ名前の型、操作、または関数の宣言がない限り、同じ名前空間を複数の Q # ファイルで宣言することができます。
特に、宣言が同一であっても、複数のファイルの同じ名前空間で同じ型を定義することは無効です。

名前空間宣言は、キーワード、名前 `namespace` 空間の名前、始めかっこ `{` 、名前空間に含まれる宣言、および終わりかっこで構成され `}` ます。
名前空間名は、ピリオドで区切られた1つまたは複数の有効な記号のシーケンスの .NET パターンに従い `.` ます。
たとえば、 `MyQuantumStuff` と `Microsoft.Quantum.Intrinsic` は有効な名前空間名です。
慣例により、名前空間名に含まれる記号は大文字になりますが、これは必須ではありません。

ファイル内でさらに下に宣言されている型または呼び出し方向への参照は、適切に解決されます。型、操作、または関数の宣言を参照の前に記述する必要はありません。

## <a name="open-directives"></a>オープンディレクティブ

名前空間ブロック内では、ディレクティブを使用して、 `open` 特定の名前空間で宣言されたすべての型と呼び出し可能な型をインポートし、非修飾名で参照することができます。
このようなディレクティブは、キーワードと、 `open` `open` その後に開く名前空間、および終端のセミコロンで構成されます。

> [!NOTE] 
> すべて `open` のディレクティブは `function` 、 `operation` `newtype` 名前空間ブロック内の、、または宣言の前に記述する必要があります。

必要に応じて、名前空間のすべての要素が定義された短い名前によって修飾されるように、開いている名前空間の短い名前を定義することもできます。 たとえば、次の名前空間宣言とオープンディレクティブがあるとします。

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

宣言する操作でからの操作が使用されている場合は `Op` `Microsoft.Quantum.Intrinsic` 、単にを使用してそれを呼び出し `Op` ます。
ただし、から特定の関数を呼び出したい場合は、 `Fn` `Microsoft.Quantum.Math` を使用して呼び出す必要があり `Math.Fn` ます。

ディレクティブは、 `open` ファイル内の名前空間ブロック全体に適用されます。
このため、上記と同じ Q # ファイルに追加の名前空間を定義した場合、 `NS` 2 番目の名前空間で定義されているすべての操作/関数/型は、開いているディレクティブを繰り返していない限り、またはにアクセスできません `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 。 

現在の名前空間で開かれて*いない*別の名前空間で定義されている型または呼び出し可能が、完全修飾名で参照されている必要があります。
たとえば、現在のブロックで名前空間が既に開かれている場合を除き、名前空間からのという名前の操作は、 `Op` `X.Y` 完全修飾名によって参照される必要があり `X.Y.Op` `X.Y` ます。 前述のように、名前空間が開かれている場合でも、 `X` として操作を参照することはできません `Y.Op` 。
の短い名前 `Z` `X.Y` がその名前空間とファイルで定義されている場合は、を `Op` として参照する必要があり `Z.Op` ます。 

通常は、ディレクティブを使用して名前空間を含めることをお勧め `open` します。
2つの名前空間で同じ名前の構造体を定義し、現在のソースが両方のコンストラクトを使用する場合は、完全修飾名を使用する必要があります。

Q # は、他の .NET 言語として名前を付ける場合と同じ規則に従います。
ただし、Q # では名前空間への相対参照はサポートされません。
つまり、名前空間が開かれている場合、という名前の操作への参照は、 `a.b` `c.d` 完全名を持つ操作に対して解決され*ません* `a.b.c.d` 。

## <a name="formatting"></a>書式設定

ほとんどの Q # ステートメントとディレクティブは、終端のセミコロンで終わり `;` ます。
`for` `operation` ステートメントブロック (下記参照) で終わるやなどのステートメントと宣言では、末尾にセミコロンを使用する必要はありません。
各ステートメントの説明には、終端のセミコロンが必要かどうかが示されます。

ステートメント (式、宣言、ディレクティブなど) は、複数の行にわたって分割される場合があります。
1行に複数のステートメントを記述することは避けてください。

## <a name="statement-blocks"></a>ステートメントブロック

Q # ステートメントは、ステートメントブロックにグループ化されます。
ステートメントブロックは、開始位置で始まり、 `{` 終わりで終わり `}` ます。

別のブロック内で構文的に囲まれたステートメントブロックは、それを含むブロックのサブブロックと見なされます。コンテナーとサブブロックは、外部ブロックと内部ブロックとも呼ばれます。

## <a name="comments"></a>コメント

コメントは、2つのスラッシュ (,) で始まり、 `//` 行の終わりまで続きます。
Q # ソースファイル内の任意の場所にコメントが表示される場合があります。

## <a name="documentation-comments"></a>ドキュメント コメント

3つのスラッシュで始まるコメント `///` は、名前空間、操作、特殊化、関数、または型定義の直前に出現するときに、コンパイラによって特別に処理されます。
その場合、その内容は、他の .NET 言語と同様に、定義された呼び出し可能またはユーザー定義型のドキュメントとして取得されます。

コメント内で `///` は、API ドキュメントの一部として表示されるテキストは[Markdown](https://daringfireball.net/projects/markdown/syntax)として書式設定され、ドキュメントのさまざまな部分が特別な名前のヘッダーによって示されています。
Markdown の拡張機能として、Q # の操作、関数、ユーザー定義型への相互参照は、を使用して含めることができます `@"<ref target>"` 。ここで、 `<ref target>` は参照されるコードオブジェクトの完全修飾名に置き換えられます。
必要に応じて、ドキュメントエンジンで追加の Markdown 拡張機能をサポートすることもできます。

例:

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

次の名前は、ドキュメントのコメントヘッダーとして認識されます。

- **Summary**: 関数または操作の動作、または型の目的の簡単な概要。 概要の最初の段落は、ホバー情報に使用されます。 プレーンテキストである必要があります。
- **説明**: 関数または操作の動作、または型の目的の説明。 概要と説明を連結して、関数、操作、または型の生成されたドキュメントファイルを作成します。
  説明には、インラインの LaTeX 形式のシンボルと式を含めることができます。
- **入力**: 操作または関数の入力タプルの説明。
  入力タプルの各要素を示す追加の Markdown サブセクションを含めることができます。
- **出力**: 演算または関数によって返される組の説明。
- **型パラメーター**: ジェネリック型パラメーターごとに1つの追加のサブセクションを含む空のセクション。
- **例**: 使用されている操作、関数、または型の簡単な例。
- **解説**: 操作、関数、または型のいくつかの側面を説明するその他の prose。
- 関連する関数、操作、またはユーザー定義型を示す完全修飾名の一覧**も参照してください**。
- **参照**: ドキュメント化されている項目の参照および引用の一覧。

## <a name="next-steps"></a>次の手順

Q # の[操作と関数](xref:microsoft.quantum.guide.operationsfunctions)について説明します。