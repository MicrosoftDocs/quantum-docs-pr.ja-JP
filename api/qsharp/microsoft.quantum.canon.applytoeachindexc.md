---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Applytoindexc 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: c005f616d580438891fbcb9f3c727b8e961e138d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850822"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="6fb7c-102">Applytoindexc 操作</span><span class="sxs-lookup"><span data-stu-id="6fb7c-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="6fb7c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6fb7c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6fb7c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6fb7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6fb7c-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="6fb7c-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6fb7c-106">修飾子は、 `C` single qubit 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6fb7c-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="6fb7c-107">入力</span><span class="sxs-lookup"><span data-stu-id="6fb7c-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="6fb7c-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="6fb7c-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6fb7c-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="6fb7c-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6fb7c-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="6fb7c-110">register : 'T[]</span></span>

<span data-ttu-id="6fb7c-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="6fb7c-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6fb7c-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6fb7c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6fb7c-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fb7c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6fb7c-114">&</span><span class="sxs-lookup"><span data-stu-id="6fb7c-114">'T</span></span>

<span data-ttu-id="6fb7c-115">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="6fb7c-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fb7c-116">参照</span><span class="sxs-lookup"><span data-stu-id="6fb7c-116">See Also</span></span>

- [<span data-ttu-id="6fb7c-117">Microsoft...... のインデックス</span><span class="sxs-lookup"><span data-stu-id="6fb7c-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)