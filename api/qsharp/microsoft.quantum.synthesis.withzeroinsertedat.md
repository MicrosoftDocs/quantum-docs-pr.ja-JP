---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withゼロの付いた関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228867"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="6e873-102">Withゼロの付いた関数</span><span class="sxs-lookup"><span data-stu-id="6e873-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="6e873-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="6e873-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="6e873-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e873-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e873-105">0ビットを整数に挿入する</span><span class="sxs-lookup"><span data-stu-id="6e873-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="6e873-106">説明</span><span class="sxs-lookup"><span data-stu-id="6e873-106">Description</span></span>

<span data-ttu-id="6e873-107">この操作では、整数を取得し、ビットを0に挿入して、 `position` 更新された値を整数として返します。</span><span class="sxs-lookup"><span data-stu-id="6e873-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="6e873-108">たとえば、数値 10 ($10 _ = 1010_ $) の位置2に0を挿入すると、 {10} {2} 数値 18 ($18 _ {10} = 10010_ {2} $) が返されます。</span><span class="sxs-lookup"><span data-stu-id="6e873-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="6e873-109">入力</span><span class="sxs-lookup"><span data-stu-id="6e873-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="6e873-110">position: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e873-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e873-111">0が挿入される位置。</span><span class="sxs-lookup"><span data-stu-id="6e873-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="6e873-112">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e873-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e873-113">変更される値</span><span class="sxs-lookup"><span data-stu-id="6e873-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="6e873-114">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6e873-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6e873-115">変更された値</span><span class="sxs-lookup"><span data-stu-id="6e873-115">Modified value</span></span>