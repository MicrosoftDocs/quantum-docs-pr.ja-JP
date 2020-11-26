---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateA
title: Istatea 操作の実行
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with an adjoint variant onto given reference and target registers.
ms.openlocfilehash: 59d47a549a6e2a208906b79504ea93bd9ebaabd7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230125"
---
# <a name="preparechoistatea-operation"></a><span data-ttu-id="bde59-102">Istatea 操作の実行</span><span class="sxs-lookup"><span data-stu-id="bde59-102">PrepareChoiStateA operation</span></span>

<span data-ttu-id="bde59-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="bde59-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="bde59-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bde59-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bde59-105">指定された参照およびターゲットレジスタに adjoint バリアントを使用して、指定された操作に対して Jamiołkowski 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="bde59-105">Prepares the Choi–Jamiołkowski state for a given operation with an adjoint variant onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiStateA (op : (Qubit[] => Unit is Adj), reference : Qubit[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bde59-106">入力</span><span class="sxs-lookup"><span data-stu-id="bde59-106">Input</span></span>

### <a name="op--qubit--unit--is-adj"></a><span data-ttu-id="bde59-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="bde59-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="reference--qubit"></a><span data-ttu-id="bde59-108">参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bde59-108">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="bde59-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bde59-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="bde59-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bde59-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="bde59-111">参照</span><span class="sxs-lookup"><span data-stu-id="bde59-111">See Also</span></span>

- [<span data-ttu-id="bde59-112">Microsoft... 準備した Istate</span><span class="sxs-lookup"><span data-stu-id="bde59-112">Microsoft.Quantum.Preparation.PrepareChoiState</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiState)