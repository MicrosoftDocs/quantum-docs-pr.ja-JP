---
uid: Microsoft.Quantum.Logical.Conditioned
title: 条件付き関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720787"
---
# <a name="conditioned-function"></a><span data-ttu-id="23317-102">条件付き関数</span><span class="sxs-lookup"><span data-stu-id="23317-102">Conditioned function</span></span>

<span data-ttu-id="23317-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="23317-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="23317-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23317-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23317-105">ブール条件の値に応じて、2つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="23317-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="23317-106">入力</span><span class="sxs-lookup"><span data-stu-id="23317-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="23317-107">条件: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="23317-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23317-108">返される入力を制御するために使用される条件。</span><span class="sxs-lookup"><span data-stu-id="23317-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="23317-109">ifTrue: ' t '</span><span class="sxs-lookup"><span data-stu-id="23317-109">ifTrue : 'T</span></span>

<span data-ttu-id="23317-110">がの場合に返される `condition` 値 `true` 。</span><span class="sxs-lookup"><span data-stu-id="23317-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="23317-111">ifFalse: t</span><span class="sxs-lookup"><span data-stu-id="23317-111">ifFalse : 'T</span></span>

<span data-ttu-id="23317-112">がの場合に返される `condition` 値 `false` 。</span><span class="sxs-lookup"><span data-stu-id="23317-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="23317-113">出力: t</span><span class="sxs-lookup"><span data-stu-id="23317-113">Output : 'T</span></span>

<span data-ttu-id="23317-114">`ifTrue``condition`が `true` の場合は `ifFalse` 。それ以外の場合は。</span><span class="sxs-lookup"><span data-stu-id="23317-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23317-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="23317-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23317-116">&</span><span class="sxs-lookup"><span data-stu-id="23317-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="23317-117">解説</span><span class="sxs-lookup"><span data-stu-id="23317-117">Remarks</span></span>

<span data-ttu-id="23317-118">演算子とは異なり `?|` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="23317-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="23317-119">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="23317-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```