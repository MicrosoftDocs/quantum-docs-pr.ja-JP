---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Applytoall Indexca 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: abb616498a8ff9c3348df81cf0ca1a1669561eec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208943"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="bac95-102">Applytoall Indexca 操作</span><span class="sxs-lookup"><span data-stu-id="bac95-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="bac95-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bac95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bac95-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bac95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bac95-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="bac95-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="bac95-106">修飾子は、 `CA` single qubit 操作が adjointable で制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="bac95-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="bac95-107">入力</span><span class="sxs-lookup"><span data-stu-id="bac95-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="bac95-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="bac95-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bac95-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="bac95-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="bac95-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="bac95-110">register : 'T[]</span></span>

<span data-ttu-id="bac95-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="bac95-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bac95-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bac95-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bac95-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bac95-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bac95-114">&</span><span class="sxs-lookup"><span data-stu-id="bac95-114">'T</span></span>

<span data-ttu-id="bac95-115">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="bac95-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="bac95-116">参照</span><span class="sxs-lookup"><span data-stu-id="bac95-116">See Also</span></span>

- [<span data-ttu-id="bac95-117">Microsoft...... のインデックス</span><span class="sxs-lookup"><span data-stu-id="bac95-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)