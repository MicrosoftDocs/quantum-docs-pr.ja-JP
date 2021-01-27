---
uid: Microsoft.Quantum.Canon.ApplyToEachA
title: 各操作の適用
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: da901db2bb3c70186bfe0c8812b5710198d1dff3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844618"
---
# <a name="applytoeacha-operation"></a><span data-ttu-id="11a9e-102">各操作の適用</span><span class="sxs-lookup"><span data-stu-id="11a9e-102">ApplyToEachA operation</span></span>

<span data-ttu-id="11a9e-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="11a9e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="11a9e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11a9e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11a9e-105">レジスタ内の各要素に単一の qubit 演算を適用します。</span><span class="sxs-lookup"><span data-stu-id="11a9e-105">Applies a single-qubit operation to each element in a register.</span></span>
<span data-ttu-id="11a9e-106">修飾子は、 `A` single qubit 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="11a9e-106">The modifier `A` indicates that the single-qubit operation is adjointable.</span></span>

```qsharp
operation ApplyToEachA<'T> (singleElementOperation : ('T => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="11a9e-107">入力</span><span class="sxs-lookup"><span data-stu-id="11a9e-107">Input</span></span>

### <a name="singleelementoperation--t--unit--is-adj"></a><span data-ttu-id="11a9e-108">singleElementOperation: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="11a9e-108">singleElementOperation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="11a9e-109">各 qubit に適用する操作。</span><span class="sxs-lookup"><span data-stu-id="11a9e-109">Operation to apply to each qubit.</span></span>


### <a name="register--t"></a><span data-ttu-id="11a9e-110">register: t []</span><span class="sxs-lookup"><span data-stu-id="11a9e-110">register : 'T[]</span></span>

<span data-ttu-id="11a9e-111">指定された操作を適用する qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="11a9e-111">Array of qubits on which to apply the given operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="11a9e-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11a9e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="11a9e-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="11a9e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="11a9e-114">&</span><span class="sxs-lookup"><span data-stu-id="11a9e-114">'T</span></span>

<span data-ttu-id="11a9e-115">操作が動作するターゲット。</span><span class="sxs-lookup"><span data-stu-id="11a9e-115">The target on which the operation acts.</span></span>

## <a name="example"></a><span data-ttu-id="11a9e-116">例</span><span class="sxs-lookup"><span data-stu-id="11a9e-116">Example</span></span>

<span data-ttu-id="11a9e-117">3 qubit $ \ket{+} $ 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="11a9e-117">Prepare a three-qubit $\ket{+}$ state:</span></span>

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a><span data-ttu-id="11a9e-118">参照</span><span class="sxs-lookup"><span data-stu-id="11a9e-118">See Also</span></span>

- [<span data-ttu-id="11a9e-119">Microsoft. ApplyToEach</span><span class="sxs-lookup"><span data-stu-id="11a9e-119">Microsoft.Quantum.Canon.ApplyToEach</span></span>](xref:Microsoft.Quantum.Canon.ApplyToEach)