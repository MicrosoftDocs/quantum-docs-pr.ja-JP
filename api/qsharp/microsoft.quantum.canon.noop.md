---
uid: Microsoft.Quantum.Canon.NoOp
title: NoOp 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: NoOp
qsharp.summary: Performs the identity operation (no-op) on an argument.
ms.openlocfilehash: 35b6b62cab35f941f04b150dcca763457ddaa084
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205968"
---
# <a name="noop-operation"></a><span data-ttu-id="fdf97-102">NoOp 操作</span><span class="sxs-lookup"><span data-stu-id="fdf97-102">NoOp operation</span></span>

<span data-ttu-id="fdf97-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fdf97-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fdf97-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fdf97-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fdf97-105">引数に対して identity 操作 (no op) を実行します。</span><span class="sxs-lookup"><span data-stu-id="fdf97-105">Performs the identity operation (no-op) on an argument.</span></span>

```qsharp
operation NoOp<'T> (input : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="fdf97-106">説明</span><span class="sxs-lookup"><span data-stu-id="fdf97-106">Description</span></span>

<span data-ttu-id="fdf97-107">この操作では、任意の型の値を取得し、それに対して何も実行しません。</span><span class="sxs-lookup"><span data-stu-id="fdf97-107">This operation takes a value of any type and does nothing to it.</span></span>
<span data-ttu-id="fdf97-108">これは、操作の種類の入力が必要な場合には常に役立ちますが、アクションを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fdf97-108">This can be useful whenever an input of an operation type is expected, but no action should be taken.</span></span>
<span data-ttu-id="fdf97-109">たとえば、特定のエラー修正より隣人によってエラーが発生していないことが示された場合は、 `NoOp<Qubit[]>` 適切な回復手順である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fdf97-109">For instance, if a particular error correction syndrome indicates that no error has occurred, `NoOp<Qubit[]>` may be the correct recovery procedure.</span></span>
<span data-ttu-id="fdf97-110">同様に、操作で状態の準備手順を入力と想定している場合は、を使用して、 `NoOp<Qubit[]>` 状態 $ \ket{0 \ cドット 0} $ を準備できます。</span><span class="sxs-lookup"><span data-stu-id="fdf97-110">Similarly, if an operation expects a state preparation procedure as input, `NoOp<Qubit[]>` can be used to prepare the state $\ket{0 \cdots 0}$.</span></span>

## <a name="input"></a><span data-ttu-id="fdf97-111">入力</span><span class="sxs-lookup"><span data-stu-id="fdf97-111">Input</span></span>

### <a name="input--t"></a><span data-ttu-id="fdf97-112">入力: ' t</span><span class="sxs-lookup"><span data-stu-id="fdf97-112">input : 'T</span></span>

<span data-ttu-id="fdf97-113">無視する値。</span><span class="sxs-lookup"><span data-stu-id="fdf97-113">A value to be ignored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fdf97-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fdf97-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fdf97-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdf97-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fdf97-116">&</span><span class="sxs-lookup"><span data-stu-id="fdf97-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="fdf97-117">解説</span><span class="sxs-lookup"><span data-stu-id="fdf97-117">Remarks</span></span>

<span data-ttu-id="fdf97-118">ほとんどの場合、の型パラメーターは `NoOp` 明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdf97-118">In almost all cases, the type parameter for `NoOp` needs to be specified explicitly.</span></span> <span data-ttu-id="fdf97-119">たとえば、 `NoOp<Qubit>` はと同じです <xref:microsoft.quantum.intrinsic.i> 。</span><span class="sxs-lookup"><span data-stu-id="fdf97-119">For instance, `NoOp<Qubit>` is identical to <xref:microsoft.quantum.intrinsic.i>.</span></span>

## <a name="see-also"></a><span data-ttu-id="fdf97-120">参照</span><span class="sxs-lookup"><span data-stu-id="fdf97-120">See Also</span></span>

- [<span data-ttu-id="fdf97-121">Microsoft. Quantum. I</span><span class="sxs-lookup"><span data-stu-id="fdf97-121">Microsoft.Quantum.Intrinsic.I</span></span>](xref:Microsoft.Quantum.Intrinsic.I)