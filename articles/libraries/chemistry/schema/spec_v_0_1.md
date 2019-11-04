---
title: Broombridge スキーマの仕様
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185360"
---
# <a name="broombridge-specification-v01"></a>Broombridge の仕様 v 0.1 #

このドキュメントでは、"必要"、"NOT NOT"、"REQUIRED"、"where"、"not NOT"、"be"、"NOT not"、"推奨"、"may"、および "OPTIONAL" を、 [RFC 2119](https://tools.ietf.org/html/rfc2119)で説明されているように解釈することが重要です。

見出しが "NOTE"、"情報"、または "警告" のサイドバーは役に立つものです。

## <a name="introduction"></a>はじめる ##

このセクションは有益です。

Broombridge ドキュメントは、クォンタムシミュレーションとプログラミングツールチェーンを使用して処理するために、クォンタムの化学でシミュレーションの問題のインスタンスを伝えることを目的としています。

## <a name="serialization"></a>シリアル化 ##

このセクションは non-normative です。

Broombridge ドキュメントは、 [RFC 4627](https://tools.ietf.org/html/rfc4627)セクション2.2 で説明されているように、JSON オブジェクトを表す[yaml 1.2 ドキュメント](http://yaml.org/spec/)としてシリアル化する必要があります。
YAML にシリアル化されたオブジェクトには、値が `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`で、JSON スキーマ draft-06 仕様 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] に従って有効である必要があるプロパティ `"$schema"` が必要です。

この仕様の残りの部分では、"Broombridge オブジェクト" は Broombridge YAML ドキュメントから逆シリアル化された JSON オブジェクトを参照します。

特に明記されていない限り、このドキュメントで明示的に指定されている以外のプロパティをオブジェクトに追加することはできません。

## <a name="additional-definitions"></a>用語の追加定義 ##

このセクションは non-normative です。

### <a name="quantity-objects"></a>Quantity オブジェクト ###

このセクションは non-normative です。

_Quantity オブジェクト_は JSON オブジェクトであり、値がテーブル1に示されている許可値の1つである `units` プロパティを持つ必要があります。

Quantity オブジェクトは、`units` プロパティに加えて1つのプロパティ `value` がある場合、_単純な quantity オブジェクト_です。
`value` プロパティの値には数値を指定する必要があります。

Quantity オブジェクトは、`units` プロパティに加えて `lower` および `upper` プロパティがある場合に、制限された_quantity オブジェクト_です。
`lower` プロパティと `upper` プロパティの値は数値である必要があります。
範囲指定された quantity オブジェクトには、値が数値であるプロパティ `value` が存在する場合があります。

Quantity オブジェクトは、プロパティ `format` と、その `units` プロパティに加えて `values` プロパティがある場合に、_スパース配列の quantity オブジェクト_です。
`format` の値は、`sparse`文字列である必要があります。
`values` プロパティの値は配列である必要があります。
`values` の各要素は、スパース配列の量のインデックスと値を表す配列である必要があります。

スパース配列の quantity オブジェクトの各要素のインデックスは、スパース配列の quantity オブジェクト全体で一意である必要があります。
値が `0`のインデックスが存在する場合、パーサーは、そのインデックスがまったく存在しないスパース配列の quantity オブジェクトと同じように、スパース配列の quantity オブジェクトを処理する必要があります。


Quantity オブジェクトは、

- 単純な quantity オブジェクト
- 制限付き数量オブジェクト。
- スパース配列の quantity オブジェクト。


### <a name="examples"></a>例 ###

このセクションは有益です。

$ 1.9844146837\,\mathrm{Ha} $ を表す単純な数量:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

範囲 $ [-7,-6\,] に対する一様分布を表す、\mathrm{Ha} $ の範囲外の数量。

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

次に示すのは、要素 `[1, 2]` `hello` と等しく、要素 `[3, 4]` `world`と等しい場合の疎配列の数量です。

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>書式セクション ##

このセクションは non-normative です。

Broombridge オブジェクトには、`version`という1つのプロパティを持つ JSON オブジェクトを値として持つプロパティ `format` が必要です。
`version` プロパティには `"0.1"`値を指定する必要があります。

### <a name="example"></a>例 ###

このセクションは有益です。

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>整数セットセクション ##

このセクションは non-normative です。

Broombridge オブジェクトには、値が JSON 配列であるプロパティ `integral_sets` が必要です。
`integral_sets` プロパティの値の各項目は、このセクションの残りの部分で説明されているように、1つの積分のセットを記述する JSON オブジェクトである必要があります。
このセクションの残りの部分では、"整数セットオブジェクト" という用語は、Broombridge オブジェクトの `integral_sets` プロパティの値の項目を参照します。

各整数セットオブジェクトには、値が JSON オブジェクトである `metadata` プロパティが必要です。
`metadata` の値には、空の JSON オブジェクト (つまり、`{}`) を指定することも、実装で定義されている追加のプロパティを含めることもできます。

### <a name="hamiltonian-section"></a>Hamiltonian セクション ###

#### <a name="overview"></a>ユーザーとグループ ####

このセクションは有益です。

各整数セットオブジェクトの `hamiltonian` プロパティは、特定の量子化学の問題の Hamiltonian について説明します。これは、1つの単語と2つの単語の項を、実際の数値の疎配列として一覧表示することによって記述します。
各整数 set オブジェクトによって記述される Hamiltonian 演算子は、という形式になります。

$ $ H = \ sum\_\{i、j\}\ sum\_{/sigma\ in\\{\uparrow, ij\\\_}} H \{\}\{a ^\}/ダガー \_{i,、\ sigma} a\_{j, \ sigma} + \ frac{1}{2}-sum\_\{i, j, k, l\}\ sum\_{-シグマ, \r ho-in\\{\uparrow, \ downarrow\\}} h\_{ijkl} a ^-ダガー\_{i, \ sigma} a ^ ダガー\_{k, \r ho} a\_{l, \r ho} a\_{j, \ sigma}, $ $

ここでは、Mulliken 規約で _ {ijkl} = (ij | kl ダイバージェンス) $ を $h します。

わかりやすくするために、1 ~ 電子の用語は

$ $ h_ {ij} = \ int {\mathrm d} x \ psi ^ *\_i (x) \ 左 (\ frac{1}{2}\n abla ^ 2 + \ sum\_{A} \frac{Z\_A} {| x-x\_A |} \ right) \ psi\_j (x)、$ $

そして、次の2つの用語があります。

$ $ h\_\{ijkl\} = \ iint \{\mathrm d\}x ^ 2 \ psi ^\{\*\}\_i (x\_1) \ psi\_j (x\_1) & frac\{1\}\{\|x\_1-x\_2\|\}\ psi\_k ^\{\*\}(x\_2) \ psi\_l (x\_2)。
$$

`integral_sets` プロパティの各要素の[`basis_set` プロパティ](#basis-set-object)について説明したように、使用されるベース関数が実際の値であることをさらに明示的に想定しています。
これにより、用語の間で次の symmetries を使用して、Hamiltonian の表現を圧縮することができます。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>目次 ####

このセクションは non-normative です。

各整数セットには、値が JSON オブジェクトである `hamiltonian` プロパティが必要です。
`hamiltonian` プロパティの値は Hamiltonian オブジェクトとして知られており、このセクションの残りの部分で説明するように、プロパティ `one_electron_integrals` と `two_electron_integrals` を持っている必要があります。
Hamiltonian オブジェクトには、プロパティ `particle_hole_representation`を含めることもできます。
存在する場合、`particle_hole_representation` の値は、このセクションの残りの部分で説明されている形式に従う必要があります。

##### <a name="one-electron-integrals-object"></a>1-電子積分オブジェクト #####

このセクションは non-normative です。

Hamiltonian オブジェクトの `one_electron_integrals` プロパティは、インデックスが2つの整数で、値が数値であるスパース配列の数量である必要があります。
すべての用語には、`i >= j``[i, j]` インデックスが必要です。

> 付箋これは $h _ {ij} = h_ {ji} $ という対称を反映しています。これは、Hamiltonian が Hermitian であるという事実の結果です。


###### <a name="example"></a>例 ######

このセクションは有益です。

次の疎配列の量は、Hamiltonian $ $ H = \ left (-5.0 (a ^\{\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{/ダガー\}\_{1, \ down←} a\_{1 を表します。、\ down\uparrow}}) + 0.17 (a ^\{\}\_{2, a\_{1, \uparrow} + a ^\{\}{1, \uparrow} a \_{2, \uparrow} + a ^\_\ ダガー\{\}{2, \ down←} a\_{1, \ down←} + a ^\{\ ダガー\}\_{1, \ down←} a\_{2, \ down←}), \mathrm{Ha}.
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> Broombridge は、1から始まるインデックスを使用します。


##### <a name="two-electron-integrals-object"></a>2つの電子積分オブジェクト #####

このセクションは non-normative です。

Hamiltonian オブジェクトの `two_electron_integrals` プロパティは、`index_convention`という1つの追加のプロパティを持つスパース配列の数量である必要があります。
`two_electron_integrals` の値の各要素には、4つのインデックスが必要です。

各 `two_electron_integrals` プロパティには、`index_convention` プロパティが必要です。
`index_convention` プロパティの値は、表1に示されている許可された値のいずれかである必要があります。
`index_convention` の値が `mulliken`の場合、`two_electron_integrals` スパース配列の数量の各要素に対して、Broombridge ドキュメントを読み込むパーサーは、2-3-電子 $h オペレーター (_ {i, j, k, l} a ^ \dagger_i a ^ & daggera_k a_l $) と等しい Hamiltonian term をインスタンス化する必要があります。$i $、$j $、$k $、および $l $ は、範囲内の整数である必要があります。1から整数セットオブジェクトの `n_electrons` プロパティで指定された原子の数までの整数を指定します。 $h _ {i, j, k, l} $ は、疎配列の量の要素 `[i, j, k, l, h(i, j, k, l)]` です。

###### <a name="symmetries"></a>Symmetries ######

このセクションは non-normative です。

`two_electron_integrals` オブジェクトの `index_convention` プロパティが `mulliken`と等しい場合、インデックス `[i, j, k, l]` を持つ要素が存在する場合、次のインデックスは `[i, j, k, l]`と等しい場合を除き、存在してはなりません。

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> `index_convention` プロパティは疎数量オブジェクトであるため、異なる要素でインデックスを繰り返し使用することはできません。
> 特に、`[i, j, k, l]` インデックスを持つ要素が存在する場合、他の要素にそのインデックスを含めることはできません。


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>例 #######

このセクションは有益です。

次のオブジェクトは、Hamiltonian を指定します。

$ $ H = \frac12 \ sum\_{/シグマ, \r ho\ in\\{\uparrow,-downarrow\\}} \ biggr (1.6 a ^ {-dagger}\_{1, \ sigma} a ^ {-dagger}\_{1, \r ho} a\_{1, \r ho} a\_{1, \ sigma{1}-0.1 a ^ {-dagger}\_{6, \ sigma} a ^ {\ dagger}\_{1, \r ho} a\_{3, \r ho} a\_{2, \ sigma\_a ^ {-dagger}\_{6, \ sigma} a ^ {-0.1 dagger} a ^ {1, \r ho} a\_{2, \r ho}\_a {3,、\ sigma{1}-0.1 a ^ {\ dagger}\_{1, \ sigma} a ^ {-dagger}\_{6, \r ho} a\_{3, \r ho} a\_{3, \r ho} a ^ {1, \ sigma} a ^ {1, 0.1 \ sigma} a ^ {\_/dagger}\_{6, \r ho} a\_{2, \r ho} a\_{3, \ sigma} $ $ $ $-0.1 a ^ {\ dagger}\_{3, \ sigma} a ^ {-dagger}\_{2, \r ho} a\_{6, \r ho} a\_{1,/sigma} a ^ {-dagger}\_{3, \ sigma} a ^ {& dagger}\_{2 0.1, \r ho} a\_{1, \r ho} a\_{6,-sigma{1}-0.1 a ^ {-dagger}\_{2,/sigma} a ^ {-dagger}\_{3, \r ho} a\_{6, \r ho} a\_{1, \ sigma} a\_{1,-sigma} {2 0.1,、\ sigma} a ^ {-dagger}\_{3, \r ho} a\_{1, \r ho} a\_{6, \ sigma{1} \ biggr)\\, \T extrm{ha{2}.
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a>パーティクル–穴表現オブジェクト #####

このセクションは non-normative です。

パーティクル–穴表現オブジェクトは、格納されている積分がパーティクル穴の表現に対して定義されていることを指定します。この場合、作成演算子と annihilation 演算子では、使用されている参照状態 (たとえば、[excitations]) から離れた場所にが記述されます。Fock 状態です。
オブジェクトは省略可能です。
オブジェクトが指定されていない場合、Hamiltonian は、パーティクル穴の表現で指定されていないと解釈されます。
存在する場合、`particle_hole_representation` の値は、インデックスが4つの整数で、値が数値と文字列であるスパース配列の quantity オブジェクトである必要があります。
各要素の値の文字列部分には `'+'` および `'-'` 文字だけを含める必要があります。これは、用語の特定の係数が、パーティクルの穴表現で作成または annihilation 演算子であるかどうかを指定します。  たとえば `"-+++"` サイト $i $ で作成された穴と、サイト $j、k $、$l $ に作成されているパーティクルです。

> [!NOTE]
> `particle_hole_representation` の値がスパース配列の quantity オブジェクトであるため、`unit` プロパティと `format` プロパティを指定する必要があります。
> 表1に、許容される単位が含まれています。
> `format` プロパティは必須であり、Hamiltonian 係数が高密度またはスパース配列として指定されているかどうかを示します。
> 現在のバージョンでは、スパース配列のみがサポートされています。指定されていない要素はすべて $0 $ ですが、将来のバージョンでは `format` プロパティの追加の値のサポートが追加される場合があります。

### <a name="initial-state-section"></a>初期状態セクション ###

Initial_state_suggestion オブジェクトは、指定された Hamiltonian の最初のクォンタム状態を指定します。 このオブジェクトは、JSON `state` オブジェクトの配列である必要があります。

#### <a name="state-object"></a>状態オブジェクト ####

各状態は、占有の法則を表します。 各状態オブジェクトには、文字列を含む `label` プロパティが必要です。 各状態オブジェクトには、ベース状態の配列とその正規化されていない振幅を含む `superposition` プロパティが必要です。

たとえば、初期状態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {-dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2,}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {-dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ down矢印}) + 0.2 (a ^ {-dagger}\_{1, \uparrow}a ^ {/dagger}\_{3, \uparrow}a ^ {/dagger}\_{2, \ket})} {\ sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}}{0} $ $表される
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a>ベースセットオブジェクト ####

このセクションは non-normative です。

各整数セットオブジェクトは、`basis_set` プロパティを持つことができます。
存在する場合、`basis_set` プロパティの値は、`type` と `name`の2つのプロパティを持つオブジェクトである必要があります。

`basis_set` プロパティの値によって識別されるベース関数は、実際の値である必要があります。

> [!NOTE]
> この仕様の将来のバージョンでは、すべての基礎関数が実際の値であることを前提としています。

## <a name="tables-and-lists"></a>テーブルとリスト ##

### <a name="table-1-allowed-physical-units"></a>表 1 許可される物理ユニット ###

このセクションは non-normative です。

単位を指定する文字列は、次のいずれかである必要があります。

- `hartree`
- `ev`

パーサーとプロデューサーは、次の単純な quantity オブジェクトを同等として扱う必要があります。

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>表 2 許可されるインデックスの規則 ###

このセクションは non-normative です。

インデックス規則を指定する文字列は、次のいずれかである必要があります。

- `mulliken`

このセクションは有益です。

この仕様の将来のバージョンでは、追加のインデックス規則が導入される可能性があります。

#### <a name="interpretation-of-index-conventions"></a>インデックス規則の解釈 ####

このセクションは有益です。
