---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Istate 操作の実行中
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724002"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="3d985-102">Istate 操作の実行中</span><span class="sxs-lookup"><span data-stu-id="3d985-102">PrepareChoiState operation</span></span>

<span data-ttu-id="3d985-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="3d985-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="3d985-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3d985-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3d985-105">指定された操作について、指定された参照およびターゲットレジスタに Jamiłkowski 状態を準備します。</span><span class="sxs-lookup"><span data-stu-id="3d985-105">Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="3d985-106">入力</span><span class="sxs-lookup"><span data-stu-id="3d985-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="3d985-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d985-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3d985-108">操作 $ \ ラムダ $ Jamiłkowski state $J (-ラムダ)/2 ^ N $ を準備します。ここで $N $ は、が動作する qubits の数です `op` 。</span><span class="sxs-lookup"><span data-stu-id="3d985-108">Operation $\Lambda$ whose Choi–Jamiłkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="3d985-109">参照: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d985-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3d985-110">のアクションの参照として使用される、$ \ket{00\cdots 0} $ 状態から始まる qubits のレジスタ `op` 。</span><span class="sxs-lookup"><span data-stu-id="3d985-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3d985-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3d985-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3d985-112">が適用される $ \ket{00\cdots 0} $ 状態の最初の qubits のレジスタ `op` 。</span><span class="sxs-lookup"><span data-stu-id="3d985-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3d985-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3d985-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3d985-114">解説</span><span class="sxs-lookup"><span data-stu-id="3d985-114">Remarks</span></span>

<span data-ttu-id="3d985-115">Jamiłkowski state $J (-ラムダ) $ of クォンタムプロセスは、$ $ \begin{align} J (\ ラムダ) \mathrel{: =} として定義されています (& a)。 (& a) J (& a): =} (& \! \! )、\langle\boldone $ $ where $ |X\rangle \! \rangle $ は、列スタック規則内のマトリックス $X $ の *ベクター化* です。</span><span class="sxs-lookup"><span data-stu-id="3d985-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="3d985-116">この状態についての従来の説明を学習すると、任意の入力状態に作用する $-ラムダ $ の効果に関する完全な情報が得られ、 *量子プロセス tomography* の基盤が形成されます。</span><span class="sxs-lookup"><span data-stu-id="3d985-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography* .</span></span>

## <a name="see-also"></a><span data-ttu-id="3d985-117">参照</span><span class="sxs-lookup"><span data-stu-id="3d985-117">See Also</span></span>

- [<span data-ttu-id="3d985-118">Microsoft......... この Istatea</span><span class="sxs-lookup"><span data-stu-id="3d985-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="3d985-119">Microsoft...... 準備</span><span class="sxs-lookup"><span data-stu-id="3d985-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="3d985-120">PrepareChoiStateCA の準備</span><span class="sxs-lookup"><span data-stu-id="3d985-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)