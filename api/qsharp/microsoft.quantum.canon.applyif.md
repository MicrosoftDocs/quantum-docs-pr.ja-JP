---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218837"
---
# <a name="applyif-operation"></a><span data-ttu-id="be0d4-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="be0d4-102">ApplyIf operation</span></span>

<span data-ttu-id="be0d4-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be0d4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be0d4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be0d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be0d4-105">従来のビットで条件付き操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="be0d4-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="be0d4-106">説明</span><span class="sxs-lookup"><span data-stu-id="be0d4-106">Description</span></span>

<span data-ttu-id="be0d4-107">操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="be0d4-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="be0d4-108">`false`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="be0d4-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="be0d4-109">入力</span><span class="sxs-lookup"><span data-stu-id="be0d4-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="be0d4-110">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be0d4-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="be0d4-111">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="be0d4-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="be0d4-112">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="be0d4-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="be0d4-113">op が適用されるかどうかを制御するブール値。</span><span class="sxs-lookup"><span data-stu-id="be0d4-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="be0d4-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="be0d4-114">target : 'T</span></span>

<span data-ttu-id="be0d4-115">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="be0d4-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be0d4-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be0d4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="be0d4-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="be0d4-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be0d4-118">&</span><span class="sxs-lookup"><span data-stu-id="be0d4-118">'T</span></span>

<span data-ttu-id="be0d4-119">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="be0d4-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="be0d4-120">参照</span><span class="sxs-lookup"><span data-stu-id="be0d4-120">See Also</span></span>

- [<span data-ttu-id="be0d4-121">Microsoft. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="be0d4-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="be0d4-122">Microsoft. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="be0d4-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="be0d4-123">Microsoft. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="be0d4-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)