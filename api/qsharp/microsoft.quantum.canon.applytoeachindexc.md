---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: Applytoindexc 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 38fa23c70965118f1787f156bd617d6e967aba05
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217664"
---
# <a name="applytoeachindexc-operation"></a><span data-ttu-id="7a9ea-102">Applytoindexc 操作</span><span class="sxs-lookup"><span data-stu-id="7a9ea-102">ApplyToEachIndexC operation</span></span>

<span data-ttu-id="7a9ea-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a9ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a9ea-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a9ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a9ea-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="7a9ea-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="7a9ea-106">修飾子は、 `C` single qubit 操作が制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="7a9ea-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="7a9ea-107">入力</span><span class="sxs-lookup"><span data-stu-id="7a9ea-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-ctl"></a><span data-ttu-id="7a9ea-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="7a9ea-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="7a9ea-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="7a9ea-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="7a9ea-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="7a9ea-110">register : 'T[]</span></span>

<span data-ttu-id="7a9ea-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="7a9ea-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a9ea-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a9ea-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7a9ea-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7a9ea-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a9ea-114">&</span><span class="sxs-lookup"><span data-stu-id="7a9ea-114">'T</span></span>

<span data-ttu-id="7a9ea-115">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="7a9ea-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a9ea-116">参照</span><span class="sxs-lookup"><span data-stu-id="7a9ea-116">See Also</span></span>

- [<span data-ttu-id="7a9ea-117">Microsoft...... のインデックス</span><span class="sxs-lookup"><span data-stu-id="7a9ea-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)