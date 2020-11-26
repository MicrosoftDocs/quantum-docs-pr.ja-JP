---
uid: Microsoft.Quantum.Logical.Not
title: Not 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197451"
---
# <a name="not-function"></a><span data-ttu-id="9cbed-102">Not 関数</span><span class="sxs-lookup"><span data-stu-id="9cbed-102">Not function</span></span>

<span data-ttu-id="9cbed-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="9cbed-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="9cbed-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9cbed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9cbed-105">値のブール型の否定を返します。</span><span class="sxs-lookup"><span data-stu-id="9cbed-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="9cbed-106">入力</span><span class="sxs-lookup"><span data-stu-id="9cbed-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="9cbed-107">値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9cbed-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9cbed-108">符号を反転する値。</span><span class="sxs-lookup"><span data-stu-id="9cbed-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9cbed-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9cbed-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9cbed-110">`true``value`がの場合にのみ `false` 。</span><span class="sxs-lookup"><span data-stu-id="9cbed-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9cbed-111">解説</span><span class="sxs-lookup"><span data-stu-id="9cbed-111">Remarks</span></span>

<span data-ttu-id="9cbed-112">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="9cbed-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```