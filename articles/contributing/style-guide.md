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
# <a name="q-style-guide"></a>Q # スタイルガイド #
## <a name="general-conventions"></a>一般的な規則 ##

このガイドで推奨されている規則は、Q&a で記述されたプログラムやライブラリを読みやすく理解しやすくすることを目的としています。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- より読みやすくわかりやすいコードをユーザーに提供するために意図的に作成しない限り、規則を無視しないでください。

# <a name="examplestabexamples"></a>[例](#tab/examples)

***

## <a name="naming-conventions"></a>名前付け規則 ##

Quantum 開発キットの提供では、quantum 開発者が簡単に読むことができ、驚くほど簡単なプログラムを作成するのに役立つ関数名と操作名に努めています。
ここで重要なのは、関数、操作、および型の名前を選択するときに、プログラマがクォンタムの概念を表現するために使用する*ボキャブラリ*を確立することです。お客様が選択した内容を明確に伝えることができます。
これにより、導入された名前が隠すのではなく、明確になるようにする責任があります。
このセクションでは、Q # 開発コミュニティで最高の機能を実現するための明示的なガイダンスという観点から、この義務を満たす方法について詳しく説明します。

### <a name="operations-and-functions"></a>操作と関数 ###

名前によって最初に確立されるものの1つは、特定のシンボルが関数または操作を表すかどうかです。
関数と演算の違いは、コードブロックの動作を理解するために重要です。
関数と操作の区別をユーザーに伝えるために、副作用を使用して、その Q&a モデルのクォンタム操作に依存しています。
つまり、操作は何らかの処理*を行います*。

一方、関数は、データ間の数学的な関係を記述します。
式 `Sin(PI() / 2.0)`*は*`1.0`であり、プログラムの状態またはその qubits を意味するものではありません。

要約すると、操作は関数を処理するときに処理を行います。
この区別は、動詞と関数として名詞として名前が付けられることを示しています。

> [!NOTE]
> ユーザー定義型を宣言すると、その型のインスタンスを構築する新しい関数が暗黙的に同時に定義されます。
> その観点からは、ユーザー定義型に名詞という名前を付けて、型自体とコンストラクター関数の名前が一貫している必要があります。

適切であれば、操作の名前は、操作によって行われた効果を明確に示す動詞で始まることを確認してください。
例えば次が挙げられます。

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

特に特別な意味があるケースの1つは、操作が別の操作を入力として受け取り、それを呼び出すときです。
このような場合、外部操作が定義されているときに、入力操作によって実行されるアクションが明確にはなりません。そのため、右の動詞はすぐにはクリアされません。
`ApplyIf`、`ApplyToEach`、`ApplyToFirst`のように、動詞 `Apply`をお勧めします。
この場合、`IterateThroughCartesianPower`のように、他の動詞も便利です。

| 動詞 | 期待される効果 |
| ---- | ------ |
| 適用 | 入力として指定された操作が呼び出されます。 |
| アサート | シミュレーターによって実行されるクォンタム測定の結果に関する仮説 |
| 見積もり | 1つ以上の測定値からの推定値を表す、古典的な値が返されます。 |
| 計測 | クォンタム測定が実行され、その結果がユーザーに返されます。 |
| 準備 | 指定された qubits のレジスタは、特定の状態に初期化されます |
| サンプル (英語) | 古典的な値は、ある分布からランダムに返されます。 |

関数の場合は、一般的な名詞を優先して動詞を使用しないことをお勧めします (以下の適切な名詞に関するガイダンスを参照してください)。または形容詞:

- `ConstantArray`
- `Head`
- `LookupFunction`

特に、ほとんどの場合は、必要に応じて過去の participles を使用することをお勧めします。これは、関数名が、クォンタムプログラム内の別の場所にあるアクションや副作用に強い接続されていることを示すためです。
たとえば、`ControlledOnInt` は動詞 "control" の part 分詞形式を使用して、関数が引数を変更するための形容詞として機能することを示します。
この名前には、以下で説明するように、組み込みの `Controlled` ファンクタのセマンティクスと照合するという追加の利点があります。
同様に、_エージェント名詞_を使用して、`Encode`に厳密に関連付けられた UDT の名前 `Encoder` の場合のように、操作名から関数名や UDT 名を作成できます。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 操作名には動詞を使用します。
- 関数名には名詞または形容詞を使用します。
- ユーザー定義型および属性に対して名詞を使用します。
- すべての呼び出し可能な名前については、`pascalCase`、`snake_case`、または `ANGRY_CASE`に `CamelCase` を使用します。 特に、呼び出し可能な名前が大文字で始まることを確認します。
- すべてのローカル変数に対して、`CamelCase`、`snake_case`、または `ANGRY_CASE`に `pascalCase` を使用します。 特に、ローカル変数の先頭が小文字であることを確認します。
- 関数名と操作名にアンダースコア `_` を使用しないようにします。階層の追加レベルが必要な場合は、名前空間と名前空間のエイリアスを使用します。

# <a name="examplestabexamples"></a>[例](#tab/examples)

|   | EnableAdfsAuthentication | description |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | 操作の効果を示すには、動詞 ("リフレクト") の使用をクリアします。 |
| ☒ | <s>`operation XRotation`</s> | 名詞句の使用は、操作ではなく、関数を提案します。 |
| ☒ | <s>`operation search_oracle`</s> | `snake_case` contravenes Q # 表記の使用。 |
| ☒ | <s>`operation Search_Oracle`</s> | 操作名の内部でのアンダースコアの使用 contravenes Q # 表記。 |
| ☑ | `function StatePreparationOracle` | 名詞句を使用すると、関数が操作を返すことがわかります。 |
| ☑ | `function EqualityFact` | 名詞 ("fact") の使用をクリアし、これが関数であることを意味します。 |
| ☒ | <s>`function GetRotationAngles`</s> | 動詞 ("get") を使用すると、これが操作であることが提案されます。 |
| ☑ | `newtype GeneratorTerm` | 名詞句の使用は、UDT コンストラクターを呼び出した結果を明確に表します。 |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | 動詞句を使用すると、UDT コンストラクターが操作であることがわかります。 |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | 名詞句を使用すると、属性の使用が伝えます。 |

***

### <a name="shorthand-and-abbreviations"></a>ショートハンドと省略形 ###

上記のアドバイスには、多くの形式があります。これは、クォンタムコンピューティングに共通し、広く使用されています。
特にターゲットコンピューターの操作に固有の操作については、既存の一般的なショートハンドを使用することをお勧めします。
たとえば、`ApplyX`ではなく名前 `X` を選択し、`RotateAboutZ`ではなく `Rz` します。
この短縮形を使用する場合、操作名はすべて大文字にする必要があります (例: `MAJ`)。

一般的に使用されている頭字語と頭字語 ("quantum フーリエ変換" など) の場合は、この規則を適用するときに注意が必要です。
頭字語と頭字語を完全な名前で使用するための一般的な .NET 表記規則に従うことをお勧めします。

- 2文字の頭字語と頭字語は大文字で名前が付けられます (例: "ビッグエンディアン" の場合は `BE`)。
- すべての長い頭字語と頭字語は、`CamelCase` (例: "クォンタムフーリエ変換" の `Qft`) に名前が付けられています。

このため、QFT を実装する操作は、ショート `QFT` として、または `ApplyQft`として書き出すことができます。

特に一般的に使用される操作と関数では、より長い形式の_別名_として短縮名を指定することをお勧めします。

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 必要に応じて、一般的に受け入れられ、広く使用されている短縮形を検討してください。
- 省略形には大文字を使用します。
- 短い (2 文字) 頭字語と頭字語には大文字を使用します。
- `CamelCase` は、頭字語と頭字語を長く (3 文字以上) 使用します。

# <a name="examplestabexamples"></a>[例](#tab/examples)

|   | EnableAdfsAuthentication | description |
|---|------|-------------|
| ☑ | `X` | 「$X $ transformation の適用」の短縮形 |
| ☑ | `CNOT` | "制御された-NOT" の短縮形 |
| ☒ | <s>`Cnot`</s> | 短縮形を `CamelCase`にすることはできません。 |
| ☑ | `ApplyQft` | 一般的な initialism "QFT" は、長い形式の名前の一部として表示されます。 |
| ☑ | `QFT` | 一般的な initialism "QFT" は、短縮名の一部として表示されます。 |



***


### <a name="proper-nouns-in-names"></a>名前の正しい名詞 ###

物理的には、最初に発行する人の後に名前が付けられることがよくありますが、ほとんどのまずでは、すべての人の名前とすべての履歴を理解することはできません。
物理的な名前付け規則に頼ると、その他の背景からのユーザーは一般的な操作と概念を使用するために、一見見えにくい名前の多くを学習する必要があるため、エントリに大きなバリアが生じる可能性があります。
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
このため、概念の発行履歴を記述する適切な名詞に対して、概念を説明する一般的な名詞を使用することをお勧めします。
具体的な例として、1つの制御されていないスワップとダブル制御されていない操作は、教育機関の資料では "Fredkin" および "Toffoli" 操作と呼ばれますが、主に Q # では `CSWAP` と `CCNOT`として識別されます。
どちらの場合も、API ドキュメントコメントは、適切な名詞に基づいて、適切なすべての引用文と同義の名前を提供します。

この設定は、適切な名詞の一部の使用が常に必要であるという点で特に重要です。 Q # は、多くの従来の言語で設定されているようになります。また、はブール型のロジックへの参照で `Bool` 型を表します。(ジョージ Boole)
同様に、いくつかのクォンタムの概念も同様の方法で名前が付けられます。これには、Q # 言語に組み込まれている `Pauli` 型も含まれます。
適切な名詞の使用を最小限に抑えて、そのような用途が重要ではない場合は、適切な名詞があまり避けられないような影響を軽減します。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance) 

次のことをお勧めします。

- 名前には適切な名詞を使用しないようにしてください。

# <a name="examplestabexamples"></a>[例](#tab/examples)

***

### <a name="type-conversions"></a>型変換 ###

Q # は厳密かつ厳密に型指定された言語であるため、1つの型の値は、型変換関数への明示的な呼び出しを使用して、別の型の値としてのみ使用できます。
これは、値が暗黙的に型を変更できるようにする言語 (例: 型の上位変換)、またはキャストを使用した場合とは対照的です。
その結果、型変換関数は、Q # ライブラリ開発で重要な役割を果たし、名前付けに関してよく発生する決定の1つを構成します。
ただし、型変換は常に_決定的_であるため、関数として記述することができます。そのため、上記のアドバイスに従ってください。
具体的には、型変換関数を動詞 (例: `ConvertToX`) または副詞 prepositional フレーズ (`ToX`) として指定しないことをお勧めしますが、変換元と変換先の型を示す形容詞 prepositional 指定語句として名前を付けることをお勧めします (`XAsY`)。
型変換関数の名前で配列の型を一覧表示する場合は、短縮 `Arr`をお勧めします。
例外的な状況を発生させないように、すべての型変換関数には `As` を使用して名前を付け、迅速に識別できるようにすることをお勧めします。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 関数が `X` 型の値を `Y`型の値に変換する場合は、`AsY` または `XAsY`のいずれかの名前を使用します。

# <a name="examplestabexamples"></a>[例](#tab/examples)

|   | EnableAdfsAuthentication | description |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | 前置詞 "to" は、関数ではなく操作を示す動詞句を生成します。 |
| ☒ | <s>`AsDouble`</s> | 入力の型は、関数名からは明確ではありません。 |
| ☒ | <s>`PauliArrFromBoolArr`</s> | 入力と出力の型が間違った順序で表示されています。 |
| ☑ | `ResultArrAsBoolArr` | 入力型と出力型はどちらも明確です。 |

***

### <a name="private-or-internal-names"></a>プライベートまたは内部名 ###

多くの場合、名前はライブラリまたはプロジェクトの内部での使用を目的としたものであり、ライブラリによって提供される API の保証された部分ではありません。
関数や操作に名前を付けて、内部のみのコードに誤った依存関係が明らかになるようにする場合は、このことを明確に示すことをお勧めします。
操作または関数が直接使用するためのものではなく、部分的なアプリケーションによって動作する一致する呼び出し元によって使用される必要がある場合は、部分的に適用される呼び出し可能な `_` で始まる名前を使用することを検討してください。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 関数、操作、またはユーザー定義型が Q # ライブラリまたはプログラムのパブリック API の一部ではない場合は、その名前が先頭のアンダースコア (`_`) で始まることを確認します。

# <a name="examplestabexamples"></a>[例](#tab/examples)

|   | EnableAdfsAuthentication | description |
|---|------|-------------|
| ☒ | <s>`ApplyDecomposedOperation_`</s> | アンダースコア `_` は、名前の末尾には記述できません。 |
| ☑ | `_ApplyDecomposedOperation` | 先頭にあるアンダースコア `_` は、この操作が内部でのみ使用されることを明確に示しています。 |

***

### <a name="variants"></a>△ ###

この制限は、Q # の将来のバージョンでは保持されない場合がありますが、現在のところ、関連する操作のグループ、またはその入力がサポートしている機能や、引数の具象型によって区別される関数のグループが存在することがあります。
これらのグループは、同じルート名を使用し、そのバリアントを示す 1 ~ 2 文字で区別できます。

| サフィックス | 意味 |
|--------|---------|
| `A` | `Adjoint` をサポートするために必要な入力 |
| `C` | `Controlled` をサポートするために必要な入力 |
| `CA` | `Controlled` と `Adjoint` をサポートするために必要な入力 |
| `I` | 入力または入力の型が `Int` |
| `D` | 入力または入力の型が `Double` |
| `L` | 入力または入力の型が `BigInt` |

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 関数または演算が、入力の型およびファンクタのサポートによって類似の関数や操作に関連付けられていない場合は、サフィックスを使用しないでください。
- 関数または演算が、入力の型およびファンクタのサポートによって類似の関数または演算に関連付けられている場合は、上記の表のようにサフィックスを使用して、バリアントを区別します。

# <a name="examplestabexamples"></a>[例](#tab/examples)

***

### <a name="arguments-and-variables"></a>引数と変数 ###

関数または操作の Q # コードの主な目的は、簡単に読み取り、理解できるようにすることです。
同様に、入力と型引数の名前は、指定された関数または引数の使用方法を伝達する必要があります。


# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- すべての変数と入力の名前については、`CamelCase`、`snake_case`、または `ANGRY_CASE`に `pascalCase` を使用します。
- 入力名はわかりやすい名前にする必要があります。可能な限り、1文字または2文字の名前は避けてください。
- 型引数を1つだけ受け取る演算と関数は、そのロールが明確である場合に `T` によってその型引数を示す必要があります。
- 関数または操作が複数の型引数を受け取る場合、または1つの型引数の役割が明確でない場合は、型ごとに `T` で始まる短い大文字の単語 (例: `TOutput`) を使用することを検討してください。
- 引数と変数名に型名を含めないでください。この情報は、開発環境によって提供されることがあります。
- スカラー型をリテラル名 (`flagQubit`) で表し、配列型を複数形 (`measResults`) で表します。
  特に qubits の配列の場合は、何らかの方法で密接に関連付けられている qubits のシーケンスを名前が参照する `Register` によって、このような型を指定することを検討してください。
- 配列へのインデックスとして使用される変数は `idx` で始まり、単数形にする必要があります (例: `things[idxThing]`)。
  特に、1文字の変数名をインデックスとして使用するのは避けてください。少なくとも `idx` を使用することを検討してください。
- 配列の長さを保持するために使用される変数は `n` で始まる必要があります (例: `nThings`)。

# <a name="examplestabexamples"></a>[例](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>ユーザー定義型の名前付き項目 ###

ユーザー定義型の名前付き項目には、UDT コンストラクターへの入力でも `CamelCase`として名前を付ける必要があります。
これは、アクセサー表記 (例: `callable::Apply`) やコピーと更新の表記 (`set arr w/= Data <- newData`) を使用する場合に、名前付き項目をローカルスコープ変数への参照から明確に分離するために役立ちます。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- UDT コンストラクターの名前付き項目には、`CamelCase`という名前を付ける必要があります。つまり、先頭は大文字にする必要があります。
- 操作に解決される名前付き項目は、動詞フェーズとして名前を付ける必要があります。
- 操作に解決されない名前付きの項目には、名詞句として名前を付ける必要があります。
- 操作をラップする Udt の場合は、`Apply` という名前の単一の項目を定義する必要があります。

# <a name="examplestabexamples"></a>[例](#tab/examples)

|   | 短い | description |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | 名前 `Apply` は、名前付きの項目が操作であることを示す、`CamelCase`形式の動詞の語句です。 |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | 名前付き項目の先頭は大文字である必要があります。 |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | 関数に解決される名前付きの項目は、動詞句としてではなく、名詞句として名前を付ける必要があります。 |

***

## <a name="input-conventions"></a>入力規則 ##

開発者が操作または関数を呼び出すときは、その操作または関数に対するさまざまな入力を特定の順序で指定する必要があります。これにより、開発者がライブラリを利用するために直面する認識負荷を増やすことができます。
具体的には、多くの場合、入力順序を記憶するタスクは、「クォンタムアルゴリズムの実装のプログラミング」の作業には煩わされません。
豊富な IDE サポートではこれを大きな範囲に抑えることができますが、一般的な規則の設計と準拠が優れているため、API による認識の負荷を最小限に抑えることもできます。

可能な場合は、操作または関数によって期待される入力の数を減らすことが役に立つことがあります。これにより、各入力のロールが、その操作や関数を呼び出す開発者と、後でそのコードを読み取っている開発者の両方にとってより明確になります。
特に、操作または関数の引数の数を減らすことができない場合、または適切でない場合は、入力の順序を予測するときにユーザーが直面する驚きを最小限にするために、一貫した順序を付けることが重要です。

カリー化 f (x, y) ≡ f (x) (y) の汎化として部分的なアプリケーションを考えることから、多くの場合、入力の順序付け規則をお勧めします。
したがって、最初の引数を部分的に適用すると、適切な場合は常に独自の権限を持つ呼び出し可能になります。
この原則に従うと、次の引数の順序を使用することを検討してください。

- 角度、累乗のベクトルなど、従来の呼び出し不可能な引数。
- 呼び出し可能な引数 (関数と引数)。
  関数と演算の両方を引数として使用する場合は、関数の後に操作を配置することを検討してください。
- 呼び出し可能な引数によって処理されるコレクションは、`Map`、`Iter`、`Enumerate`、および `Fold`の場合と同様の方法で動作します。
- コントロールとして使用される qubit 引数。
- ターゲットとして使用される qubit 引数。

操作 `ApplyPhaseEstimationIteration` を検討してください。これは、角度と oracle を使用するフェーズ推定で使用し、さまざまなスケールファクターの配列によって変更された `Rz` に角度を渡して、oracle のアプリケーションを制御します。
次のように、入力を `ApplyPhaseEstimationIteration` に順序付けます。

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
意外なことを最小限に抑えるための特別なケースとして、一部の関数と操作は、`Adjoint` 組み込みの関数と `Controlled`の動作を模倣しています。
たとえば、`ControlledOnInt<'T>` の型が `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`の場合、`ControlledOnInt<Qubit[]>(5, _)` は `Controlled` のファンクタと同じように動作しますが、コントロールレジスタが state $ \ket{5} = \ket{101}$ を表しているという条件に基づいています。
したがって、開発者は、呼び出し可能なが最後に変換されるように `ControlledOnInt` 入力を要求し、結果として得られる操作は、`Controlled` のファンクタの出力の後に入力 `(Qubit[], 'T)` と同じ順序で---する必要があります。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 部分アプリケーションの使用と一貫性のある入力順序を使用します。
- 組み込みのファンクターと一貫性のある入力順序を使用します。
- すべての古典入力をクォンタム入力の前に配置します。

# <a name="examplestabexamples"></a>[例](#tab/examples)

***

## <a name="documentation-conventions"></a>ドキュメントの表記規則 ##

Q # 言語では、特別に書式設定されたドキュメントコメントを使用して、操作、関数、およびユーザー定義型にドキュメントを添付できます。
これらのドキュメントコメントは、3つのスラッシュ (`///`) で表され、各操作、関数、およびユーザー定義型の目的、それぞれに必要な入力、およびなどを記述するために使用できる小さな[Docfx-Flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)ドキュメントです。
Quantum Development Kit に用意されているコンパイラは、これらのコメントを抽出し、それらのコメントを使用して、 https://docs.microsoft.com/quantum 時と同様の横組みドキュメントを作成します。
同様に、Quantum 開発キットで提供されている言語サーバーは、これらのコメントを使用して、ユーザーが Q # コード内のシンボルにマウスポインターを置いたときにヘルプを提供します。
ドキュメントコメントを使用すると、このドキュメントの他の規則を使用して簡単には表現できない詳細情報を提供することで、ユーザーがコードを理解するのに役立ちます。

<div class="nextstepaction">
    [ドキュメントコメント構文のリファレンス](xref:microsoft.quantum.language.statements#documentation-comments)
</div>

この機能を効果的に使用してユーザーを支援するには、ドキュメントコメントを記述する際に注意することをお勧めします。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance)

次のことをお勧めします。

- 各パブリック関数、操作、およびユーザー定義型は、ドキュメントコメントの直前に記述する必要があります。
- 各ドキュメントコメントには、少なくとも次のセクションが含まれている必要があります。
    - Summary
    - Input (入力)
    - 出力 (該当する場合)
- すべての概要が2文以下であることを確認します。 より多くの領域が必要な場合は、`# Summary` の直後に `# Description` のセクションを入力します。詳細については、こちらを参照してください。
- すべてのクライアントが概要で TeX 表記をサポートするわけではないため、適切な場合は、集計に数値を含めないでください。 Prose ドキュメント (TeX や Markdown など) を書き込む場合は、長い行の長さを使用することをお勧めします。
- `# Description` セクションで、関連するすべての数値式を指定します。
- 入力を記述するときは、コンパイラによって推論される可能性があるため、各入力の型を繰り返さないでください。
- 必要に応じて、それぞれ独自の `# Example` セクションに例を入力します。
- コードを一覧表示する前に、各例を簡単に説明します。
- 関連するすべての教育機関向けの出版物 (例: 論文、手続き、ブログ投稿、および代替の実装) については、リンクの箇条書きリストとして、`# References` セクションを参照してください。
- 可能であれば、すべての引用リンクが永続的で不変の識別子になるようにしてください (DOIs またはバージョン管理された arXiv の番号)。
- 演算または関数が、ファンクタバリアントによって他の操作や関数に関連付けられている場合は、[`# See Also`] セクションで他のバリアントを箇条書きとして一覧表示します。
- レベル 1 (`/// #`) のセクション間に空白のコメント行を残しておきますが、レベル 2 (`/// ##`) のセクションの間に空白行を入れないでください。

# <a name="examplestabexamples"></a>[例](#tab/examples)

#### <a name=""></a>☑ ####

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

## <a name="formatting-conventions"></a>書式設定の規則 ##

前述の提案に加えて、一貫性のある書式設定規則を使用するためにコードをできるだけ読みやすくするために役立ちます。
このような書式設定規則は、本質的にはやや自由で、個人的には見栄えがよくなります。
それでも、コラボレーターのグループ内では一貫した書式指定規則を維持することをお勧めします。また、Quantum 開発キット自体などの大規模な Q # プロジェクトの場合は特にそうです。
これらの規則は、Q # コンパイラと統合された書式設定ツールを使用して自動的に適用できます。

# <a name="guidancetabguidance"></a>[ガイダンス](#tab/guidance) 

次のことをお勧めします。

- 移植性を確保するには、タブの代わりに4つのスペースを使用します。
  たとえば、VS Code では次のようになります。
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- 79文字の行が適切な位置に折り返されます。
- バイナリ演算子の前後にスペースを使用します。
- 型の注釈に使用されるコロンの両側でスペースを使用します。
- 配列と組リテラルで使用するコンマの後に1つのスペースを使用します (例: 関数と操作への入力で)。
- 関数、操作、または UDT の名前の後、または属性宣言の `@` 後にスペースを使用しないでください。
- 各属性の宣言は、独自の行に配置する必要があります。

# <a name="examplestabexamples"></a>[例](#tab/examples)

|   | 短い | description |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | バイナリ演算子の前後にスペースを使用します。 |
| ☒ | <s>`target:Qubit`</s> | 注釈のコロンを囲むにはスペースを使用します。 |
| ☑ | `Example(a, b, c)` | 入力タプル内の項目は、読みやすくするために適切に配置されています。 |
| ☒ | <s>`Example (a, b, c)`</s> | 関数、操作、または UDT の名前の後にスペースは表示されません。 |

***

