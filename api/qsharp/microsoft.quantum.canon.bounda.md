---
uid: Microsoft.Quantum.Canon.BoundA
title: BoundA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216950"
---
# <a name="bounda-function"></a><span data-ttu-id="59fca-102">BoundA</span><span class="sxs-lookup"><span data-stu-id="59fca-102">BoundA function</span></span>

<span data-ttu-id="59fca-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59fca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59fca-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59fca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59fca-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="59fca-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="59fca-106">修飾子は、 `A` 配列内のすべての操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="59fca-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="59fca-107">入力</span><span class="sxs-lookup"><span data-stu-id="59fca-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="59fca-108">操作: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 []</span><span class="sxs-lookup"><span data-stu-id="59fca-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="59fca-109">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="59fca-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="59fca-110">出力: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="59fca-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="59fca-111">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="59fca-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="59fca-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="59fca-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59fca-113">&</span><span class="sxs-lookup"><span data-stu-id="59fca-113">'T</span></span>

<span data-ttu-id="59fca-114">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="59fca-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="59fca-115">参照</span><span class="sxs-lookup"><span data-stu-id="59fca-115">See Also</span></span>

- [<span data-ttu-id="59fca-116">Microsoft......</span><span class="sxs-lookup"><span data-stu-id="59fca-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)