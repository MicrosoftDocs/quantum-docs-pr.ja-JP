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
# <a name="broombridge-specification-v02"></a><span data-ttu-id="7021b-103">Broombridge Specification v 0.2</span><span class="sxs-lookup"><span data-stu-id="7021b-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="7021b-104">このドキュメントでは、"必要"、"NOT NOT"、"REQUIRED"、"where"、"not NOT"、"be"、"NOT not"、"推奨"、"may"、および "OPTIONAL" を、 [RFC 2119](https://tools.ietf.org/html/rfc2119)で説明されているように解釈することが重要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="7021b-105">見出しが "NOTE"、"情報"、または "警告" のサイドバーは役に立つものです。</span><span class="sxs-lookup"><span data-stu-id="7021b-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="7021b-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="7021b-106">Introduction</span></span> ##

<span data-ttu-id="7021b-107">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-107">This section is informative.</span></span>

<span data-ttu-id="7021b-108">Broombridge ドキュメントは、クォンタムシミュレーションとプログラミングツールチェーンを使用して処理するために、クォンタムの化学でシミュレーションの問題のインスタンスを伝えることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="7021b-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="7021b-109">シリアル化</span><span class="sxs-lookup"><span data-stu-id="7021b-109">Serialization</span></span> ##

<span data-ttu-id="7021b-110">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-110">This section is normative.</span></span>

<span data-ttu-id="7021b-111">Broombridge ドキュメントは、 [RFC 4627](https://tools.ietf.org/html/rfc4627)セクション2.2 で説明されているように、JSON オブジェクトを表す[yaml 1.2 ドキュメント](http://yaml.org/spec/)としてシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="7021b-112">YAML にシリアル化されたオブジェクトには、値が `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`で、JSON スキーマ draft-06 仕様 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] に従って有効である必要があるプロパティ `"$schema"` が必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="7021b-113">この仕様の残りの部分では、"Broombridge オブジェクト" は Broombridge YAML ドキュメントから逆シリアル化された JSON オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="7021b-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="7021b-114">特に明記されていない限り、このドキュメントで明示的に指定されている以外のプロパティをオブジェクトに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="7021b-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="7021b-115">追加の定義</span><span class="sxs-lookup"><span data-stu-id="7021b-115">Additional Definitions</span></span> ##

<span data-ttu-id="7021b-116">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="7021b-117">Quantity オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7021b-117">Quantity Objects</span></span> ###

<span data-ttu-id="7021b-118">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-118">This section is normative.</span></span>

<span data-ttu-id="7021b-119">_Quantity オブジェクト_は JSON オブジェクトであり、値がテーブル1に示されている許可値の1つである `units` プロパティを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="7021b-120">Quantity オブジェクトは、`units` プロパティに加えて1つのプロパティ `value` がある場合、_単純な quantity オブジェクト_です。</span><span class="sxs-lookup"><span data-stu-id="7021b-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="7021b-121">`value` プロパティの値には数値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="7021b-122">Quantity オブジェクトは、`units` プロパティに加えて `lower` および `upper` プロパティがある場合に、制限された_quantity オブジェクト_です。</span><span class="sxs-lookup"><span data-stu-id="7021b-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="7021b-123">`lower` プロパティと `upper` プロパティの値は数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="7021b-124">範囲指定された quantity オブジェクトには、値が数値であるプロパティ `value` が存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="7021b-125">Quantity オブジェクトは、プロパティ `format` と、その `units` プロパティに加えて `values` プロパティがある場合に、_スパース配列の quantity オブジェクト_です。</span><span class="sxs-lookup"><span data-stu-id="7021b-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="7021b-126">`format` の値は、`sparse`文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="7021b-127">`values` プロパティの値は配列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="7021b-128">`values` の各要素は、スパース配列の量のインデックスと値を表す配列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="7021b-129">スパース配列の quantity オブジェクトの各要素のインデックスは、スパース配列の quantity オブジェクト全体で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="7021b-130">値が `0`のインデックスが存在する場合、パーサーは、そのインデックスがまったく存在しないスパース配列の quantity オブジェクトと同じように、スパース配列の quantity オブジェクトを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="7021b-131">Quantity オブジェクトは、</span><span class="sxs-lookup"><span data-stu-id="7021b-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="7021b-132">単純な quantity オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7021b-132">a simple quantity object,</span></span>
- <span data-ttu-id="7021b-133">制限付き数量オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7021b-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="7021b-134">スパース配列の quantity オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7021b-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="7021b-135">例</span><span class="sxs-lookup"><span data-stu-id="7021b-135">Examples</span></span> ###

<span data-ttu-id="7021b-136">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-136">This section is informative.</span></span>

<span data-ttu-id="7021b-137">$ 1.9844146837\,\mathrm{Ha} $ を表す単純な数量:</span><span class="sxs-lookup"><span data-stu-id="7021b-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="7021b-138">範囲 $ [-7,-6\,] に対する一様分布を表す、\mathrm{Ha} $ の範囲外の数量。</span><span class="sxs-lookup"><span data-stu-id="7021b-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="7021b-139">次に示すのは、要素 `[1, 2]` `hello` と等しく、要素 `[3, 4]` `world`と等しい場合の疎配列の数量です。</span><span class="sxs-lookup"><span data-stu-id="7021b-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="7021b-140">書式セクション</span><span class="sxs-lookup"><span data-stu-id="7021b-140">Format Section</span></span> ##

<span data-ttu-id="7021b-141">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-141">This section is normative.</span></span>

<span data-ttu-id="7021b-142">Broombridge オブジェクトには、`version`という1つのプロパティを持つ JSON オブジェクトを値として持つプロパティ `format` が必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="7021b-143">`version` プロパティには `"0.2"`値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="7021b-144">例</span><span class="sxs-lookup"><span data-stu-id="7021b-144">Example</span></span> ###

<span data-ttu-id="7021b-145">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="7021b-146">問題の説明セクション</span><span class="sxs-lookup"><span data-stu-id="7021b-146">Problem Description Section</span></span> ##

<span data-ttu-id="7021b-147">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-147">This section is normative.</span></span>

<span data-ttu-id="7021b-148">Broombridge オブジェクトには、値が JSON 配列であるプロパティ `problem_description` が必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="7021b-149">`problem_description` プロパティの値の各項目は、このセクションの残りの部分で説明されているように、1つの積分のセットを記述する JSON オブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="7021b-150">このセクションの残りの部分では、"問題説明オブジェクト" という用語は、Broombridge オブジェクトの [`problem_description`] プロパティの値の項目を指します。</span><span class="sxs-lookup"><span data-stu-id="7021b-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="7021b-151">問題説明オブジェクトにはそれぞれ、JSON オブジェクトの値を持つプロパティ `metadata` が必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="7021b-152">`metadata` の値には、空の JSON オブジェクト (つまり、`{}`) を指定することも、実装で定義されている追加のプロパティを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="7021b-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="7021b-153">Hamiltonian セクション</span><span class="sxs-lookup"><span data-stu-id="7021b-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="7021b-154">概要</span><span class="sxs-lookup"><span data-stu-id="7021b-154">Overview</span></span> ####

<span data-ttu-id="7021b-155">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-155">This section is informative.</span></span>

<span data-ttu-id="7021b-156">各問題説明オブジェクトの [`hamiltonian`] プロパティには、1つまたは2つの単語の項を実数の疎配列として一覧表示することによって、特定の量子化学の問題の Hamiltonian が記述されています。</span><span class="sxs-lookup"><span data-stu-id="7021b-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="7021b-157">各問題の説明オブジェクトによって記述される Hamiltonian 演算子は、</span><span class="sxs-lookup"><span data-stu-id="7021b-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="7021b-158">$ $ H = \ sum\_\{i、j\}\ sum\_{/sigma\ in\\{\uparrow, ij\\\_}} H \{\}\{a ^\}/ダガー \_{i, \ sigma} a\_{j, \ sigma} +-frac{1}{2}-sum\_\{i、j、k、l\}-sum\_{/σ、\r ho\ in\\{\uparrow, \ downarrow\\}} H\_{ijkl} a ^\_{i, \ sigma} a ^ ダガー\_{k, \r ho} a\_{l, \r ho} a\_{j, \ sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="7021b-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="7021b-159">ここでは、Mulliken 規約で _ {ijkl} = (ij | kl ダイバージェンス) $ を $h します。</span><span class="sxs-lookup"><span data-stu-id="7021b-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="7021b-160">わかりやすくするために、1 ~ 電子の用語は</span><span class="sxs-lookup"><span data-stu-id="7021b-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="7021b-161">$ $ h_ {ij} = \ int {\mathrm d} x \ psi ^ \*\_i (x) \ 左 (\ frac{1}{2}\n abla ^ 2 + \ sum\_{A} \frac{Z\_A} {| x-x\_A |} \ right) \ psi\_j (x)、$ $</span><span class="sxs-lookup"><span data-stu-id="7021b-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="7021b-162">そして、次の2つの用語があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-162">and the two-electron term is</span></span>

<span data-ttu-id="7021b-163">$ $ h\_\{ijkl\} = \ iint \{\mathrm d\}x ^ 2 \ psi ^\{\*\}\_i (x\_1) \ psi\_j (x\_1) \ frac\{1\}\{\|x\_1-x\_2\|\}\ psi\_k ^\{\*\}(x\_2) \ psi\_l (x\_2)。</span><span class="sxs-lookup"><span data-stu-id="7021b-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="7021b-164">`integral_sets` プロパティの各要素の[`basis_set` プロパティ](#basis-set-object)について説明したように、使用されるベース関数が実際の値であることをさらに明示的に想定しています。</span><span class="sxs-lookup"><span data-stu-id="7021b-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="7021b-165">これにより、用語の間で次の symmetries を使用して、Hamiltonian の表現を圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="7021b-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="7021b-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。</span><span class="sxs-lookup"><span data-stu-id="7021b-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="7021b-167">内容</span><span class="sxs-lookup"><span data-stu-id="7021b-167">Contents</span></span> ####

<span data-ttu-id="7021b-168">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-168">This section is normative.</span></span>

<span data-ttu-id="7021b-169">問題説明オブジェクトにはそれぞれ、JSON オブジェクトの値を持つプロパティ `hamiltonian` が必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="7021b-170">`hamiltonian` プロパティの値は Hamiltonian オブジェクトとして知られており、このセクションの残りの部分で説明するように、プロパティ `one_electron_integrals` と `two_electron_integrals` を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="7021b-171">各問題の説明オブジェクトには、値が単純な quantity オブジェクトである `coulomb_repulsion` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="7021b-172">各問題の説明オブジェクトには、値が単純な quantity オブジェクトである `energy_offet` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="7021b-173">付箋`coulomb_repulsion` と `energy_offet` の値を一緒に追加すると、Hamiltonian の id 用語がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="7021b-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="7021b-174">1-電子積分オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7021b-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="7021b-175">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-175">This section is normative.</span></span>

<span data-ttu-id="7021b-176">Hamiltonian オブジェクトの `one_electron_integrals` プロパティは、インデックスが2つの整数で、値が数値であるスパース配列の数量である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="7021b-177">すべての用語には、`i >= j``[i, j]` インデックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="7021b-178">付箋これは $h _ {ij} = h_ {ji} $ という対称を反映しています。これは、Hamiltonian が Hermitian であるという事実の結果です。</span><span class="sxs-lookup"><span data-stu-id="7021b-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="7021b-179">例</span><span class="sxs-lookup"><span data-stu-id="7021b-179">Example</span></span> ######

<span data-ttu-id="7021b-180">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-180">This section is informative.</span></span>

<span data-ttu-id="7021b-181">次の疎配列の量は、Hamiltonian $ $ H = \ left (-5.0 (a ^\{\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\ ダガー\}\_{1, \uparrow}\{\}{2, \uparrow} a \_{1, + a ^\_/ダガー\{\}{1, \uparrow} a \_{2, 0.17\_\uparrow} + a ^\_/ダガー\{\}{2。 \_{1, a {2, \ down←} a\_{1, \ down←} + a ^\{\ ダガー\}\_{1, \ down←} a\_{2, \ down←}), \mathrm{Ha}.\\</span><span class="sxs-lookup"><span data-stu-id="7021b-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="7021b-182">Broombridge は、1から始まるインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="7021b-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="7021b-183">2つの電子積分オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7021b-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="7021b-184">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-184">This section is normative.</span></span>

<span data-ttu-id="7021b-185">Hamiltonian オブジェクトの `two_electron_integrals` プロパティは、`index_convention`という1つの追加のプロパティを持つスパース配列の数量である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="7021b-186">`two_electron_integrals` の値の各要素には、4つのインデックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="7021b-187">各 `two_electron_integrals` プロパティには、`index_convention` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="7021b-188">`index_convention` プロパティの値は、表1に示されている許可された値のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="7021b-189">`index_convention` の値が `mulliken`の場合、`two_electron_integrals` sparse 配列の数量の各要素に対して、Broombridge ドキュメントを読み込むパーサーは、2-3-電子オペレーター $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $。ここで $i $、$j $、$k $、および $l $ は少なくとも1の値の整数である必要があります。 $h _ {i, j, k, l} $ は、疎配列の量の要素 `[i, j, k, l, h(i, j, k, l)]` です。</span><span class="sxs-lookup"><span data-stu-id="7021b-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="7021b-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="7021b-190">Symmetries</span></span> ######

<span data-ttu-id="7021b-191">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-191">This section is normative.</span></span>

<span data-ttu-id="7021b-192">`two_electron_integrals` オブジェクトの `index_convention` プロパティが `mulliken`と等しい場合、インデックス `[i, j, k, l]` を持つ要素が存在する場合、次のインデックスは `[i, j, k, l]`と等しい場合を除き、存在してはなりません。</span><span class="sxs-lookup"><span data-stu-id="7021b-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="7021b-193">`index_convention` プロパティは疎数量オブジェクトであるため、異なる要素でインデックスを繰り返し使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7021b-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="7021b-194">特に、`[i, j, k, l]` インデックスを持つ要素が存在する場合、他の要素にそのインデックスを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7021b-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="7021b-195">例</span><span class="sxs-lookup"><span data-stu-id="7021b-195">Example</span></span> #######

<span data-ttu-id="7021b-196">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-196">This section is informative.</span></span>

<span data-ttu-id="7021b-197">次のオブジェクトは、Hamiltonian を指定します。</span><span class="sxs-lookup"><span data-stu-id="7021b-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="7021b-198">$ $ H = \frac12 \ sum\_{/シグマ, \r ho\ in\\{\uparrow, (& a)\\}} \ biggr (1.6 a ^ {\ dagger}\_{1, \ sigma} a ^ {-dagger} a ^ {1, \r ho} a\_{1, \r ho} a\_{\_1, \ sigma-0.1 a ^ {-dagger}\_{6, \ sigma} a ^ {-dagger}\_{1, \r ho} a\_{3, \r ho} a\_{3, \r ho} a ^ {6, \ sigma} a ^ {6, \ sigma} a ^ {/dagger}\_{1, \r ho} a\_{2 0.1\_, \r ho} a\_{3, \ sigma-0.1 a ^ {-dagger}\_{1, \ sigma} a ^ {\ dagger}\_{6, \r ho} a\_{3, \r ho} a\_{2, \ sigma} a ^ {-dagger}\_{1,-sigma} a ^ {-dagger}\_0.1 {6, \r ho} a\_{2, \r ho} a\_{3, \ sigma} $ $ $ $-0.1 a ^ {-dagger}\_{3, \ sigma} a ^ {\ dagger}\_{2, \r ho} a\_{6, \r ho} a\_{1, \ sigma-0.1 a ^ {-dagger}\_{3,、\ sigma} a ^ {\ dagger}\_{2, \r ho} a\_{1, \r ho} a\_{1, \r ho} a {6, \ sig\_0.1 ma} a ^ {2,-sigma} a ^ {& dagger}\_{3, \r ho} a\_{6, \r ho} a\_{1,/sigma\_-0.1 a ^ {-dagger}\_{2,/sigma} a ^ {-dagger}\_{3, \r ho} a {1, \r ho} a\_{6,/sigma/biggr)\\, \T extrm{ha$。</span><span class="sxs-lookup"><span data-stu-id="7021b-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="7021b-199">初期状態セクション</span><span class="sxs-lookup"><span data-stu-id="7021b-199">Initial State Section</span></span> ###

<span data-ttu-id="7021b-200">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-200">This section is normative.</span></span>

<span data-ttu-id="7021b-201">値が JSON 配列である `initial_state_suggestion` オブジェクトは、指定された Hamiltonian に対して対象となる初期クォンタムの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="7021b-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="7021b-202">`initial_state_suggestion` プロパティの値の各項目は、このセクションの残りの部分で説明するように、1つのクォンタム状態を記述する JSON オブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="7021b-203">このセクションの残りの部分では、"state オブジェクト" という用語は、Broombridge オブジェクトの `initial_state_suggestion` プロパティの値の項目を参照します。</span><span class="sxs-lookup"><span data-stu-id="7021b-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="7021b-204">状態オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7021b-204">State object</span></span> ####

<span data-ttu-id="7021b-205">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-205">This section is normative.</span></span>

<span data-ttu-id="7021b-206">各状態オブジェクトには、文字列を含む `label` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="7021b-207">各状態オブジェクトには、`method` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="7021b-208">`method` プロパティの値は、表3に示されている許可された値のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="7021b-209">各状態オブジェクトには、値が単純な quantity オブジェクトである必要がある `energy` プロパティが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="7021b-210">`method` プロパティの値が `sparse_multi_configurational`場合、状態オブジェクトには、ベース状態の配列とその正規化されていない振幅を含む `superposition` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="7021b-211">たとえば、初期状態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\ dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ket}){0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {-dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ down\_}) + 0.2 (a ^ {/dagger} {1, \uparrow}a ^ {\ dagger}\_{3, \uparrow}a ^ {\ dagger}\_{2, \ down})} {\ sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0}$ $ $ $ \ket{E} $ がエネルギー $0.987 \T extrm{ha} $ を持つ $ $ は、によって表されます。</span><span class="sxs-lookup"><span data-stu-id="7021b-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
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

<span data-ttu-id="7021b-212">`method` プロパティの値が `unitary_coupled_cluster`の場合、状態オブジェクトには、JSON オブジェクトの値を持つ `cluster_operator` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="7021b-213">JSON オブジェクトには、値が basis 状態である `reference_state` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="7021b-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="7021b-214">JSON オブジェクトには、1つの本体のクラスター演算子とその振幅の配列を値として持つ `one_body_amplitudes` のプロパティがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="7021b-215">JSON オブジェクトには、2つの本体のクラスター演算子とその振幅の配列を値として持つ `two_body_amplitudes` のプロパティがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="7021b-216">基本的な状態とその正規化されていない振幅の配列を格納します。</span><span class="sxs-lookup"><span data-stu-id="7021b-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="7021b-217">たとえば、状態 $ $ \ket{\text{reference}} = (a ^ {\ dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ down}) \ket{0}, $ $</span><span class="sxs-lookup"><span data-stu-id="7021b-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="7021b-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="7021b-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="7021b-219">$ $ T = 0.1 a ^ {\ dagger}\_{3, \uparrow}a\_{2, \ down\uparrow}a} + 0.2 a ^ {-dagger}\_{2,\_{2, \ down}-0.3 a ^ {-dagger}\_{1, \uparrow}a ^ {/dagger}\_{3, \uparrow}a\_{2, \ down} $ $ はによって表されます\_</span><span class="sxs-lookup"><span data-stu-id="7021b-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="7021b-220">ベースセットオブジェクト</span><span class="sxs-lookup"><span data-stu-id="7021b-220">Basis Set Object</span></span> ####

<span data-ttu-id="7021b-221">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-221">This section is normative.</span></span>

<span data-ttu-id="7021b-222">問題説明オブジェクトには、`basis_set` プロパティがある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="7021b-223">存在する場合、`basis_set` プロパティの値は、`type` と `name`の2つのプロパティを持つオブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="7021b-224">`basis_set` プロパティの値によって識別されるベース関数は、実際の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="7021b-225">この仕様の将来のバージョンでは、すべての基礎関数が実際の値であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="7021b-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="7021b-226">テーブルとリスト</span><span class="sxs-lookup"><span data-stu-id="7021b-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="7021b-227">テーブル 1。</span><span class="sxs-lookup"><span data-stu-id="7021b-227">Table 1.</span></span> <span data-ttu-id="7021b-228">許可される物理ユニット</span><span class="sxs-lookup"><span data-stu-id="7021b-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="7021b-229">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-229">This section is normative.</span></span>

<span data-ttu-id="7021b-230">単位を指定する文字列は、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="7021b-231">パーサーとプロデューサーは、次の単純な quantity オブジェクトを同等として扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="7021b-232">表 2.</span><span class="sxs-lookup"><span data-stu-id="7021b-232">Table 2.</span></span> <span data-ttu-id="7021b-233">許可されるインデックスの規則</span><span class="sxs-lookup"><span data-stu-id="7021b-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="7021b-234">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-234">This section is normative.</span></span>

<span data-ttu-id="7021b-235">インデックス規則を指定する文字列は、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="7021b-236">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-236">This section is informative.</span></span>

<span data-ttu-id="7021b-237">この仕様の将来のバージョンでは、追加のインデックス規則が導入される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="7021b-238">インデックス規則の解釈</span><span class="sxs-lookup"><span data-stu-id="7021b-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="7021b-239">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="7021b-240">表 3.</span><span class="sxs-lookup"><span data-stu-id="7021b-240">Table 3.</span></span> <span data-ttu-id="7021b-241">許可される状態のメソッド</span><span class="sxs-lookup"><span data-stu-id="7021b-241">Allowed State methods</span></span> ###

<span data-ttu-id="7021b-242">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="7021b-242">This section is normative.</span></span>

<span data-ttu-id="7021b-243">状態メソッドを指定する文字列は、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="7021b-244">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="7021b-244">This section is informative.</span></span>

<span data-ttu-id="7021b-245">この仕様の将来のバージョンでは、追加の状態メソッドが導入される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7021b-245">Additional state methods may be introduced in future versions of this specification.</span></span>
