---
title: '標準ライブラリの数値演算 Q#'
description: '組み込みデータ型で使用される標準ライブラリの典型的な数学関数について説明 Q# します。'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692057"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="c909b-103">古典数学関数</span><span class="sxs-lookup"><span data-stu-id="c909b-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="c909b-104">これらの関数は、主に、組み込みのデータ型、、およびを操作するために使用され Q# `Int` `Double` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="c909b-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="c909b-105">この <xref:Microsoft.Quantum.Intrinsic.Random> 操作には署名があり `(Double[] => Int)` ます。</span><span class="sxs-lookup"><span data-stu-id="c909b-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="c909b-106">このメソッドは、入力として double の配列を取得し、ランダムに選択されたインデックスをとして配列に返し `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="c909b-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="c909b-107">特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。</span><span class="sxs-lookup"><span data-stu-id="c909b-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="c909b-108">0に等しい n 個の配列要素は無視され、そのインデックスは返されません。</span><span class="sxs-lookup"><span data-stu-id="c909b-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="c909b-109">配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="c909b-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
