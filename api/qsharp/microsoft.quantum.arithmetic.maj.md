---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846548"
---
# <a name="maj-operation"></a><span data-ttu-id="65331-102">MAJ 操作</span><span class="sxs-lookup"><span data-stu-id="65331-102">MAJ operation</span></span>

<span data-ttu-id="65331-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="65331-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="65331-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65331-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65331-105">これにより、インプレースマジョリティ操作が3つの qubits に適用されます。</span><span class="sxs-lookup"><span data-stu-id="65331-105">This applies the in-place majority operation to 3 qubits.</span></span>

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="65331-106">説明</span><span class="sxs-lookup"><span data-stu-id="65331-106">Description</span></span>

<span data-ttu-id="65331-107">ターゲットの qubit を $ \ket{z} $ として、入力 qubit の入力状態を $ \ket{x} $ および $ \ket{y} $ として示す場合、この操作では次の変換が実行されます: $ \ket{xyz} \rightarrow \ket{x、oplus z} \ket{y/oplus z} \ket{\operatorname{MAJ} (x, y, z)} $。</span><span class="sxs-lookup"><span data-stu-id="65331-107">If we denote the state of the target qubit as $\ket{z}$, and input states of the input qubits as $\ket{x}$ and $\ket{y}$, then this operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="65331-108">入力</span><span class="sxs-lookup"><span data-stu-id="65331-108">Input</span></span>

### <a name="input0--qubit"></a><span data-ttu-id="65331-109">input0: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65331-109">input0 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65331-110">最初の入力 qubit。</span><span class="sxs-lookup"><span data-stu-id="65331-110">The first input qubit.</span></span>


### <a name="input1--qubit"></a><span data-ttu-id="65331-111">input1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65331-111">input1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65331-112">2番目の入力 qubit。</span><span class="sxs-lookup"><span data-stu-id="65331-112">The second input qubit.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="65331-113">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65331-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65331-114">マジョリティ関数が適用される qubit。</span><span class="sxs-lookup"><span data-stu-id="65331-114">A qubit onto which the majority function will be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65331-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65331-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

