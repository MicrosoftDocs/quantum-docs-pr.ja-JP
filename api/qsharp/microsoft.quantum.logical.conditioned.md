---
uid: Microsoft.Quantum.Logical.Conditioned
title: 条件付き関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817301"
---
# <a name="conditioned-function"></a><span data-ttu-id="4bcbb-102">条件付き関数</span><span class="sxs-lookup"><span data-stu-id="4bcbb-102">Conditioned function</span></span>

<span data-ttu-id="4bcbb-103">名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4bcbb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4bcbb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4bcbb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4bcbb-105">ブール条件の値に応じて、2つの値のいずれかを返します。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="4bcbb-106">入力</span><span class="sxs-lookup"><span data-stu-id="4bcbb-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="4bcbb-107">条件: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4bcbb-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4bcbb-108">返される入力を制御するために使用される条件。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="4bcbb-109">ifTrue: ' t '</span><span class="sxs-lookup"><span data-stu-id="4bcbb-109">ifTrue : 'T</span></span>

<span data-ttu-id="4bcbb-110">がの場合に返される `condition` 値 `true` 。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="4bcbb-111">ifFalse: t</span><span class="sxs-lookup"><span data-stu-id="4bcbb-111">ifFalse : 'T</span></span>

<span data-ttu-id="4bcbb-112">がの場合に返される `condition` 値 `false` 。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="4bcbb-113">出力: t</span><span class="sxs-lookup"><span data-stu-id="4bcbb-113">Output : 'T</span></span>

<span data-ttu-id="4bcbb-114">`ifTrue``condition`が `true` の場合は `ifFalse` 。それ以外の場合は。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4bcbb-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4bcbb-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4bcbb-116">&</span><span class="sxs-lookup"><span data-stu-id="4bcbb-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="4bcbb-117">解説</span><span class="sxs-lookup"><span data-stu-id="4bcbb-117">Remarks</span></span>

<span data-ttu-id="4bcbb-118">演算子とは異なり `?|` 、この関数はショートサーキットではなく、両方の入力が完全に評価されます。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="4bcbb-119">ショートサーキットの動作は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4bcbb-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```