---
title: Broombridge スキーマ仕様 (ver 0.2)
description: Microsoft quantum 化学ライブラリの Broombridge 量子化学スキーマ v 0.2 の仕様について詳しく説明します。
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275854"
---
# <a name="broombridge-specification-v02"></a>Broombridge Specification v 0.2 #

このドキュメントでは、"必要"、"NOT NOT"、"REQUIRED"、"where"、"not NOT"、"be"、"NOT not"、"推奨"、"may"、および "OPTIONAL" を、 [RFC 2119](https://tools.ietf.org/html/rfc2119)で説明されているように解釈することが重要です。

見出しが "NOTE"、"情報"、または "警告" のサイドバーは役に立つものです。

## <a name="introduction"></a>概要 ##

このセクションは有益です。

Broombridge ドキュメントは、クォンタムシミュレーションとプログラミングツールチェーンを使用して処理するために、クォンタムの化学でシミュレーションの問題のインスタンスを伝えることを目的としています。

## <a name="serialization"></a>シリアル化 ##

このセクションは non-normative です。

Broombridge ドキュメントは、 [RFC 4627](https://tools.ietf.org/html/rfc4627)セクション2.2 で説明されているように、JSON オブジェクトを表す[yaml 1.2 ドキュメント](http://yaml.org/spec/)としてシリアル化する必要があります。
YAML にシリアル化されるオブジェクトに `"$schema"` は、値が `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` で、JSON スキーマ draft-06 仕様 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] に従って有効である必要があるプロパティが必要です。

この仕様の残りの部分では、"Broombridge オブジェクト" は Broombridge YAML ドキュメントから逆シリアル化された JSON オブジェクトを参照します。

特に明記されていない限り、このドキュメントで明示的に指定されている以外のプロパティをオブジェクトに追加することはできません。

## <a name="additional-definitions"></a>追加の定義 ##

このセクションは non-normative です。

### <a name="quantity-objects"></a>Quantity オブジェクト ###

このセクションは non-normative です。

_Quantity オブジェクト_は JSON オブジェクトであり、 `units` テーブル1に示されている許容値のいずれかの値を持つプロパティを持つ必要があります。

Quantity オブジェクトは、そのプロパティに加えて1つのプロパティがある場合、_単純な quantity オブジェクト_です `value` `units` 。
プロパティの値は `value` 数値である必要があります。

Quantity オブジェクトは、その_bounded quantity object_ `lower` `upper` プロパティに加えてプロパティがある場合は、制限された quantity オブジェクトです `units` 。
`lower`プロパティとプロパティの値は `upper` 数値である必要があります。
範囲指定された quantity オブジェクトには、値が数値であるプロパティが含まれる場合があり `value` ます。

Quantity オブジェクトは、そのプロパティに加えてプロパティとプロパティがある場合に、_スパース配列の quantity オブジェクト_です `format` `values` `units` 。
の値は `format` 文字列である必要があり `sparse` ます。
プロパティの値は `values` 配列である必要があります。
の各要素 `values` は、スパース配列の量のインデックスと値を表す配列である必要があります。

スパース配列の quantity オブジェクトの各要素のインデックスは、スパース配列の quantity オブジェクト全体で一意である必要があります。
インデックスに値が指定されている場合 `0` 、パーサーは、そのインデックスがまったく存在しないスパース配列の quantity オブジェクトと同じように、スパース配列の quantity オブジェクトを処理する必要があります。


Quantity オブジェクトは、

- 単純な quantity オブジェクト
- 制限付き数量オブジェクト。
- スパース配列の quantity オブジェクト。


### <a name="examples"></a>使用例 ###

このセクションは有益です。

$ 1.9844146837 \Mathrm{Ha} $ を表す単純な数量 \, :

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

範囲 $ [-7,-6] \Mathrm{Ha} $ に対する一様分布を表す、制限された数量 \, 。

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

次に示すのは、と等しい要素と、と等しい要素を持つ疎配列の数量です `[1, 2]` `hello` `[3, 4]` `world` 。

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

Broombridge オブジェクトには、 `format` という1つのプロパティを持つ JSON オブジェクトを値として持つプロパティが必要です `version` 。
`version`プロパティは、値を持つ必要があり `"0.2"` ます。

### <a name="example"></a>例 ###

このセクションは有益です。

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>問題の説明セクション ##

このセクションは non-normative です。

Broombridge オブジェクトに `problem_description` は、JSON 配列の値を持つプロパティが必要です。
このセクションの残りの部分で説明するように、プロパティの値の各項目は、 `problem_description` 1 つの積分のセットを記述する JSON オブジェクトである必要があります。
このセクションの残りの部分では、"問題説明オブジェクト" という用語は、Broombridge オブジェクトのプロパティの値の項目を指し `problem_description` ます。

問題説明オブジェクトにはそれぞれ、 `metadata` JSON オブジェクトの値を持つプロパティが必要です。
の値は、 `metadata` 空の JSON オブジェクト (つまり、)、 `{}` または実装によって定義された追加のプロパティを含むことができます。

### <a name="hamiltonian-section"></a>Hamiltonian セクション ###

#### <a name="overview"></a>概要 ####

このセクションは有益です。

`hamiltonian`各問題説明オブジェクトのプロパティは、特定の量子化学の問題の Hamiltonian について説明します。これは、1つの単語と2つの単語の用語を、実際の数値の疎配列として一覧表示することによって記述します。
各問題の説明オブジェクトによって記述される Hamiltonian 演算子は、

$ $ H = \ sum \_ \{ i, j \} \ sum \_ {\ sigma\ in \\ {\uparrow, \\ \_ \{ ij { \} \{ \} \_ i, \ sigma} a \_ {j, \ sigma} + & # ac/sum i,、& # 1; {1} {2} \_ \{ j, k, l \} \ sum \_ {/シグマ, \r ho\ in \\ {\uparrow, \ down← \\ }} H \_ {ijkl} a ^-ダガー \_ {i, \ sigma} a ^-ダガー \_ {k, \r ho} a \_ {l, \r ho} a \_ {j, \ sigma}, $ $

ここでは、Mulliken 規約で _ {ijkl} = (ij | kl ダイバージェンス) $ を $h します。

わかりやすくするために、1 ~ 電子の用語は

$ $ h_ {ij} = \ int {\mathrm d} x \ psi ^ * \_ i (x) \ left (\ frac {1} {2} \n abla ^ 2 + \ sum \_ {a} \frac{Z \_ a} {| x-x \_ A |} \ right) \ psi \_ j (x)、$ $

そして、次の2つの用語があります。

$ $ h \_ \{ ijkl \} = \ iint \{ \mathrm d \} x ^ 2 \ psi ^ \{ \* \} \_ i (x \_ 1) \ psi \_ j (x \_ 1) & frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \ psi \_ k ^ \{ \* \} (x \_ 2) \ psi \_ l (x \_ 2)
$$

プロパティの各要素の[ `basis_set` プロパティ](#basis-set-object)の説明に示されているように `integral_sets` 、使用されるベース関数が実際の値であることをさらに明示的に想定しています。
これにより、用語の間で次の symmetries を使用して、Hamiltonian の表現を圧縮することができます。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>内容 ####

このセクションは non-normative です。

問題説明オブジェクトにはそれぞれ、 `hamiltonian` JSON オブジェクトの値を持つプロパティが必要です。
このプロパティの値 `hamiltonian` は Hamiltonian オブジェクトと呼ばれ、 `one_electron_integrals` `two_electron_integrals` このセクションの残りの部分で説明するように、プロパティを持つ必要があります。

問題説明オブジェクトにはそれぞれ、 `coulomb_repulsion` 単純な quantity オブジェクトを値とするプロパティが必要です。
問題説明オブジェクトにはそれぞれ、 `energy_offet` 単純な quantity オブジェクトを値とするプロパティが必要です。
> 付箋との値を `coulomb_repulsion` 一緒に追加すると、 `energy_offet` Hamiltonian の id 用語がキャプチャされます。

##### <a name="one-electron-integrals-object"></a>1-電子積分オブジェクト #####

このセクションは non-normative です。

`one_electron_integrals`Hamiltonian オブジェクトのプロパティは、インデックスが2つの整数で、値が数値であるスパース配列の数量である必要があります。
すべての用語にはインデックスが必要 `[i, j]` `i >= j` です。

> 付箋これは $h _ {ij} = h_ {ji} $ という対称を反映しています。これは、Hamiltonian が Hermitian であるという事実の結果です。


###### <a name="example"></a>例 ######

このセクションは有益です。

次の疎配列の量は、Hamiltonian $ $ H = \ left (-5.0 (a ^- \{ ダガー \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ ダガー \} \_ {1, \ down←} a \_ {1, \ down}) + 0.17 (a ^- \{ ダガー \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^- \{ ダガー \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^- \{ ダガー \} \_ {2,} a \_ {1, \ down←} + a ^ \{ \} \_ {1, \ down←} a \_ {2, \\ ,), \mathrm{Ha}.
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

`two_electron_integrals`Hamiltonian オブジェクトのプロパティは、という1つの追加プロパティを持つスパース配列の数量である必要があり `index_convention` ます。
の値の各要素には、 `two_electron_integrals` 4 つのインデックスが必要です。

各 `two_electron_integrals` プロパティにはプロパティが必要 `index_convention` です。
プロパティの値は、 `index_convention` 表1に示す許可されている値のいずれかである必要があります。
の値がである場合、 `index_convention` `mulliken` スパース配列の数量の各要素に対して `two_electron_integrals` 、Broombridge ドキュメントを読み込むパーサーは、Hamiltonian term を 2-3 と同じでインスタンス化する必要があります $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $。ここで $i $、$j $、$k $、および $l $ は少なくとも1の値の整数である必要があります。 $h _ {i, j, k, l} $ は、 `[i, j, k, l, h(i, j, k, l)]` 疎配列の量の要素です。

###### <a name="symmetries"></a>Symmetries ######

このセクションは non-normative です。

`index_convention`オブジェクトのプロパティ `two_electron_integrals` がに等しい場合、 `mulliken` インデックスを持つ要素が存在する場合、 `[i, j, k, l]` 次のインデックスはと等しい場合を除き、存在してはなりません `[i, j, k, l]` 。

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> `index_convention`プロパティは疎数量オブジェクトであるため、インデックスを別の要素で繰り返すことはできません。
> 特に、インデックスを持つ要素 `[i, j, k, l]` が存在する場合、他の要素はそのインデックスを持つことはできません。


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>例 #######

このセクションは有益です。

次のオブジェクトは、Hamiltonian を指定します。

$$ H = \frac12 \sum \_ {\sigma,\rho\in \\ {\uparrow,\downarrow \\ }}\Biggr( 1.6 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {1,\rho} a \_ {1,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {6,\sigma} a^{\dagger} \_ {1,\rho} a \_ {2,\rho} a \_ {3,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {3,\rho} a \_ {2,\sigma}- 0.1 a^{\dagger} \_ {1,\sigma} a^{\dagger} \_ {6,\rho} a \_ {2,\rho} a \_ {3,\sigma} $$ $$- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {6,\rho} a \_ {1,\sigma}- 0.1 a^{\dagger} \_ {3,\sigma} a^{\dagger} \_ {2,\rho} a \_ {1,\rho} a \_ {6,\sigma}- 0.1 a^{\dagger} \_ {2,\sigma} a^{\dagger} \_ {3, \r ho} a \_ {6, \r ho} a \_ {1,-sigma} a {1, 0.1-sigma} a ^ {-dagger} \_ {2, \ sigma} a ^ {-dagger} \_ {3, \r ho} a \_ {1, \r ho} a \_ {6,-sigma{2}/biggr) \\ 。
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

`initial_state_suggestion`値が JSON 配列であるオブジェクトは、指定された Hamiltonian の最初のクォンタム状態を指定します。 このセクションの残りの部分で説明するように、プロパティの値の各項目は、 `initial_state_suggestion` 1 つのクォンタム状態を記述する JSON オブジェクトである必要があります。
このセクションの残りの部分では、"state オブジェクト" という用語は、Broombridge オブジェクトのプロパティの値の項目を参照し `initial_state_suggestion` ます。

#### <a name="state-object"></a>状態オブジェクト ####

このセクションは non-normative です。

各状態オブジェクトには `label` 、文字列を含むプロパティが必要です。 各状態オブジェクトには、 `method` プロパティが必要です。 プロパティの値は、 `method` 表3に示されている許可された値のいずれかである必要があります。
各状態オブジェクトは、値が `energy` 単純な quantity オブジェクトである必要があるプロパティを持つことができます。

プロパティの値がの場合 `method` `sparse_multi_configurational` 、状態オブジェクトには、 `superposition` ベース状態の配列とその正規化されていない振幅を含むプロパティが必要です。

たとえば、最初の状態は $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\ dagger} \_ {1, \uparrow}a ^ {\ dagger} \_ {2, \uparrow}a ^ {\ dagger} \_ {2, \ket}) {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {-dagger} {1, \uparrow}a ^ {-dagger} {2, \_ \uparrow}a ^ {\ dagger} \_ \_ {2, \ down↓}) + 0.2 (a ^ {-dagger} { \_ 1, \uparrow}a ^ {-dagger} { \_ 3, \uparrow}a ^ {\ dagger} \_ {2, \ downshow})} {\ sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} 、$ $ where $ \ket{E} $ はエネルギー $0.987 \t extrm{ha} $ を表します。
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

プロパティの値がの場合 `method` `unitary_coupled_cluster` 、状態オブジェクトは、 `cluster_operator` 値が JSON オブジェクトであるプロパティを持つ必要があります。
JSON オブジェクトに `reference_state` は、値が basis 状態であるプロパティが必要です。
JSON オブジェクトには、 `one_body_amplitudes` 1 つの本体のクラスター演算子とその振幅の配列を値として持つプロパティが含まれている場合があります。
JSON オブジェクトには、 `two_body_amplitudes` 2 つの本体のクラスター演算子とその振幅の配列を値として持つプロパティが含まれている場合があります。
基本的な状態とその正規化されていない振幅の配列を格納します。

たとえば、状態 $ $ \ket{\text{reference}} = (a ^ {-dagger} \_ {1, \uparrow}a ^ {\ dagger} { \_ 2, \uparrow}a ^ {/dagger} \_ {2, ^}) \ket {0} , $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}, $ $

$ $ T = 0.1 a ^ {\ dagger} \_ {3, \uparrow}a \_ {2, \ down} + 0.2 a ^ {-dagger} \_ {2, \uparrow}a \_ {2, \ down}-0.3 a ^ {-dagger} { \_ 1, \uparrow}a ^ {/dagger} {3, \_ \_ \uparrow}a \_ {2, \ down} $ $ はによって表されます。
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

問題説明オブジェクトにはそれぞれプロパティがある場合があり `basis_set` ます。
存在する場合、プロパティの値は、 `basis_set` との2つのプロパティを持つオブジェクトである必要があり `type` `name` ます。

プロパティの値によって識別されるベース関数は、実際の値で `basis_set` ある必要があります。

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

### <a name="table-3-allowed-state-methods"></a>表 3 許可される状態のメソッド ###

このセクションは non-normative です。

状態メソッドを指定する文字列は、次のいずれかである必要があります。

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

このセクションは有益です。

この仕様の将来のバージョンでは、追加の状態メソッドが導入される可能性があります。
