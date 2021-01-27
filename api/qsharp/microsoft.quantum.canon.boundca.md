---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844526"
---
# <a name="boundca-function"></a><span data-ttu-id="db71a-102">BoundCA 関数</span><span class="sxs-lookup"><span data-stu-id="db71a-102">BoundCA function</span></span>

<span data-ttu-id="db71a-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="db71a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="db71a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="db71a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="db71a-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="db71a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="db71a-106">修飾子は、 `CA` 配列内のすべての操作が adjointable および制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="db71a-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="db71a-107">入力</span><span class="sxs-lookup"><span data-stu-id="db71a-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="db71a-108">操作: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="db71a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="db71a-109">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="db71a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="db71a-110">出力: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="db71a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="db71a-111">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="db71a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="db71a-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="db71a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="db71a-113">&</span><span class="sxs-lookup"><span data-stu-id="db71a-113">'T</span></span>

<span data-ttu-id="db71a-114">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="db71a-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="db71a-115">例</span><span class="sxs-lookup"><span data-stu-id="db71a-115">Example</span></span>

<span data-ttu-id="db71a-116">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="db71a-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="db71a-117">and</span><span class="sxs-lookup"><span data-stu-id="db71a-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="db71a-118">参照</span><span class="sxs-lookup"><span data-stu-id="db71a-118">See Also</span></span>

- [<span data-ttu-id="db71a-119">Microsoft......</span><span class="sxs-lookup"><span data-stu-id="db71a-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)