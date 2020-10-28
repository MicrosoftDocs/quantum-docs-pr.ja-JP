---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723293"
---
# <a name="xor-function"></a><span data-ttu-id="1be79-102">Xor 関数</span><span class="sxs-lookup"><span data-stu-id="1be79-102">Xor function</span></span>

<span data-ttu-id="1be79-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="1be79-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="1be79-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1be79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1be79-105">2つの値のブール型の排他的和を返します。</span><span class="sxs-lookup"><span data-stu-id="1be79-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="1be79-106">入力</span><span class="sxs-lookup"><span data-stu-id="1be79-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="1be79-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1be79-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1be79-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="1be79-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="1be79-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1be79-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1be79-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="1be79-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1be79-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1be79-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1be79-112">`true` とのいずれかだけがの `a` 場合 `b` にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="1be79-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>