---
uid: Microsoft.Quantum.Canon.Snd
title: Snd 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715449"
---
# <a name="snd-function"></a><span data-ttu-id="f0db2-102">Snd 関数</span><span class="sxs-lookup"><span data-stu-id="f0db2-102">Snd function</span></span>

<span data-ttu-id="f0db2-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0db2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0db2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0db2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0db2-105">ペアが指定されると、はその2番目の要素を返します。</span><span class="sxs-lookup"><span data-stu-id="f0db2-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="f0db2-106">入力</span><span class="sxs-lookup"><span data-stu-id="f0db2-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="f0db2-107">pair: (' U '、' U)</span><span class="sxs-lookup"><span data-stu-id="f0db2-107">pair : ('T,'U)</span></span>

<span data-ttu-id="f0db2-108">2つの要素を持つタプル。</span><span class="sxs-lookup"><span data-stu-id="f0db2-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="f0db2-109">出力: ' U</span><span class="sxs-lookup"><span data-stu-id="f0db2-109">Output : 'U</span></span>

<span data-ttu-id="f0db2-110">の2番目の要素 `pair` 。</span><span class="sxs-lookup"><span data-stu-id="f0db2-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0db2-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f0db2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f0db2-112">&</span><span class="sxs-lookup"><span data-stu-id="f0db2-112">'T</span></span>

<span data-ttu-id="f0db2-113">ペアの最初のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="f0db2-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="f0db2-114">' U</span><span class="sxs-lookup"><span data-stu-id="f0db2-114">'U</span></span>

<span data-ttu-id="f0db2-115">ペアの2番目のメンバーの型。</span><span class="sxs-lookup"><span data-stu-id="f0db2-115">The type of the pair's second member.</span></span>