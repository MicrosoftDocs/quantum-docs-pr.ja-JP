---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716690"
---
# <a name="bounda-function"></a><span data-ttu-id="d6421-102">BoundA</span><span class="sxs-lookup"><span data-stu-id="d6421-102">BoundA function</span></span>

<span data-ttu-id="d6421-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d6421-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d6421-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d6421-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d6421-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6421-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="d6421-106">修飾子は、 `A` 配列内のすべての操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="d6421-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="d6421-107">入力</span><span class="sxs-lookup"><span data-stu-id="d6421-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="d6421-108">操作: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 []</span><span class="sxs-lookup"><span data-stu-id="d6421-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="d6421-109">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="d6421-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="d6421-110">出力: t => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="d6421-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d6421-111">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="d6421-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d6421-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6421-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d6421-113">&</span><span class="sxs-lookup"><span data-stu-id="d6421-113">'T</span></span>

<span data-ttu-id="d6421-114">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="d6421-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6421-115">参照</span><span class="sxs-lookup"><span data-stu-id="d6421-115">See Also</span></span>

- [<span data-ttu-id="d6421-116">Microsoft......</span><span class="sxs-lookup"><span data-stu-id="d6421-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)