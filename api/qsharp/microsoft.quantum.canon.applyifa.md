---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 8bdca1bf286d564dfbb540bc9d63c035d2196f00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845035"
---
# <a name="applyifa-operation"></a><span data-ttu-id="98990-102">ApplyIfA 操作</span><span class="sxs-lookup"><span data-stu-id="98990-102">ApplyIfA operation</span></span>

<span data-ttu-id="98990-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="98990-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="98990-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98990-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98990-105">クラシックビットで条件付き adjointable 操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="98990-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="98990-106">説明</span><span class="sxs-lookup"><span data-stu-id="98990-106">Description</span></span>

<span data-ttu-id="98990-107">操作とビット値を指定した場合は、 `op` `bit` `op` がの場合はに適用され `target` `bit` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="98990-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="98990-108">`false`の場合、には何も起こりません `target` 。</span><span class="sxs-lookup"><span data-stu-id="98990-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="98990-109">サフィックスは、 `A` 適用される操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="98990-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="98990-110">入力</span><span class="sxs-lookup"><span data-stu-id="98990-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="98990-111">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="98990-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="98990-112">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="98990-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="98990-113">bit: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="98990-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="98990-114">op が適用されるかどうかを制御するブール値。</span><span class="sxs-lookup"><span data-stu-id="98990-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="98990-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="98990-115">target : 'T</span></span>

<span data-ttu-id="98990-116">操作が適用される入力。</span><span class="sxs-lookup"><span data-stu-id="98990-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98990-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98990-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="98990-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="98990-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="98990-119">&</span><span class="sxs-lookup"><span data-stu-id="98990-119">'T</span></span>

<span data-ttu-id="98990-120">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="98990-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="example"></a><span data-ttu-id="98990-121">例</span><span class="sxs-lookup"><span data-stu-id="98990-121">Example</span></span>

<span data-ttu-id="98990-122">次の例では、値の配列として指定された古典的なビット文字列によって表される計算基準の状態に qubits のレジスタを準備し `Bool` ます。</span><span class="sxs-lookup"><span data-stu-id="98990-122">The following prepares a register of qubits into a computational basis state represented by a classical bit string given as an array of `Bool` values:</span></span>

```qsharp
let bitstring = [true, false, true];
using (register = Qubit(3)) {
    ApplyToEach(ApplyIf(X, _, _), Zipped(bitstring, register));
    // register should now be in the state |101⟩.
    ...
}
```

## <a name="see-also"></a><span data-ttu-id="98990-123">参照</span><span class="sxs-lookup"><span data-stu-id="98990-123">See Also</span></span>

- [<span data-ttu-id="98990-124">Microsoft. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="98990-124">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="98990-125">Microsoft. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="98990-125">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="98990-126">Microsoft. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="98990-126">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)