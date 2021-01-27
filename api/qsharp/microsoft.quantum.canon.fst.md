---
uid: Microsoft.Quantum.Canon.Fst
title: Fst 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840519"
---
# <a name="fst-function"></a><span data-ttu-id="55d61-102">Fst 関数</span><span class="sxs-lookup"><span data-stu-id="55d61-102">Fst function</span></span>

<span data-ttu-id="55d61-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55d61-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55d61-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55d61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55d61-105">ペアが指定されている場合、最初の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="55d61-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="55d61-106">入力</span><span class="sxs-lookup"><span data-stu-id="55d61-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="55d61-107">pair: (' U '、' U)</span><span class="sxs-lookup"><span data-stu-id="55d61-107">pair : ('T,'U)</span></span>

<span data-ttu-id="55d61-108">2つの要素を持つタプル。</span><span class="sxs-lookup"><span data-stu-id="55d61-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="55d61-109">出力: t</span><span class="sxs-lookup"><span data-stu-id="55d61-109">Output : 'T</span></span>

<span data-ttu-id="55d61-110">`pair` の最初の要素。</span><span class="sxs-lookup"><span data-stu-id="55d61-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="55d61-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="55d61-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55d61-112">&</span><span class="sxs-lookup"><span data-stu-id="55d61-112">'T</span></span>

<span data-ttu-id="55d61-113">ペアの最初のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="55d61-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="55d61-114">' U</span><span class="sxs-lookup"><span data-stu-id="55d61-114">'U</span></span>

<span data-ttu-id="55d61-115">ペアの2番目のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="55d61-115">The type of the pair's second member.</span></span>