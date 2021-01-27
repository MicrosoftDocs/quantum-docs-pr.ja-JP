---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: 109a5c4748d183f199e420b4b1aef687613d220c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841881"
---
# <a name="applyif-operation"></a><span data-ttu-id="14e67-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="14e67-102">ApplyIf operation</span></span>

<span data-ttu-id="14e67-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14e67-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14e67-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14e67-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14e67-105">従来のビットで条件付き操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="14e67-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="14e67-106">説明</span><span class="sxs-lookup"><span data-stu-id="14e67-106">Description</span></span>

<span data-ttu-id="14e67-107">操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="14e67-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="14e67-108">`false`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="14e67-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="14e67-109">入力</span><span class="sxs-lookup"><span data-stu-id="14e67-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="14e67-110">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14e67-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="14e67-111">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="14e67-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="14e67-112">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="14e67-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="14e67-113">op が適用されるかどうかを制御するブール値。</span><span class="sxs-lookup"><span data-stu-id="14e67-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="14e67-114">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="14e67-114">target : 'T</span></span>

<span data-ttu-id="14e67-115">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="14e67-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14e67-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14e67-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="14e67-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="14e67-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14e67-118">&</span><span class="sxs-lookup"><span data-stu-id="14e67-118">'T</span></span>

<span data-ttu-id="14e67-119">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="14e67-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="14e67-120">例</span><span class="sxs-lookup"><span data-stu-id="14e67-120">Example</span></span>

<span data-ttu-id="14e67-121">次の例では、値の配列として指定された古典的なビット文字列によって表される計算基準の状態に qubits のレジスタを準備し `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="14e67-121">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="14e67-122">参照</span><span class="sxs-lookup"><span data-stu-id="14e67-122">See Also</span></span>

- [<span data-ttu-id="14e67-123">Microsoft. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="14e67-123">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="14e67-124">Microsoft. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="14e67-124">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="14e67-125">Microsoft. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="14e67-125">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)