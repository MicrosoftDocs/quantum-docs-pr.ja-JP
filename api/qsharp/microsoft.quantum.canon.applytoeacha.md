---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: 各操作の適用
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: 9819e78760caf6180edc5c2ca5e402060e3029a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217800"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="2e671-102">各操作の適用</span><span class="sxs-lookup"><span data-stu-id="2e671-102">ApplyToEachA operation</span></span>

<span data-ttu-id="2e671-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e671-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e671-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e671-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e671-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="2e671-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="2e671-106">修飾子は、 `A` single qubit 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="2e671-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="2e671-107">入力</span><span class="sxs-lookup"><span data-stu-id="2e671-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="2e671-108">singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="2e671-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2e671-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="2e671-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="2e671-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="2e671-110">register : 'T[]</span></span>

<span data-ttu-id="2e671-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="2e671-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e671-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e671-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e671-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e671-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e671-114">&</span><span class="sxs-lookup"><span data-stu-id="2e671-114">'T</span></span>

<span data-ttu-id="2e671-115">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="2e671-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e671-116">参照</span><span class="sxs-lookup"><span data-stu-id="2e671-116">See Also</span></span>

- [<span data-ttu-id="2e671-117">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="2e671-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)