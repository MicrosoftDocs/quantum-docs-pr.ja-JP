---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateA
title: Istatea 操作の実行
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateA
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation with an adjoint variant onto given reference and target registers.
ms.openlocfilehash: c679f9a02aa15f9a582257770b8dc57d798d1b29
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710983"
---
# <a name="preparechoistatea-operation"></a><span data-ttu-id="e6362-102">Istatea 操作の実行</span><span class="sxs-lookup"><span data-stu-id="e6362-102">PrepareChoiStateA operation</span></span>

<span data-ttu-id="e6362-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e6362-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e6362-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e6362-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e6362-105">指定された参照およびターゲットレジスタに adjoint バリアントを使用して、指定された操作に対して Jamiłkowski 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="e6362-105">Prepares the Choi–Jamiłkowski state for a given operation with an adjoint variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateA (op : (Qubit[] => Unit is Adj), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e6362-106">入力</span><span class="sxs-lookup"><span data-stu-id="e6362-106">Input</span></span>

### <a name="op--qubit--unit-adj"></a><span data-ttu-id="e6362-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞</span><span class="sxs-lookup"><span data-stu-id="e6362-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="e6362-108">参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6362-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="e6362-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e6362-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="e6362-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e6362-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e6362-111">参照</span><span class="sxs-lookup"><span data-stu-id="e6362-111">See Also</span></span>

- [<span data-ttu-id="e6362-112">Microsoft... 準備した Istate</span><span class="sxs-lookup"><span data-stu-id="e6362-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)