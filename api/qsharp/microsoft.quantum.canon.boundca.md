---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716634"
---
# <a name="boundca-function"></a><span data-ttu-id="460ed-102">BoundCA 関数</span><span class="sxs-lookup"><span data-stu-id="460ed-102">BoundCA function</span></span>

<span data-ttu-id="460ed-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="460ed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="460ed-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="460ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="460ed-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="460ed-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="460ed-106">修飾子は、 `CA` 配列内のすべての操作が adjointable および制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="460ed-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="460ed-107">入力</span><span class="sxs-lookup"><span data-stu-id="460ed-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="460ed-108">操作: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="460ed-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="460ed-109">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="460ed-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="460ed-110">出力: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="460ed-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="460ed-111">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="460ed-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="460ed-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="460ed-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="460ed-113">&</span><span class="sxs-lookup"><span data-stu-id="460ed-113">'T</span></span>

<span data-ttu-id="460ed-114">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="460ed-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="460ed-115">参照</span><span class="sxs-lookup"><span data-stu-id="460ed-115">See Also</span></span>

- [<span data-ttu-id="460ed-116">Microsoft......</span><span class="sxs-lookup"><span data-stu-id="460ed-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)