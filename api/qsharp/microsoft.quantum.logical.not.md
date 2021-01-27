---
uid: Microsoft.Quantum.Logical.Not
title: Not 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849089"
---
# <a name="not-function"></a><span data-ttu-id="ce87c-102">Not 関数</span><span class="sxs-lookup"><span data-stu-id="ce87c-102">Not function</span></span>

<span data-ttu-id="ce87c-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ce87c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ce87c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce87c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce87c-105">値のブール型の否定を返します。</span><span class="sxs-lookup"><span data-stu-id="ce87c-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="ce87c-106">入力</span><span class="sxs-lookup"><span data-stu-id="ce87c-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="ce87c-107">値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ce87c-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ce87c-108">符号を反転する値。</span><span class="sxs-lookup"><span data-stu-id="ce87c-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ce87c-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ce87c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ce87c-110">`true``value`がの場合にのみ `false` 。</span><span class="sxs-lookup"><span data-stu-id="ce87c-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce87c-111">解説</span><span class="sxs-lookup"><span data-stu-id="ce87c-111">Remarks</span></span>

<span data-ttu-id="ce87c-112">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="ce87c-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```