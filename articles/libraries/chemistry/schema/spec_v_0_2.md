---
title: Broombridge スキーマ仕様 (ver 0.2)
description: Microsoft quantum 化学ライブラリの Broombridge 量子化学スキーマ v 0.2 の仕様について詳しく説明します。
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907275"
---
# <a name="broombridge-specification-v02"></a>Broombridge Specification v 0.2 #

このドキュメントでは、"必要"、"NOT NOT"、"REQUIRED"、"where"、"not NOT"、"be"、"NOT not"、"推奨"、"may"、および "OPTIONAL" を、 [RFC 2119](https://tools.ietf.org/html/rfc2119)で説明されているように解釈することが重要です。

見出しが "NOTE"、"情報"、または "警告" のサイドバーは役に立つものです。

## <a name="introduction"></a>はじめに ##

このセクションは有益です。

Broombridge ドキュメントは、クォンタムシミュレーションとプログラミングツールチェーンを使用して処理するために、クォンタムの化学でシミュレーションの問題のインスタンスを伝えることを目的としています。

## <a name="serialization"></a>シリアル化 ##

このセクションは non-normative です。

Broombridge ドキュメントは、 [RFC 4627](https://tools.ietf.org/html/rfc4627)セクション2.2 で説明されているように、JSON オブジェクトを表す[yaml 1.2 ドキュメント](http://yaml.org/spec/)としてシリアル化する必要があります。
YAML にシリアル化されたオブジェクトには、値が `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`で、JSON スキーマ draft-06 仕様 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] に従って有効である必要があるプロパティ `"$schema"` が必要です。

この仕様の残りの部分では、"Broombridge オブジェクト" は Broombridge YAML ドキュメントから逆シリアル化された JSON オブジェクトを参照します。

特に明記されていない限り、このドキュメントで明示的に指定されている以外のプロパティをオブジェクトに追加することはできません。

## <a name="additional-definitions"></a>追加の定義 ##

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
`version` プロパティには `"0.2"`値を指定する必要があります。

### <a name="example"></a>例 ###

このセクションは有益です。

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>問題の説明セクション ##

このセクションは non-normative です。

Broombridge オブジェクトには、値が JSON 配列であるプロパティ `problem_description` が必要です。
`problem_description` プロパティの値の各項目は、このセクションの残りの部分で説明されているように、1つの積分のセットを記述する JSON オブジェクトである必要があります。
このセクションの残りの部分では、"問題説明オブジェクト" という用語は、Broombridge オブジェクトの [`problem_description`] プロパティの値の項目を指します。

問題説明オブジェクトにはそれぞれ、JSON オブジェクトの値を持つプロパティ `metadata` が必要です。
`metadata` の値には、空の JSON オブジェクト (つまり、`{}`) を指定することも、実装で定義されている追加のプロパティを含めることもできます。

### <a name="hamiltonian-section"></a>Hamiltonian セクション ###

#### <a name="overview"></a>概要 ####

このセクションは有益です。

各問題説明オブジェクトの [`hamiltonian`] プロパティには、1つまたは2つの単語の項を実数の疎配列として一覧表示することによって、特定の量子化学の問題の Hamiltonian が記述されています。
各問題の説明オブジェクトによって記述される Hamiltonian 演算子は、

$ $ H = \ sum\_\{i、j\}\ sum\_{/sigma\ in\\{\uparrow, ij\\\_}} H \{\}\{a ^\}/ダガー \_{i, \ sigma} a\_{j, \ sigma} +-frac{1}{2}-sum\_\{i、j、k、l\}-sum\_{/σ、\r ho\ in\\{\uparrow, \ downarrow\\}} H\_{ijkl} a ^\_{i, \ sigma} a ^ ダガー\_{k, \r ho} a\_{l, \r ho} a\_{j, \ sigma}, $ $

ここでは、Mulliken 規約で _ {ijkl} = (ij | kl ダイバージェンス) $ を $h します。

わかりやすくするために、1 ~ 電子の用語は

$ $ h_ {ij} = \ int {\mathrm d} x \ psi ^ *\_i (x) \ 左 (\ frac{1}{2}\n abla ^ 2 + \ sum\_{A} \frac{Z\_A} {| x-x\_A |} \ right) \ psi\_j (x)、$ $

そして、次の2つの用語があります。

$ $ h\_\{ijkl\} = \ iint \{\mathrm d\}x ^ 2 \ psi ^\{\*\}\_i (x\_1) \ psi\_j (x\_1) \ frac\{1\}\{\|x\_1-x\_2\|\}\ psi\_k ^\{\*\}(x\_2) \ psi\_l (x\_2)。
$$

`integral_sets` プロパティの各要素の[`basis_set` プロパティ](#basis-set-object)について説明したように、使用されるベース関数が実際の値であることをさらに明示的に想定しています。
これにより、用語の間で次の symmetries を使用して、Hamiltonian の表現を圧縮することができます。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>内容 ####

このセクションは non-normative です。

問題説明オブジェクトにはそれぞれ、JSON オブジェクトの値を持つプロパティ `hamiltonian` が必要です。
`hamiltonian` プロパティの値は Hamiltonian オブジェクトとして知られており、このセクションの残りの部分で説明するように、プロパティ `one_electron_integrals` と `two_electron_integrals` を持っている必要があります。

各問題の説明オブジェクトには、値が単純な quantity オブジェクトである `coulomb_repulsion` プロパティが必要です。
各問題の説明オブジェクトには、値が単純な quantity オブジェクトである `energy_offet` プロパティが必要です。
> 付箋`coulomb_repulsion` と `energy_offet` の値を一緒に追加すると、Hamiltonian の id 用語がキャプチャされます。

##### <a name="one-electron-integrals-object"></a>1-電子積分オブジェクト #####

このセクションは non-normative です。

Hamiltonian オブジェクトの `one_electron_integrals` プロパティは、インデックスが2つの整数で、値が数値であるスパース配列の数量である必要があります。
すべての用語には、`i >= j``[i, j]` インデックスが必要です。

> 付箋これは $h _ {ij} = h_ {ji} $ という対称を反映しています。これは、Hamiltonian が Hermitian であるという事実の結果です。


###### <a name="example"></a>例 ######

このセクションは有益です。

次の疎配列の量は、Hamiltonian $ $ H = \ left (-5.0 (a ^\{\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\ ダガー\}\_{1, \uparrow}\{\}{2, \uparrow} a \_{1, + a ^\_/ダガー\{\}{1, \uparrow} a \_{2, 0.17\_\uparrow} + a ^\_/ダガー\{\}{2。 \_{1, a {2, \ down←} a\_{1, \ down←} + a ^\{\ ダガー\}\_{1, \ down←} a\_{2, \ down←}), \mathrm{Ha}.\\
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
`index_convention` の値が `mulliken`の場合、`two_electron_integrals` sparse 配列の数量の各要素に対して、Broombridge ドキュメントを読み込むパーサーは、2-3-電子オペレーター $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $。ここで $i $、$j $、$k $、および $l $ は少なくとも1の値の整数である必要があります。 $h _ {i, j, k, l} $ は、疎配列の量の要素 `[i, j, k, l, h(i, j, k, l)]` です。

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

$ $ H = \frac12 \ sum\_{/シグマ, \r ho\ in\\{\uparrow, (& a)\\}} \ biggr (1.6 a ^ {\ dagger}\_{1, \ sigma} a ^ {-dagger} a ^ {1, \r ho} a\_{1, \r ho} a\_{\_1, \ sigma-0.1 a ^ {-dagger}\_{6, \ sigma} a ^ {-dagger}\_{1, \r ho} a\_{3, \r ho} a\_{3, \r ho} a ^ {6, \ sigma} a ^ {6, \ sigma} a ^ {/dagger}\_{1, \r ho} a\_{2 0.1\_, \r ho} a\_{3, \ sigma-0.1 a ^ {-dagger}\_{1, \ sigma} a ^ {\ dagger}\_{6, \r ho} a\_{3, \r ho} a\_{2, \ sigma} a ^ {-dagger}\_{1,-sigma} a ^ {-dagger}\_0.1 {6, \r ho} a\_{2, \r ho} a\_{3, \ sigma} $ $ $ $-0.1 a ^ {-dagger}\_{3, \ sigma} a ^ {\ dagger}\_{2, \r ho} a\_{6, \r ho} a\_{1, \ sigma-0.1 a ^ {-dagger}\_{3,、\ sigma} a ^ {\ dagger}\_{2, \r ho} a\_{1, \r ho} a\_{1, \r ho} a {6, \ sig\_0.1 ma} a ^ {2,-sigma} a ^ {& dagger}\_{3, \r ho} a\_{6, \r ho} a\_{1,/sigma\_-0.1 a ^ {-dagger}\_{2,/sigma} a ^ {-dagger}\_{3, \r ho} a {1, \r ho} a\_{6,/sigma/biggr)\\, \T extrm{ha$。
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

### <a name="initial-state-section"></a>初期状態セクション ###

このセクションは non-normative です。

値が JSON 配列である `initial_state_suggestion` オブジェクトは、指定された Hamiltonian に対して対象となる初期クォンタムの状態を指定します。 `initial_state_suggestion` プロパティの値の各項目は、このセクションの残りの部分で説明するように、1つのクォンタム状態を記述する JSON オブジェクトである必要があります。
このセクションの残りの部分では、"state オブジェクト" という用語は、Broombridge オブジェクトの `initial_state_suggestion` プロパティの値の項目を参照します。

#### <a name="state-object"></a>状態オブジェクト ####

このセクションは non-normative です。

各状態オブジェクトには、文字列を含む `label` プロパティが必要です。 各状態オブジェクトには、`method` プロパティが必要です。 `method` プロパティの値は、表3に示されている許可された値のいずれかである必要があります。
各状態オブジェクトには、値が単純な quantity オブジェクトである必要がある `energy` プロパティが存在する場合があります。

`method` プロパティの値が `sparse_multi_configurational`場合、状態オブジェクトには、ベース状態の配列とその正規化されていない振幅を含む `superposition` プロパティが必要です。

たとえば、初期状態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\ dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ket}){0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {-dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ down\_}) + 0.2 (a ^ {/dagger} {1, \uparrow}a ^ {\ dagger}\_{3, \uparrow}a ^ {\ dagger}\_{2, \ down})} {\ sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}$ $ $ $ \ket{E} $ がエネルギー $0.987 \T extrm{ha} $ を持つ $ $ は、によって表されます。
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

`method` プロパティの値が `unitary_coupled_cluster`の場合、状態オブジェクトには、JSON オブジェクトの値を持つ `cluster_operator` プロパティが必要です。
JSON オブジェクトには、値が basis 状態である `reference_state` プロパティが必要です。
JSON オブジェクトには、1つの本体のクラスター演算子とその振幅の配列を値として持つ `one_body_amplitudes` のプロパティがある場合があります。
JSON オブジェクトには、2つの本体のクラスター演算子とその振幅の配列を値として持つ `two_body_amplitudes` のプロパティがある場合があります。
基本的な状態とその正規化されていない振幅の配列を格納します。

たとえば、状態 $ $ \ket{\text{reference}} = (a ^ {\ dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ down}) \ket{0}, $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}, $ $

$ $ T = 0.1 a ^ {\ dagger}\_{3, \uparrow}a\_{2, \ down\uparrow}a} + 0.2 a ^ {-dagger}\_{2,\_{2, \ down}-0.3 a ^ {-dagger}\_{1, \uparrow}a ^ {/dagger}\_{3, \uparrow}a\_{2, \ down} $ $ はによって表されます\_
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a>ベースセットオブジェクト ####

このセクションは non-normative です。

問題説明オブジェクトには、`basis_set` プロパティがある場合があります。
存在する場合、`basis_set` プロパティの値は、`type` と `name`の2つのプロパティを持つオブジェクトである必要があります。

`basis_set` プロパティの値によって識別されるベース関数は、実際の値である必要があります。

> [!NOTE]
> この仕様の将来のバージョンでは、すべての基礎関数が実際の値であることを前提としています。

## <a name="tables-and-lists"></a>テーブルとリスト ##

### <a name="table-1-allowed-physical-units"></a>テーブル 1。 許可される物理ユニット ###

このセクションは non-normative です。

単位を指定する文字列は、次のいずれかである必要があります。

- `hartree`
- `ev`

パーサーとプロデューサーは、次の単純な quantity オブジェクトを同等として扱う必要があります。

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>表 2. 許可されるインデックスの規則 ###

このセクションは non-normative です。

インデックス規則を指定する文字列は、次のいずれかである必要があります。

- `mulliken`

このセクションは有益です。

この仕様の将来のバージョンでは、追加のインデックス規則が導入される可能性があります。

#### <a name="interpretation-of-index-conventions"></a>インデックス規則の解釈 ####

このセクションは有益です。

### <a name="table-3-allowed-state-methods"></a>表 3. 許可される状態のメソッド ###

このセクションは non-normative です。

状態メソッドを指定する文字列は、次のいずれかである必要があります。

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

このセクションは有益です。

この仕様の将来のバージョンでは、追加の状態メソッドが導入される可能性があります。
