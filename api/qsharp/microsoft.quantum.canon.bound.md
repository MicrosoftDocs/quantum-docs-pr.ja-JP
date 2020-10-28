---
uid: Microsoft.Quantum.Canon.Bound
title: バインドされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716704"
---
# <a name="bound-function"></a><span data-ttu-id="e94f8-102">バインドされた関数</span><span class="sxs-lookup"><span data-stu-id="e94f8-102">Bound function</span></span>

<span data-ttu-id="e94f8-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e94f8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e94f8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e94f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e94f8-105">1つの入力に対して動作する操作の配列を指定すると、によって、指定された各操作を順番に実行する新しい操作が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e94f8-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="e94f8-106">入力</span><span class="sxs-lookup"><span data-stu-id="e94f8-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="e94f8-107">操作: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="e94f8-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="e94f8-108">指定された入力に対して実行される一連の操作。</span><span class="sxs-lookup"><span data-stu-id="e94f8-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="e94f8-109">出力: t => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e94f8-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e94f8-110">入力に基づいて指定された各操作を順番に実行する新しい操作。</span><span class="sxs-lookup"><span data-stu-id="e94f8-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e94f8-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e94f8-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e94f8-112">&</span><span class="sxs-lookup"><span data-stu-id="e94f8-112">'T</span></span>

<span data-ttu-id="e94f8-113">配列内の各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="e94f8-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="e94f8-114">参照</span><span class="sxs-lookup"><span data-stu-id="e94f8-114">See Also</span></span>

- [<span data-ttu-id="e94f8-115">Microsoft. BoundC</span><span class="sxs-lookup"><span data-stu-id="e94f8-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="e94f8-116">Microsoft. Canon. BoundA</span><span class="sxs-lookup"><span data-stu-id="e94f8-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="e94f8-117">Microsoft............... Fr-ca</span><span class="sxs-lookup"><span data-stu-id="e94f8-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)