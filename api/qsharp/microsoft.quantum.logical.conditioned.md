---
uid: Microsoft.Quantum.Logical.Conditioned
title: 条件付き関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198488"
---
# <a name="conditioned-function"></a><span data-ttu-id="84611-102">条件付き関数</span><span class="sxs-lookup"><span data-stu-id="84611-102">Conditioned function</span></span>

<span data-ttu-id="84611-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="84611-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="84611-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84611-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84611-105">ブール条件の値に応じて、2つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="84611-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="84611-106">入力</span><span class="sxs-lookup"><span data-stu-id="84611-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="84611-107">条件: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="84611-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="84611-108">返される入力を制御するために使用される条件。</span><span class="sxs-lookup"><span data-stu-id="84611-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="84611-109">ifTrue: ' t '</span><span class="sxs-lookup"><span data-stu-id="84611-109">ifTrue : 'T</span></span>

<span data-ttu-id="84611-110">がの場合に返される `condition` 値 `true` 。</span><span class="sxs-lookup"><span data-stu-id="84611-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="84611-111">ifFalse: t</span><span class="sxs-lookup"><span data-stu-id="84611-111">ifFalse : 'T</span></span>

<span data-ttu-id="84611-112">がの場合に返される `condition` 値 `false` 。</span><span class="sxs-lookup"><span data-stu-id="84611-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="84611-113">出力: t</span><span class="sxs-lookup"><span data-stu-id="84611-113">Output : 'T</span></span>

<span data-ttu-id="84611-114">`ifTrue``condition`が `true` の場合は `ifFalse` 。それ以外の場合は。</span><span class="sxs-lookup"><span data-stu-id="84611-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="84611-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="84611-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84611-116">&</span><span class="sxs-lookup"><span data-stu-id="84611-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="84611-117">解説</span><span class="sxs-lookup"><span data-stu-id="84611-117">Remarks</span></span>

<span data-ttu-id="84611-118">演算子とは異なり `?|` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="84611-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="84611-119">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="84611-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```