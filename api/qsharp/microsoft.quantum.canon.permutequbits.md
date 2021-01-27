---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 2fbbe0d99ad1383d77cb08ff6b03bcebd8a1971f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852323"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="5640c-102">PermuteQubits 操作</span><span class="sxs-lookup"><span data-stu-id="5640c-102">PermuteQubits operation</span></span>

<span data-ttu-id="5640c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5640c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5640c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5640c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5640c-105">スワップ操作を使用した Permutes qubits。</span><span class="sxs-lookup"><span data-stu-id="5640c-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5640c-106">入力</span><span class="sxs-lookup"><span data-stu-id="5640c-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="5640c-107">順序付け: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5640c-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5640c-108">Qubits の新しい順序について説明します。ここで、インデックス i の qubits は [i] の順に並べられます。</span><span class="sxs-lookup"><span data-stu-id="5640c-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="5640c-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5640c-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5640c-110">操作する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="5640c-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5640c-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5640c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="5640c-112">例</span><span class="sxs-lookup"><span data-stu-id="5640c-112">Example</span></span>

<span data-ttu-id="5640c-113">順序 = [2, 1, 0] と register $ \ket{\ alpha_0} \ket{\ alpha_1} \ket{\ alpha_2} $、PermuteQubits によってレジスタが $ \ket{\ alpha_2} \ket{\ alpha_1} \ket{\ alpha_0} $ に変更されます</span><span class="sxs-lookup"><span data-stu-id="5640c-113">Given ordering = [2, 1, 0] and register $\ket{\alpha_0} \ket{\alpha_1} \ket{\alpha_2}$, PermuteQubits changes the register into $\ket{\alpha_2} \ket{\alpha_1} \ket{\alpha_0}$</span></span>

```qsharp
// The following two lines are equivalent
PermuteQubits([2, 1, 0], register);
SWAP(register[0], register[2]);
```