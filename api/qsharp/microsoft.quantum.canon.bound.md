---
uid: Microsoft.Quantum.Canon.Bound
title: バインドされた関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207600"
---
# <a name="bound-function"></a><span data-ttu-id="17d16-102">バインドされた関数</span><span class="sxs-lookup"><span data-stu-id="17d16-102">Bound function</span></span>

<span data-ttu-id="17d16-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17d16-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17d16-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17d16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17d16-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="17d16-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="17d16-106">入力</span><span class="sxs-lookup"><span data-stu-id="17d16-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="17d16-107">操作: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="17d16-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="17d16-108">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="17d16-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="17d16-109">出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17d16-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="17d16-110">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="17d16-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="17d16-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="17d16-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17d16-112">&</span><span class="sxs-lookup"><span data-stu-id="17d16-112">'T</span></span>

<span data-ttu-id="17d16-113">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="17d16-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="17d16-114">参照</span><span class="sxs-lookup"><span data-stu-id="17d16-114">See Also</span></span>

- [<span data-ttu-id="17d16-115">Microsoft. BoundC</span><span class="sxs-lookup"><span data-stu-id="17d16-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="17d16-116">Microsoft. Canon. BoundA</span><span class="sxs-lookup"><span data-stu-id="17d16-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="17d16-117">Microsoft............... Fr-ca</span><span class="sxs-lookup"><span data-stu-id="17d16-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)