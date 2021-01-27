---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: Applytoindexa 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: fb278f217ac450ab48aa37b0035cd1bdd295d3e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850826"
---
# <a name="applytoeachindexa-operation"></a><span data-ttu-id="6290d-102">Applytoindexa 操作</span><span class="sxs-lookup"><span data-stu-id="6290d-102">ApplyToEachIndexA operation</span></span>

<span data-ttu-id="6290d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6290d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6290d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6290d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6290d-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="6290d-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="6290d-106">修飾子は、 `A` single qubit 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6290d-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6290d-107">入力</span><span class="sxs-lookup"><span data-stu-id="6290d-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj"></a><span data-ttu-id="6290d-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="6290d-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6290d-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="6290d-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="6290d-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="6290d-110">register : 'T[]</span></span>

<span data-ttu-id="6290d-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="6290d-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6290d-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6290d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6290d-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6290d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6290d-114">&</span><span class="sxs-lookup"><span data-stu-id="6290d-114">'T</span></span>

<span data-ttu-id="6290d-115">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="6290d-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="6290d-116">参照</span><span class="sxs-lookup"><span data-stu-id="6290d-116">See Also</span></span>

- [<span data-ttu-id="6290d-117">Microsoft...... のインデックス</span><span class="sxs-lookup"><span data-stu-id="6290d-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)