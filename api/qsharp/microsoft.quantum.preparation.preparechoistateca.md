---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateCA
title: PrepareChoiStateCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateCA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.
ms.openlocfilehash: b9d2cdaea1ebc957719d92bf12901c54a55a56aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709443"
---
# <a name="preparechoistateca-operation"></a><span data-ttu-id="13d64-102">PrepareChoiStateCA 操作</span><span class="sxs-lookup"><span data-stu-id="13d64-102">PrepareChoiStateCA operation</span></span>

<span data-ttu-id="13d64-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="13d64-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="13d64-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13d64-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13d64-105">指定された参照およびターゲットレジスタに対し、制御されるバリアントと adjoint バリアントの両方を持つ特定の操作に対して、[Jamiłkowski] 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="13d64-105">Prepares the Choi–Jamiłkowski state for a given operation with both controlled and adjoint variants onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateCA (op : (Qubit[] => Unit is Adj + Ctl), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="13d64-106">入力</span><span class="sxs-lookup"><span data-stu-id="13d64-106">Input</span></span>

### <a name="op--qubit--unit-adj--ctl"></a><span data-ttu-id="13d64-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="13d64-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="13d64-108">参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="13d64-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="13d64-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="13d64-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="13d64-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13d64-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="13d64-111">参照</span><span class="sxs-lookup"><span data-stu-id="13d64-111">See Also</span></span>

- [<span data-ttu-id="13d64-112">Microsoft... 準備した Istate</span><span class="sxs-lookup"><span data-stu-id="13d64-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)