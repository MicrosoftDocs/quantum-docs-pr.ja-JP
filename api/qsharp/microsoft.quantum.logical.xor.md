---
uid: Microsoft.Quantum.Logical.Xor
title: Xor 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848448"
---
# <a name="xor-function"></a><span data-ttu-id="63fed-102">Xor 関数</span><span class="sxs-lookup"><span data-stu-id="63fed-102">Xor function</span></span>

<span data-ttu-id="63fed-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="63fed-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="63fed-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63fed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63fed-105">2つの値のブール型の排他的和を返します。</span><span class="sxs-lookup"><span data-stu-id="63fed-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="63fed-106">入力</span><span class="sxs-lookup"><span data-stu-id="63fed-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="63fed-107">a: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63fed-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63fed-108">考慮される最初の値。</span><span class="sxs-lookup"><span data-stu-id="63fed-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="63fed-109">b: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63fed-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63fed-110">考慮する2番目の値。</span><span class="sxs-lookup"><span data-stu-id="63fed-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="63fed-111">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="63fed-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63fed-112">`true` とのいずれかだけがの `a` 場合 `b` にのみ `true` 。</span><span class="sxs-lookup"><span data-stu-id="63fed-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>