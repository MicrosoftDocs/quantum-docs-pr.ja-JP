---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: Applytoall c 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: b8b51e1c8d52c140c3ca1e5a54d0bd4cf4873046
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850846"
---
# <a name="applytoeachc-operation"></a><span data-ttu-id="eff69-102">Applytoall c 操作</span><span class="sxs-lookup"><span data-stu-id="eff69-102">ApplyToEachC operation</span></span>

<span data-ttu-id="eff69-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eff69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eff69-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eff69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eff69-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="eff69-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="eff69-106">修飾子は、 `C` single qubit 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="eff69-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="eff69-107">入力</span><span class="sxs-lookup"><span data-stu-id="eff69-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-ctl"></a><span data-ttu-id="eff69-108">singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="eff69-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="eff69-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="eff69-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="eff69-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="eff69-110">register : 'T[]</span></span>

<span data-ttu-id="eff69-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="eff69-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eff69-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eff69-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eff69-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="eff69-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eff69-114">&</span><span class="sxs-lookup"><span data-stu-id="eff69-114">'T</span></span>

<span data-ttu-id="eff69-115">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="eff69-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="eff69-116">例</span><span class="sxs-lookup"><span data-stu-id="eff69-116">Example</span></span>

<span data-ttu-id="eff69-117">3 qubit $ \ket{+} $ 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="eff69-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="eff69-118">参照</span><span class="sxs-lookup"><span data-stu-id="eff69-118">See Also</span></span>

- [<span data-ttu-id="eff69-119">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="eff69-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)