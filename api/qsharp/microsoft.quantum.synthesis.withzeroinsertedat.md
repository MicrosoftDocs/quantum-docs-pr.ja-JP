---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: Withゼロの付いた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855207"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="22610-102">Withゼロの付いた関数</span><span class="sxs-lookup"><span data-stu-id="22610-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="22610-103">名前空間: [Microsoft. Quantum. 合成](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="22610-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="22610-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22610-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22610-105">0ビットを整数に挿入する</span><span class="sxs-lookup"><span data-stu-id="22610-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="22610-106">説明</span><span class="sxs-lookup"><span data-stu-id="22610-106">Description</span></span>

<span data-ttu-id="22610-107">この操作では、整数を取得し、ビットを0に挿入して、 `position` 更新された値を整数として返します。</span><span class="sxs-lookup"><span data-stu-id="22610-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="22610-108">たとえば、数値 10 ($10 _ = 1010_ $) の位置2に0を挿入すると、 {10} {2} 数値 18 ($18 _ {10} = 10010_ {2} $) が返されます。</span><span class="sxs-lookup"><span data-stu-id="22610-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="22610-109">入力</span><span class="sxs-lookup"><span data-stu-id="22610-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="22610-110">position: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22610-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22610-111">0が挿入される位置。</span><span class="sxs-lookup"><span data-stu-id="22610-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="22610-112">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22610-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22610-113">変更される値</span><span class="sxs-lookup"><span data-stu-id="22610-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="22610-114">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="22610-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="22610-115">変更された値</span><span class="sxs-lookup"><span data-stu-id="22610-115">Modified value</span></span>