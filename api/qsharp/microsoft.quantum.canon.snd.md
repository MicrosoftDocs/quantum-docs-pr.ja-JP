---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205322"
---
# <a name="snd-function"></a><span data-ttu-id="14cf1-102">Snd 関数</span><span class="sxs-lookup"><span data-stu-id="14cf1-102">Snd function</span></span>

<span data-ttu-id="14cf1-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14cf1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14cf1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14cf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14cf1-105">ペアが指定されると、はその2番目の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="14cf1-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="14cf1-106">入力</span><span class="sxs-lookup"><span data-stu-id="14cf1-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="14cf1-107">pair: (' U '、' U)</span><span class="sxs-lookup"><span data-stu-id="14cf1-107">pair : ('T,'U)</span></span>

<span data-ttu-id="14cf1-108">2つの要素を持つタプル。</span><span class="sxs-lookup"><span data-stu-id="14cf1-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="14cf1-109">出力: ' U</span><span class="sxs-lookup"><span data-stu-id="14cf1-109">Output : 'U</span></span>

<span data-ttu-id="14cf1-110">の2番目の要素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="14cf1-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="14cf1-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="14cf1-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14cf1-112">&</span><span class="sxs-lookup"><span data-stu-id="14cf1-112">'T</span></span>

<span data-ttu-id="14cf1-113">ペアの最初のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="14cf1-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="14cf1-114">' U</span><span class="sxs-lookup"><span data-stu-id="14cf1-114">'U</span></span>

<span data-ttu-id="14cf1-115">ペアの2番目のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="14cf1-115">The type of the pair's second member.</span></span>