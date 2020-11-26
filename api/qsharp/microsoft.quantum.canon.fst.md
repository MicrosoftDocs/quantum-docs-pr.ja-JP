---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206937"
---
# <a name="fst-function"></a><span data-ttu-id="8da87-102">Fst 関数</span><span class="sxs-lookup"><span data-stu-id="8da87-102">Fst function</span></span>

<span data-ttu-id="8da87-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8da87-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8da87-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8da87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8da87-105">ペアが指定されている場合、最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="8da87-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="8da87-106">入力</span><span class="sxs-lookup"><span data-stu-id="8da87-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="8da87-107">pair: (' U '、' U)</span><span class="sxs-lookup"><span data-stu-id="8da87-107">pair : ('T,'U)</span></span>

<span data-ttu-id="8da87-108">2つの要素を持つタプル。</span><span class="sxs-lookup"><span data-stu-id="8da87-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="8da87-109">出力: t</span><span class="sxs-lookup"><span data-stu-id="8da87-109">Output : 'T</span></span>

<span data-ttu-id="8da87-110">`pair` の最初の要素。</span><span class="sxs-lookup"><span data-stu-id="8da87-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8da87-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8da87-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8da87-112">&</span><span class="sxs-lookup"><span data-stu-id="8da87-112">'T</span></span>

<span data-ttu-id="8da87-113">ペアの最初のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="8da87-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="8da87-114">' U</span><span class="sxs-lookup"><span data-stu-id="8da87-114">'U</span></span>

<span data-ttu-id="8da87-115">ペアの2番目のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="8da87-115">The type of the pair's second member.</span></span>