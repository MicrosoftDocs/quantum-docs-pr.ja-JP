---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716186"
---
# <a name="fst-function"></a><span data-ttu-id="d32c1-102">Fst 関数</span><span class="sxs-lookup"><span data-stu-id="d32c1-102">Fst function</span></span>

<span data-ttu-id="d32c1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d32c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d32c1-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d32c1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d32c1-105">ペアが指定されている場合、最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="d32c1-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="d32c1-106">入力</span><span class="sxs-lookup"><span data-stu-id="d32c1-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="d32c1-107">pair: (' U '、' U)</span><span class="sxs-lookup"><span data-stu-id="d32c1-107">pair : ('T,'U)</span></span>

<span data-ttu-id="d32c1-108">2つの要素を持つタプル。</span><span class="sxs-lookup"><span data-stu-id="d32c1-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="d32c1-109">出力: t</span><span class="sxs-lookup"><span data-stu-id="d32c1-109">Output : 'T</span></span>

<span data-ttu-id="d32c1-110">`pair` の最初の要素。</span><span class="sxs-lookup"><span data-stu-id="d32c1-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d32c1-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d32c1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d32c1-112">&</span><span class="sxs-lookup"><span data-stu-id="d32c1-112">'T</span></span>

<span data-ttu-id="d32c1-113">ペアの最初のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="d32c1-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="d32c1-114">' U</span><span class="sxs-lookup"><span data-stu-id="d32c1-114">'U</span></span>

<span data-ttu-id="d32c1-115">ペアの2番目のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="d32c1-115">The type of the pair's second member.</span></span>