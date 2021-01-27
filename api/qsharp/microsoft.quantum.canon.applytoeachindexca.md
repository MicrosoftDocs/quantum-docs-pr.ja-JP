---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexCA
title: Applytoall Indexca 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexCA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.
ms.openlocfilehash: 5046edc54576420bd8919ca52947076aed17cbce
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850795"
---
# <a name="applytoeachindexca-operation"></a><span data-ttu-id="e9d27-102">Applytoall Indexca 操作</span><span class="sxs-lookup"><span data-stu-id="e9d27-102">ApplyToEachIndexCA operation</span></span>

<span data-ttu-id="e9d27-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9d27-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9d27-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9d27-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9d27-105">レジスタ内のインデックスが付けられた各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="e9d27-105">Applies a single-qubit operation to each indexed element in a register.</span></span>
<span data-ttu-id="e9d27-106">修飾子は、 `CA` single qubit 操作が adjointable で制御可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e9d27-106">The modifier `CA` indicates that the single-qubit operation is adjointable and controllable.</span></span>

```qsharp
operation ApplyToEachIndexCA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9d27-107">入力</span><span class="sxs-lookup"><span data-stu-id="e9d27-107">Input</span></span>

### <a name="singleelementoperation--intt--unit--is-adj--ctl"></a><span data-ttu-id="e9d27-108">singleElementOperation: ([Int](xref:microsoft.quantum.lang-ref.int), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="e9d27-108">singleElementOperation : ([Int](xref:microsoft.quantum.lang-ref.int),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e9d27-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="e9d27-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="e9d27-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="e9d27-110">register : 'T[]</span></span>

<span data-ttu-id="e9d27-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="e9d27-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9d27-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9d27-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e9d27-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9d27-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e9d27-114">&</span><span class="sxs-lookup"><span data-stu-id="e9d27-114">'T</span></span>

<span data-ttu-id="e9d27-115">各操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="e9d27-115">The target on which each of the operations acts.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9d27-116">参照</span><span class="sxs-lookup"><span data-stu-id="e9d27-116">See Also</span></span>

- [<span data-ttu-id="e9d27-117">Microsoft...... のインデックス</span><span class="sxs-lookup"><span data-stu-id="e9d27-117">Microsoft.Quantum.Canon.ApplyToEachIndex</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)