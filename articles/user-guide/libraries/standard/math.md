---
title: 標準ライブラリの数値演算 Q#
description: 組み込みデータ型で使用される標準ライブラリの典型的な数学関数について説明 Q# します。
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853988"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="72a71-103">古典数学関数</span><span class="sxs-lookup"><span data-stu-id="72a71-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="72a71-104">これらの関数は、主に、組み込みのデータ型、、およびを操作するために使用され Q# `Int` `Double` `Range` ます。</span><span class="sxs-lookup"><span data-stu-id="72a71-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="72a71-105">この <xref:Microsoft.Quantum.Intrinsic.Random> 操作には署名があり `(Double[] => Int)` ます。</span><span class="sxs-lookup"><span data-stu-id="72a71-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="72a71-106">このメソッドは、入力として double の配列を取得し、ランダムに選択されたインデックスをとして配列に返し `Int` ます。</span><span class="sxs-lookup"><span data-stu-id="72a71-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="72a71-107">特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。</span><span class="sxs-lookup"><span data-stu-id="72a71-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="72a71-108">0に等しい n 個の配列要素は無視され、そのインデックスは返されません。</span><span class="sxs-lookup"><span data-stu-id="72a71-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="72a71-109">配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="72a71-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
