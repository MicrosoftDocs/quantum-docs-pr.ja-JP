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
# <a name="no-locq-file-structure"></a>Q# ファイル構造

ファイルは、一連の Q# *名前空間宣言*で構成されます。
各名前空間宣言には、ユーザー定義型、操作、および関数の宣言が含まれており、任意の数の宣言を任意の順序で含めることができます。
名前空間内の宣言の詳細については、「 [ユーザー定義型](xref:microsoft.quantum.guide.types#user-defined-types)、 [操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)、および [関数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)」を参照してください。

名前空間の宣言の外側に表示されるテキストは、コメントだけです。
特に、名前空間のドキュメントコメントは、宣言の前に記述します。 詳細については、この記事の [ドキュメントコメント](#documentation-comments) を参照してください。 

## <a name="namespace-declarations"></a>名前空間の宣言

Q#通常、ファイルには名前空間宣言が1つしかありませんが、none を指定したり、空にしたり、コメントを含めたりすることができます。また、複数の名前空間を含めることもできます。
名前空間宣言を入れ子にすることはできません。

同じ Q# 名前を持つ型、操作、または関数の宣言がない限り、同時にコンパイルされた複数のファイルで同じ名前空間を宣言できます。
特に、宣言が同一であっても、複数のファイルの同じ名前空間で同じ型を定義することは無効です。

名前空間の宣言は、キーワード、 `namespace` その後に名前空間の名前、および中かっこで囲まれた名前空間に含まれる宣言で構成され `{ }` ます。
名前空間名は、ピリオドで区切られた1つまたは複数の有効な記号のシーケンスの .NET パターンに従い `.` ます。
たとえば、 `MyQuantumStuff` と `Microsoft.Quantum.Intrinsic` は有効な名前空間名です。
規則により、名前空間の名前の記号を大文字にします。ただし、これは必須ではありません。

ファイル内でさらに下に宣言されている型または呼び出し方向への参照は、適切に解決されます。型、操作、または関数の宣言を参照の前に記述する必要はありません。

## <a name="open-directives"></a>オープンディレクティブ

名前空間ブロック内では、ディレクティブを使用して、 `open` 特定の名前空間で宣言されたすべての型と呼び出し許容型をインポートし、非修飾名で参照します。
このようなディレクティブは、キーワードと、 `open` `open` その後に開く名前空間、および終端のセミコロンで構成されます。

> [!NOTE] 
> すべて `open` のディレクティブは `function` 、 `operation` `newtype` 名前空間ブロック内の、、または宣言の前に記述する必要があります。

必要に応じて、開いている名前空間の短い名前を定義できます。 短い名前が定義されている場合は、定義された短い名前を使用して、その名前空間のすべての要素を修飾する必要があります。 たとえば、次の名前空間宣言とオープンディレクティブがあるとします。

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

宣言された操作がからの操作を使用する場合は `Op` `Microsoft.Quantum.Intrinsic` 、単にを使用して呼び出し `Op` ます。
ただし、から特定の関数を呼び出すには、 `Fn` `Microsoft.Quantum.Math` を使用してそれを呼び出す必要があり `Math.Fn` ます。

ディレクティブは、 `open` ファイル内の名前空間ブロック全体に適用されます。
このため、前と同じファイルに追加の名前空間を定義した場合、 Q# `NS` 2 番目の名前空間で定義されている操作/関数/型は、その中に open ディレクティブを繰り返していない限り、またはにアクセスできません `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 。 

現在の名前空間で開かれて *いない* 別の名前空間で定義されている型または呼び出し可能を参照するには、完全修飾名で参照する必要があります。
たとえば、名前空間からという名前の操作を指定した場合は、 `Op` `X.Y` 次のようになります。

* `X.Y.Op` `X.Y` 現在のブロックで名前空間が既に開かれている場合を除き、完全修飾名で参照する必要があります。 
* 名前空間が開かれている場合でも、 `X` として操作を参照することはできません `Y.Op` 。
* の名前空間とファイルに短い名前を定義した場合は `Z` `X.Y` 、をとして参照する必要があり `Op` `Z.Op` ます。 

通常は、ディレクティブを使用して名前空間を含めることをお勧め `open` します。
2つの名前空間で同じ名前の構造体を定義し、現在のソースが両方のコンストラクトを使用する場合は、完全修飾名を使用する必要があります。

Q# は、他の .NET 言語として名前を付ける場合と同じ規則に従います。
ただし、で Q# は、名前空間への相対参照はサポートされません。
たとえば、名前空間が開いている場合、 `a.b` という名前の操作への参照は、 `c.d` 完全名を持つ操作に解決 *されません* `a.b.c.d` 。

## <a name="formatting"></a>書式設定

ほとんどの Q# ステートメントおよびディレクティブは、終端のセミコロンで終わり `;` ます。
`for`ステートメントブロックで終了するやなどのステートメントや宣言 `operation` (次のセクションを参照) では、末尾にセミコロンを使用する必要はありません。
各ステートメントの説明には、終端のセミコロンが必要かどうかが示されます。

ステートメント (式、宣言、ディレクティブなど) は、複数の行にわたって分割できます。
1行に複数のステートメントを配置することは避けてください。

## <a name="statement-blocks"></a>ステートメントブロック

Q# ステートメントは、中かっこで囲まれたステートメントブロックにグループ化され `{ }` ます。 ステートメントブロックは、開始位置で始まり、 `{` 終わりで終わり `}` ます。

別のブロック内で構文的に囲まれたステートメントブロックは、それを含むブロックのサブブロックと見なされます。コンテナーとサブブロックは、外部ブロックと内部ブロックとも呼ばれます。

## <a name="comments"></a>コメント

コメントは、2つのスラッシュ (,) で始まり、 `//` 行の終わりまで続きます。
コメントは、ソースファイル内の任意の場所に置くことができ Q# ます。

## <a name="documentation-comments"></a>ドキュメント コメント

3つのスラッシュで始まるコメント `///` は、名前空間、操作、特殊化、関数、または型定義の直前に出現するときに、コンパイラによって特別に処理されます。
その場合、コンパイラは、定義されている呼び出し可能またはユーザー定義型のドキュメントとして、他の .NET 言語と同じように扱います。

コメント内で `///` は、API ドキュメントの一部として表示されるテキストは [Markdown](https://daringfireball.net/projects/markdown/syntax)として書式設定され、ドキュメントのさまざまな部分が特別な名前付きヘッダーによって示されます。
Markdown では、拡張機能を使用して、 `@"<ref target>"` での操作、関数、およびユーザー定義型の相互参照を Q# 行います。 `<ref target>`参照先のコードオブジェクトの完全修飾名で置き換えます。
ドキュメントエンジンによっては、追加の Markdown 拡張機能がサポートされている場合もあります。

次に例を示します。

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

次の名前は、ドキュメントのコメントヘッダーとして有効です。

- **Summary**: 関数または操作の動作、または型の目的の簡単な概要。 概要の最初の段落は、ホバー情報に使用されます。 プレーンテキストである必要があります。
- **説明**: 関数または操作の動作、または型の目的を説明します。 概要と説明を一緒に使用すると、関数、操作、または型の生成されたドキュメントファイルが形成されます。
  この説明では、インラインの LaTeX 形式のシンボルおよび式がサポートされています。
- **入力**: 操作または関数の入力タプルの説明。
  には、入力タプルの各要素を示す追加の Markdown サブセクションを含めることができます。
- **出力**: 演算または関数によって返される組の説明。
- **型パラメーター**: ジェネリック型パラメーターごとに1つの追加のサブセクションを含む空のセクション。
- **例**: 使用されている操作、関数、または型の短い例。
- **解説**: 操作、関数、または型のいくつかの側面を説明するその他の prose。
- 関連する関数、操作、またはユーザー定義型を示す完全修飾名の一覧**も参照してください**。
- **参照**: 文書化された項目の参照および引用の一覧。

## <a name="next-steps"></a>次のステップ

の [操作と関数](xref:microsoft.quantum.guide.operationsfunctions) について説明 Q# します。