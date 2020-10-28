---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718231"
---
# <a name="applyifca-operation"></a><span data-ttu-id="260ce-102">ApplyIfCA 操作</span><span class="sxs-lookup"><span data-stu-id="260ce-102">ApplyIfCA operation</span></span>

<span data-ttu-id="260ce-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="260ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="260ce-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="260ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="260ce-105">古典的なビットに対して条件付きのユニタリ操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="260ce-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="260ce-106">説明</span><span class="sxs-lookup"><span data-stu-id="260ce-106">Description</span></span>

<span data-ttu-id="260ce-107">操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="260ce-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="260ce-108">`false`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="260ce-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="260ce-109">サフィックスは、 `CA` 適用される操作が、ユニタリ (制御可能および adjointable) であることを示します。</span><span class="sxs-lookup"><span data-stu-id="260ce-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="260ce-110">入力</span><span class="sxs-lookup"><span data-stu-id="260ce-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="260ce-111">op: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="260ce-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="260ce-112">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="260ce-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="260ce-113">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="260ce-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="260ce-114">op が適用されるかどうかを制御するブール値。</span><span class="sxs-lookup"><span data-stu-id="260ce-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="260ce-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="260ce-115">target : 'T</span></span>

<span data-ttu-id="260ce-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="260ce-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="260ce-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="260ce-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="260ce-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="260ce-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="260ce-119">&</span><span class="sxs-lookup"><span data-stu-id="260ce-119">'T</span></span>

<span data-ttu-id="260ce-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="260ce-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="260ce-121">参照</span><span class="sxs-lookup"><span data-stu-id="260ce-121">See Also</span></span>

- [<span data-ttu-id="260ce-122">Microsoft. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="260ce-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="260ce-123">Microsoft. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="260ce-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="260ce-124">Microsoft. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="260ce-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)