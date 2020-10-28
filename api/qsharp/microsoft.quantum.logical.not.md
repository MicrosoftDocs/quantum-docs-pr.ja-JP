---
uid: Microsoft.Quantum.Logical.Not
title: Not 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709863"
---
# <a name="not-function"></a><span data-ttu-id="f0df8-102">Not 関数</span><span class="sxs-lookup"><span data-stu-id="f0df8-102">Not function</span></span>

<span data-ttu-id="f0df8-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f0df8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f0df8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0df8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0df8-105">値のブール型の否定を返します。</span><span class="sxs-lookup"><span data-stu-id="f0df8-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="f0df8-106">入力</span><span class="sxs-lookup"><span data-stu-id="f0df8-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="f0df8-107">値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0df8-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0df8-108">符号を反転する値。</span><span class="sxs-lookup"><span data-stu-id="f0df8-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f0df8-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f0df8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f0df8-110">`true``value`がの場合にのみ `false` 。</span><span class="sxs-lookup"><span data-stu-id="f0df8-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0df8-111">解説</span><span class="sxs-lookup"><span data-stu-id="f0df8-111">Remarks</span></span>

<span data-ttu-id="f0df8-112">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0df8-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```