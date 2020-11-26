---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: 各 Ca 操作の適用
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: dcfd4619a77413e71044e6a7d5fc19a9f22bbf94
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217749"
---
# <a name="applytoeachca-operation"></a><span data-ttu-id="476a4-102">各 Ca 操作の適用</span><span class="sxs-lookup"><span data-stu-id="476a4-102">ApplyToEachCA operation</span></span>

<span data-ttu-id="476a4-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="476a4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="476a4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="476a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="476a4-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="476a4-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="476a4-106">修飾子は、 `CA` single qubit 操作が制御可能で adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="476a4-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="476a4-107">入力</span><span class="sxs-lookup"><span data-stu-id="476a4-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a><span data-ttu-id="476a4-108">singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="476a4-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="476a4-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="476a4-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="476a4-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="476a4-110">register : 'T[]</span></span>

<span data-ttu-id="476a4-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="476a4-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="476a4-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="476a4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="476a4-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="476a4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="476a4-114">&</span><span class="sxs-lookup"><span data-stu-id="476a4-114">'T</span></span>

<span data-ttu-id="476a4-115">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="476a4-115">The target on which the operation acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="476a4-116">参照</span><span class="sxs-lookup"><span data-stu-id="476a4-116">See Also</span></span>

- [<span data-ttu-id="476a4-117">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="476a4-117">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)