---
title: Broombridge スキーマ仕様 (ver 0.1)
description: Microsoft quantum 化学ライブラリの Broombridge 量子化学スキーマ v 0.1 の仕様について詳しく説明します。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906425"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="245ad-103">Broombridge の仕様 v 0.1</span><span class="sxs-lookup"><span data-stu-id="245ad-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="245ad-104">このドキュメントでは、"必要"、"NOT NOT"、"REQUIRED"、"where"、"not NOT"、"be"、"NOT not"、"推奨"、"may"、および "OPTIONAL" を、 [RFC 2119](https://tools.ietf.org/html/rfc2119)で説明されているように解釈することが重要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="245ad-105">見出しが "NOTE"、"情報"、または "警告" のサイドバーは役に立つものです。</span><span class="sxs-lookup"><span data-stu-id="245ad-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="245ad-106">はじめに</span><span class="sxs-lookup"><span data-stu-id="245ad-106">Introduction</span></span> ##

<span data-ttu-id="245ad-107">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-107">This section is informative.</span></span>

<span data-ttu-id="245ad-108">Broombridge ドキュメントは、クォンタムシミュレーションとプログラミングツールチェーンを使用して処理するために、クォンタムの化学でシミュレーションの問題のインスタンスを伝えることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="245ad-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="245ad-109">シリアル化</span><span class="sxs-lookup"><span data-stu-id="245ad-109">Serialization</span></span> ##

<span data-ttu-id="245ad-110">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-110">This section is normative.</span></span>

<span data-ttu-id="245ad-111">Broombridge ドキュメントは、 [RFC 4627](https://tools.ietf.org/html/rfc4627)セクション2.2 で説明されているように、JSON オブジェクトを表す[yaml 1.2 ドキュメント](http://yaml.org/spec/)としてシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="245ad-112">YAML にシリアル化されたオブジェクトには、値が `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`で、JSON スキーマ draft-06 仕様 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] に従って有効である必要があるプロパティ `"$schema"` が必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="245ad-113">この仕様の残りの部分では、"Broombridge オブジェクト" は Broombridge YAML ドキュメントから逆シリアル化された JSON オブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="245ad-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="245ad-114">特に明記されていない限り、このドキュメントで明示的に指定されている以外のプロパティをオブジェクトに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="245ad-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="245ad-115">追加の定義</span><span class="sxs-lookup"><span data-stu-id="245ad-115">Additional Definitions</span></span> ##

<span data-ttu-id="245ad-116">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="245ad-117">Quantity オブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-117">Quantity Objects</span></span> ###

<span data-ttu-id="245ad-118">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-118">This section is normative.</span></span>

<span data-ttu-id="245ad-119">_Quantity オブジェクト_は JSON オブジェクトであり、値がテーブル1に示されている許可値の1つである `units` プロパティを持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="245ad-120">Quantity オブジェクトは、`units` プロパティに加えて1つのプロパティ `value` がある場合、_単純な quantity オブジェクト_です。</span><span class="sxs-lookup"><span data-stu-id="245ad-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="245ad-121">`value` プロパティの値には数値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="245ad-122">Quantity オブジェクトは、`units` プロパティに加えて `lower` および `upper` プロパティがある場合に、制限された_quantity オブジェクト_です。</span><span class="sxs-lookup"><span data-stu-id="245ad-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="245ad-123">`lower` プロパティと `upper` プロパティの値は数値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="245ad-124">範囲指定された quantity オブジェクトには、値が数値であるプロパティ `value` が存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="245ad-125">Quantity オブジェクトは、プロパティ `format` と、その `units` プロパティに加えて `values` プロパティがある場合に、_スパース配列の quantity オブジェクト_です。</span><span class="sxs-lookup"><span data-stu-id="245ad-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="245ad-126">`format` の値は、`sparse`文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="245ad-127">`values` プロパティの値は配列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="245ad-128">`values` の各要素は、スパース配列の量のインデックスと値を表す配列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="245ad-129">スパース配列の quantity オブジェクトの各要素のインデックスは、スパース配列の quantity オブジェクト全体で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="245ad-130">値が `0`のインデックスが存在する場合、パーサーは、そのインデックスがまったく存在しないスパース配列の quantity オブジェクトと同じように、スパース配列の quantity オブジェクトを処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="245ad-131">Quantity オブジェクトは、</span><span class="sxs-lookup"><span data-stu-id="245ad-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="245ad-132">単純な quantity オブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-132">a simple quantity object,</span></span>
- <span data-ttu-id="245ad-133">制限付き数量オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="245ad-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="245ad-134">スパース配列の quantity オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="245ad-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="245ad-135">例</span><span class="sxs-lookup"><span data-stu-id="245ad-135">Examples</span></span> ###

<span data-ttu-id="245ad-136">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-136">This section is informative.</span></span>

<span data-ttu-id="245ad-137">$ 1.9844146837\,\mathrm{Ha} $ を表す単純な数量:</span><span class="sxs-lookup"><span data-stu-id="245ad-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="245ad-138">範囲 $ [-7,-6\,] に対する一様分布を表す、\mathrm{Ha} $ の範囲外の数量。</span><span class="sxs-lookup"><span data-stu-id="245ad-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="245ad-139">次に示すのは、要素 `[1, 2]` `hello` と等しく、要素 `[3, 4]` `world`と等しい場合の疎配列の数量です。</span><span class="sxs-lookup"><span data-stu-id="245ad-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="245ad-140">書式セクション</span><span class="sxs-lookup"><span data-stu-id="245ad-140">Format Section</span></span> ##

<span data-ttu-id="245ad-141">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-141">This section is normative.</span></span>

<span data-ttu-id="245ad-142">Broombridge オブジェクトには、`version`という1つのプロパティを持つ JSON オブジェクトを値として持つプロパティ `format` が必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="245ad-143">`version` プロパティには `"0.1"`値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="245ad-144">例</span><span class="sxs-lookup"><span data-stu-id="245ad-144">Example</span></span> ###

<span data-ttu-id="245ad-145">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="245ad-146">整数セットセクション</span><span class="sxs-lookup"><span data-stu-id="245ad-146">Integral Sets Section</span></span> ##

<span data-ttu-id="245ad-147">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-147">This section is normative.</span></span>

<span data-ttu-id="245ad-148">Broombridge オブジェクトには、値が JSON 配列であるプロパティ `integral_sets` が必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="245ad-149">`integral_sets` プロパティの値の各項目は、このセクションの残りの部分で説明されているように、1つの積分のセットを記述する JSON オブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="245ad-150">このセクションの残りの部分では、"整数セットオブジェクト" という用語は、Broombridge オブジェクトの `integral_sets` プロパティの値の項目を参照します。</span><span class="sxs-lookup"><span data-stu-id="245ad-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="245ad-151">各整数セットオブジェクトには、値が JSON オブジェクトである `metadata` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="245ad-152">`metadata` の値には、空の JSON オブジェクト (つまり、`{}`) を指定することも、実装で定義されている追加のプロパティを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="245ad-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="245ad-153">Hamiltonian セクション</span><span class="sxs-lookup"><span data-stu-id="245ad-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="245ad-154">概要</span><span class="sxs-lookup"><span data-stu-id="245ad-154">Overview</span></span> ####

<span data-ttu-id="245ad-155">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-155">This section is informative.</span></span>

<span data-ttu-id="245ad-156">各整数セットオブジェクトの `hamiltonian` プロパティは、特定の量子化学の問題の Hamiltonian について説明します。これは、1つの単語と2つの単語の項を、実際の数値の疎配列として一覧表示することによって記述します。</span><span class="sxs-lookup"><span data-stu-id="245ad-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="245ad-157">各整数 set オブジェクトによって記述される Hamiltonian 演算子は、という形式になります。</span><span class="sxs-lookup"><span data-stu-id="245ad-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="245ad-158">$ $ H = \ sum\_\{i、j\}\ sum\_{/sigma\ in\\{\uparrow, ij\\\_}} H \{\}\{a ^\}/ダガー \_{i, \ sigma} a\_{j, \ sigma} +-frac{1}{2}-sum\_\{i、j、k、l\}-sum\_{/σ、\r ho\ in\\{\uparrow, \ downarrow\\}} H\_{ijkl} a ^\_{i, \ sigma} a ^ ダガー\_{k, \r ho} a\_{l, \r ho} a\_{j, \ sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="245ad-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="245ad-159">ここでは、Mulliken 規約で _ {ijkl} = (ij | kl ダイバージェンス) $ を $h します。</span><span class="sxs-lookup"><span data-stu-id="245ad-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="245ad-160">わかりやすくするために、1 ~ 電子の用語は</span><span class="sxs-lookup"><span data-stu-id="245ad-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="245ad-161">$ $ h_ {ij} = \ int {\mathrm d} x \ psi ^ \*\_i (x) \ 左 (\ frac{1}{2}\n abla ^ 2 + \ sum\_{A} \frac{Z\_A} {| x-x\_A |} \ right) \ psi\_j (x)、$ $</span><span class="sxs-lookup"><span data-stu-id="245ad-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="245ad-162">そして、次の2つの用語があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-162">and the two-electron term is</span></span>

<span data-ttu-id="245ad-163">$ $ h\_\{ijkl\} = \ iint \{\mathrm d\}x ^ 2 \ psi ^\{\*\}\_i (x\_1) \ psi\_j (x\_1) \ frac\{1\}\{\|x\_1-x\_2\|\}\ psi\_k ^\{\*\}(x\_2) \ psi\_l (x\_2)。</span><span class="sxs-lookup"><span data-stu-id="245ad-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="245ad-164">`integral_sets` プロパティの各要素の[`basis_set` プロパティ](#basis-set-object)について説明したように、使用されるベース関数が実際の値であることをさらに明示的に想定しています。</span><span class="sxs-lookup"><span data-stu-id="245ad-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="245ad-165">これにより、用語の間で次の symmetries を使用して、Hamiltonian の表現を圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="245ad-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="245ad-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。</span><span class="sxs-lookup"><span data-stu-id="245ad-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="245ad-167">内容</span><span class="sxs-lookup"><span data-stu-id="245ad-167">Contents</span></span> ####

<span data-ttu-id="245ad-168">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-168">This section is normative.</span></span>

<span data-ttu-id="245ad-169">各整数セットには、値が JSON オブジェクトである `hamiltonian` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="245ad-170">`hamiltonian` プロパティの値は Hamiltonian オブジェクトとして知られており、このセクションの残りの部分で説明するように、プロパティ `one_electron_integrals` と `two_electron_integrals` を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="245ad-171">Hamiltonian オブジェクトには、プロパティ `particle_hole_representation`を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="245ad-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="245ad-172">存在する場合、`particle_hole_representation` の値は、このセクションの残りの部分で説明されている形式に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="245ad-173">1-電子積分オブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="245ad-174">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-174">This section is normative.</span></span>

<span data-ttu-id="245ad-175">Hamiltonian オブジェクトの `one_electron_integrals` プロパティは、インデックスが2つの整数で、値が数値であるスパース配列の数量である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="245ad-176">すべての用語には、`i >= j``[i, j]` インデックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="245ad-177">付箋これは $h _ {ij} = h_ {ji} $ という対称を反映しています。これは、Hamiltonian が Hermitian であるという事実の結果です。</span><span class="sxs-lookup"><span data-stu-id="245ad-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="245ad-178">例</span><span class="sxs-lookup"><span data-stu-id="245ad-178">Example</span></span> ######

<span data-ttu-id="245ad-179">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-179">This section is informative.</span></span>

<span data-ttu-id="245ad-180">次の疎配列の量は、Hamiltonian $ $ H = \ left (-5.0 (a ^\{\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\ ダガー\}\_{1, \uparrow}\{\}{2, \uparrow} a \_{1, + a ^\_/ダガー\{\}{1, \uparrow} a \_{2, 0.17\_\uparrow} + a ^\_/ダガー\{\}{2。 \_{1, a {2, \ down←} a\_{1, \ down←} + a ^\{\ ダガー\}\_{1, \ down←} a\_{2, \ down←}), \mathrm{Ha}.\\</span><span class="sxs-lookup"><span data-stu-id="245ad-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="245ad-181">Broombridge は、1から始まるインデックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="245ad-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="245ad-182">2つの電子積分オブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="245ad-183">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-183">This section is normative.</span></span>

<span data-ttu-id="245ad-184">Hamiltonian オブジェクトの `two_electron_integrals` プロパティは、`index_convention`という1つの追加のプロパティを持つスパース配列の数量である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="245ad-185">`two_electron_integrals` の値の各要素には、4つのインデックスが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="245ad-186">各 `two_electron_integrals` プロパティには、`index_convention` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="245ad-187">`index_convention` プロパティの値は、表1に示されている許可された値のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="245ad-188">`index_convention` の値が `mulliken`の場合、`two_electron_integrals` sparse 配列の数量の各要素に対して、Broombridge ドキュメントを読み込むパーサーは、2-3-電子オペレーター $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $。ここで、$i $、$j $、$k $、および $l $ は、包括範囲内の整数にする必要があります。1から整数 set オブジェクトの `n_electrons` プロパティで指定された原子の数まで、$h _ {i, j, k, l} $ は、スパース配列の量の `[i, j, k, l, h(i, j, k, l)]` 要素です。</span><span class="sxs-lookup"><span data-stu-id="245ad-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="245ad-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="245ad-189">Symmetries</span></span> ######

<span data-ttu-id="245ad-190">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-190">This section is normative.</span></span>

<span data-ttu-id="245ad-191">`two_electron_integrals` オブジェクトの `index_convention` プロパティが `mulliken`と等しい場合、インデックス `[i, j, k, l]` を持つ要素が存在する場合、次のインデックスは `[i, j, k, l]`と等しい場合を除き、存在してはなりません。</span><span class="sxs-lookup"><span data-stu-id="245ad-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="245ad-192">`index_convention` プロパティは疎数量オブジェクトであるため、異なる要素でインデックスを繰り返し使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="245ad-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="245ad-193">特に、`[i, j, k, l]` インデックスを持つ要素が存在する場合、他の要素にそのインデックスを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="245ad-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="245ad-194">例</span><span class="sxs-lookup"><span data-stu-id="245ad-194">Example</span></span> #######

<span data-ttu-id="245ad-195">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-195">This section is informative.</span></span>

<span data-ttu-id="245ad-196">次のオブジェクトは、Hamiltonian を指定します。</span><span class="sxs-lookup"><span data-stu-id="245ad-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="245ad-197">$ $ H = \frac12 \ sum\_{/シグマ, \r ho\ in\\{\uparrow, (& a)\\}} \ biggr (1.6 a ^ {\ dagger}\_{1, \ sigma} a ^ {-dagger} a ^ {1, \r ho} a\_{1, \r ho} a\_{\_1, \ sigma-0.1 a ^ {-dagger}\_{6, \ sigma} a ^ {-dagger}\_{1, \r ho} a\_{3, \r ho} a\_{3, \r ho} a ^ {6, \ sigma} a ^ {6, \ sigma} a ^ {/dagger}\_{1, \r ho} a\_{2 0.1\_, \r ho} a\_{3, \ sigma-0.1 a ^ {-dagger}\_{1, \ sigma} a ^ {\ dagger}\_{6, \r ho} a\_{3, \r ho} a\_{2, \ sigma} a ^ {-dagger}\_{1,-sigma} a ^ {-dagger}\_0.1 {6, \r ho} a\_{2, \r ho} a\_{3, \ sigma} $ $ $ $-0.1 a ^ {-dagger}\_{3, \ sigma} a ^ {\ dagger}\_{2, \r ho} a\_{6, \r ho} a\_{1, \ sigma-0.1 a ^ {-dagger}\_{3,、\ sigma} a ^ {\ dagger}\_{2, \r ho} a\_{1, \r ho} a\_{1, \r ho} a {6, \ sig\_0.1 ma} a ^ {2,-sigma} a ^ {& dagger}\_{3, \r ho} a\_{6, \r ho} a\_{1,/sigma\_-0.1 a ^ {-dagger}\_{2,/sigma} a ^ {-dagger}\_{3, \r ho} a {1, \r ho} a\_{6,/sigma/biggr)\\, \T extrm{ha$。</span><span class="sxs-lookup"><span data-stu-id="245ad-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="245ad-198">パーティクル–穴表現オブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="245ad-199">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-199">This section is normative.</span></span>

<span data-ttu-id="245ad-200">パーティクル–穴表現オブジェクトは、格納されている積分がパーティクル穴の表現に対して定義されていることを指定します。この場合、作成演算子と annihilation 演算子では、使用されている参照状態 (たとえば、[excitations]) から離れた場所にが記述されます。Fock 状態です。</span><span class="sxs-lookup"><span data-stu-id="245ad-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="245ad-201">オブジェクトは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="245ad-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="245ad-202">オブジェクトが指定されていない場合、Hamiltonian は、パーティクル穴の表現で指定されていないと解釈されます。</span><span class="sxs-lookup"><span data-stu-id="245ad-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="245ad-203">存在する場合、`particle_hole_representation` の値は、インデックスが4つの整数で、値が数値と文字列であるスパース配列の quantity オブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="245ad-204">各要素の値の文字列部分には `'+'` および `'-'` 文字だけを含める必要があります。これは、用語の特定の係数が、パーティクルの穴表現で作成または annihilation 演算子であるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="245ad-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="245ad-205">たとえば `"-+++"` サイト $i $ で作成された穴と、サイト $j、k $、$l $ に作成されているパーティクルです。</span><span class="sxs-lookup"><span data-stu-id="245ad-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="245ad-206">`particle_hole_representation` の値がスパース配列の quantity オブジェクトであるため、`unit` プロパティと `format` プロパティを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="245ad-207">表1に、許容される単位が含まれています。</span><span class="sxs-lookup"><span data-stu-id="245ad-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="245ad-208">`format` プロパティは必須であり、Hamiltonian 係数が高密度またはスパース配列として指定されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="245ad-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="245ad-209">現在のバージョンでは、スパース配列のみがサポートされています。指定されていない要素はすべて $0 $ ですが、将来のバージョンでは `format` プロパティの追加の値のサポートが追加される場合があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="245ad-210">初期状態セクション</span><span class="sxs-lookup"><span data-stu-id="245ad-210">Initial State Section</span></span> ###

<span data-ttu-id="245ad-211">Initial_state_suggestion オブジェクトは、指定された Hamiltonian の最初のクォンタム状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="245ad-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="245ad-212">このオブジェクトは、JSON `state` オブジェクトの配列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="245ad-213">状態オブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-213">State object</span></span> ####

<span data-ttu-id="245ad-214">各状態は、占有の法則を表します。</span><span class="sxs-lookup"><span data-stu-id="245ad-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="245ad-215">各状態オブジェクトには、文字列を含む `label` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="245ad-216">各状態オブジェクトには、ベース状態の配列とその正規化されていない振幅を含む `superposition` プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="245ad-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="245ad-217">たとえば、初期状態 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\ dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ket}){0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {-dagger}\_{1, \uparrow}a ^ {\ dagger}\_{2, \uparrow}a ^ {\ dagger}\_{2, \ down}) + 0.2 (a ^ {-dagger}\_{1, \uparrow}a ^ {\ dagger}\_{3, \uparrow}a ^ {\ dagger}\_{2, \ down})} {\ sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket{0} $ $ が表されていますは</span><span class="sxs-lookup"><span data-stu-id="245ad-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="245ad-218">ベースセットオブジェクト</span><span class="sxs-lookup"><span data-stu-id="245ad-218">Basis Set Object</span></span> ####

<span data-ttu-id="245ad-219">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-219">This section is normative.</span></span>

<span data-ttu-id="245ad-220">各整数セットオブジェクトは、`basis_set` プロパティを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="245ad-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="245ad-221">存在する場合、`basis_set` プロパティの値は、`type` と `name`の2つのプロパティを持つオブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="245ad-222">`basis_set` プロパティの値によって識別されるベース関数は、実際の値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="245ad-223">この仕様の将来のバージョンでは、すべての基礎関数が実際の値であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="245ad-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="245ad-224">テーブルとリスト</span><span class="sxs-lookup"><span data-stu-id="245ad-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="245ad-225">テーブル 1。</span><span class="sxs-lookup"><span data-stu-id="245ad-225">Table 1.</span></span> <span data-ttu-id="245ad-226">許可される物理ユニット</span><span class="sxs-lookup"><span data-stu-id="245ad-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="245ad-227">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-227">This section is normative.</span></span>

<span data-ttu-id="245ad-228">単位を指定する文字列は、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="245ad-229">パーサーとプロデューサーは、次の単純な quantity オブジェクトを同等として扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="245ad-230">表 2.</span><span class="sxs-lookup"><span data-stu-id="245ad-230">Table 2.</span></span> <span data-ttu-id="245ad-231">許可されるインデックスの規則</span><span class="sxs-lookup"><span data-stu-id="245ad-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="245ad-232">このセクションは non-normative です。</span><span class="sxs-lookup"><span data-stu-id="245ad-232">This section is normative.</span></span>

<span data-ttu-id="245ad-233">インデックス規則を指定する文字列は、次のいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="245ad-234">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-234">This section is informative.</span></span>

<span data-ttu-id="245ad-235">この仕様の将来のバージョンでは、追加のインデックス規則が導入される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="245ad-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="245ad-236">インデックス規則の解釈</span><span class="sxs-lookup"><span data-stu-id="245ad-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="245ad-237">このセクションは有益です。</span><span class="sxs-lookup"><span data-stu-id="245ad-237">This section is informative.</span></span>
