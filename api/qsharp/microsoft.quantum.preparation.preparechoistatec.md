---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateC
title: Istatec 操作の実行
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateC
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with a controlled variant onto given reference and target registers.
ms.openlocfilehash: b23b22fa4bf21ca48076ccda0db62b313f887aa9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724898"
---
# <a name="preparechoistatec-operation"></a><span data-ttu-id="60396-102">Istatec 操作の実行</span><span class="sxs-lookup"><span data-stu-id="60396-102">PrepareChoiStateC operation</span></span>

<span data-ttu-id="60396-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="60396-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="60396-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="60396-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="60396-105">指定された参照およびターゲットレジスタに制御されるバリアントを持つ特定の操作に対して、[Jamiłkowski] 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="60396-105">Prepares the Choi–Jamiłkowski state for a given operation with a controlled variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateC (op : (Qubit[] => Unit is Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="60396-106">入力</span><span class="sxs-lookup"><span data-stu-id="60396-106">Input</span></span>

### <a name="op--qubit--unit-ctl"></a><span data-ttu-id="60396-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="60396-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="60396-108">参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="60396-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="60396-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="60396-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="60396-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60396-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="60396-111">参照</span><span class="sxs-lookup"><span data-stu-id="60396-111">See Also</span></span>

- [<span data-ttu-id="60396-112">Microsoft... 準備した Istate</span><span class="sxs-lookup"><span data-stu-id="60396-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)