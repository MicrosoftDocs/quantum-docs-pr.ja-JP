---
title: Q# プログラミング言語
description: 量子プログラム開発のための Q# 言語の概要。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: b62e6866fc3609d95c26a5eab2a6eac325dfe330
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907377"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="0768d-103">Q# プログラミング言語</span><span class="sxs-lookup"><span data-stu-id="0768d-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="0768d-104">はじめに</span><span class="sxs-lookup"><span data-stu-id="0768d-104">Introduction</span></span>

<span data-ttu-id="0768d-105">量子コンピューティングの自然モデルは、GPU、FPGA、およびその他の補完プロセッサで使用されるものと同様に、量子コンピューターをコプロセッサとして扱います。</span><span class="sxs-lookup"><span data-stu-id="0768d-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="0768d-106">主要な制御ロジックは、従来の "ホスト" コンピューターでクラシック コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="0768d-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="0768d-107">必要に応じて、ホスト プログラムは補完プロセッサ上で実行されるサブルーチンを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="0768d-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="0768d-108">サブルーチンが完了すると、ホスト プログラムはサブルーチンの結果にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="0768d-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="0768d-109">Q# (Q シャープ) は、量子アルゴリズムの表現に使用されるドメイン固有のプログラミング言語です。</span><span class="sxs-lookup"><span data-stu-id="0768d-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="0768d-110">これは、従来型のホスト プログラムとコンピューターのコントロール下で、補完量子プロセッサ上で実行されるサブルーチンの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="0768d-111">量子プロセッサが普及するまで、Q# サブルーチンはシミュレーターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="0768d-112">Q# には、プリミティブ型の小さなセットと、新しい構造化型を作成するための 2 つの方法 (配列とタプル) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0768d-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="0768d-113">ループと if/then ステートメントを使用してプログラムを作成するための基本的な手続き型のモデルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0768d-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="0768d-114">Q# の最上位レベルのコンストラクトは、ユーザー定義型、操作、および関数です。</span><span class="sxs-lookup"><span data-stu-id="0768d-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="0768d-115">次のセクションで詳細を説明します。</span><span class="sxs-lookup"><span data-stu-id="0768d-115">The following sections detail:</span></span>
- [<span data-ttu-id="0768d-116">タイプ モデル</span><span class="sxs-lookup"><span data-stu-id="0768d-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="0768d-117">式</span><span class="sxs-lookup"><span data-stu-id="0768d-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="0768d-118">ステートメント</span><span class="sxs-lookup"><span data-stu-id="0768d-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="0768d-119">ファイル構造</span><span class="sxs-lookup"><span data-stu-id="0768d-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="0768d-120">規則</span><span class="sxs-lookup"><span data-stu-id="0768d-120">Conventions</span></span>

<span data-ttu-id="0768d-121">一般的な句読点がすべての状況で一貫して使用されるようにするために取り組んでいます。</span><span class="sxs-lookup"><span data-stu-id="0768d-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="0768d-122">このような記号は常に同じことを意味し、同じ概念は常に同じ方法で表されるため、Q# が学習しやすく、かつ読みやすくなることが期待されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="0768d-123">具体的な内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0768d-123">Specifically:</span></span>

- <span data-ttu-id="0768d-124">セミコロン (`;`) は、ステートメントまたは単一行のディレクティブを終了するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="0768d-125">他の目的では使用できません。</span><span class="sxs-lookup"><span data-stu-id="0768d-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="0768d-126">コンマ (`,`) は、シーケンスの要素を区切るために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="0768d-127">これは、タプル リテラル、配列リテラル、引数リスト、タプル定義、および型リストに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="0768d-128">**以前のバージョンからの変更では、`;` は配列リテラルの区切りとしてサポートされなくなりました。**</span><span class="sxs-lookup"><span data-stu-id="0768d-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="0768d-129">コロン (`:`) は、型の注釈を挿入するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="0768d-130">これは主に呼び出し可能なシグネチャで使用されます。</span><span class="sxs-lookup"><span data-stu-id="0768d-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="0768d-131">コロンは常に型シグネチャを挿入するため、0.3 で導入された三項条件付き演算子では、垂直バー (`|`) を使用して、true と false の値を区切ります。このため、Q# では、コロンではなく、C のように `cond ? tval | fval` を 使用します。</span><span class="sxs-lookup"><span data-stu-id="0768d-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
