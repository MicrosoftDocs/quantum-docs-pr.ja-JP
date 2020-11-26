---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207583"
---
# <a name="boundc-function"></a><span data-ttu-id="92f9a-102">BoundC 関数</span><span class="sxs-lookup"><span data-stu-id="92f9a-102">BoundC function</span></span>

<span data-ttu-id="92f9a-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92f9a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92f9a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="92f9a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="92f9a-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="92f9a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="92f9a-106">修飾子は、 `C` 配列内のすべての操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="92f9a-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="92f9a-107">入力</span><span class="sxs-lookup"><span data-stu-id="92f9a-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="92f9a-108">操作: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl []</span><span class="sxs-lookup"><span data-stu-id="92f9a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="92f9a-109">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="92f9a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="92f9a-110">出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="92f9a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="92f9a-111">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="92f9a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="92f9a-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="92f9a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="92f9a-113">&</span><span class="sxs-lookup"><span data-stu-id="92f9a-113">'T</span></span>

<span data-ttu-id="92f9a-114">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="92f9a-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="92f9a-115">参照</span><span class="sxs-lookup"><span data-stu-id="92f9a-115">See Also</span></span>

- [<span data-ttu-id="92f9a-116">Microsoft......</span><span class="sxs-lookup"><span data-stu-id="92f9a-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)