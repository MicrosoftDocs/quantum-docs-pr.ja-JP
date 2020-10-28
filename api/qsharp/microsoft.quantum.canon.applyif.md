---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718243"
---
# <a name="applyif-operation"></a><span data-ttu-id="1315c-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="1315c-102">ApplyIf operation</span></span>

<span data-ttu-id="1315c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1315c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1315c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1315c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1315c-105">従来のビットで条件付き操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="1315c-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="1315c-106">説明</span><span class="sxs-lookup"><span data-stu-id="1315c-106">Description</span></span>

<span data-ttu-id="1315c-107">操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="1315c-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="1315c-108">`false`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="1315c-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="1315c-109">入力</span><span class="sxs-lookup"><span data-stu-id="1315c-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="1315c-110">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1315c-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="1315c-111">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="1315c-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="1315c-112">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1315c-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1315c-113">op が適用されるかどうかを制御するブール値。</span><span class="sxs-lookup"><span data-stu-id="1315c-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="1315c-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="1315c-114">target : 'T</span></span>

<span data-ttu-id="1315c-115">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="1315c-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1315c-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1315c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1315c-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="1315c-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1315c-118">&</span><span class="sxs-lookup"><span data-stu-id="1315c-118">'T</span></span>

<span data-ttu-id="1315c-119">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="1315c-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1315c-120">参照</span><span class="sxs-lookup"><span data-stu-id="1315c-120">See Also</span></span>

- [<span data-ttu-id="1315c-121">Microsoft. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="1315c-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="1315c-122">Microsoft. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="1315c-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="1315c-123">Microsoft. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="1315c-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)