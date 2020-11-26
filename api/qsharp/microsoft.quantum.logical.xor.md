---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197094"
---
# <a name="xor-function"></a><span data-ttu-id="5a750-102">Xor 関数</span><span class="sxs-lookup"><span data-stu-id="5a750-102">Xor function</span></span>

<span data-ttu-id="5a750-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5a750-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5a750-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5a750-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5a750-105">2つの値のブール型の排他的和を返します。</span><span class="sxs-lookup"><span data-stu-id="5a750-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="5a750-106">入力</span><span class="sxs-lookup"><span data-stu-id="5a750-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="5a750-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5a750-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5a750-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="5a750-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="5a750-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5a750-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5a750-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="5a750-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5a750-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5a750-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5a750-112">`true` とのいずれかだけがの `a` 場合 `b` にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="5a750-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>