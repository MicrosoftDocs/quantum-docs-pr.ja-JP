---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712280"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="1f78e-102">KnillDistill 操作</span><span class="sxs-lookup"><span data-stu-id="1f78e-102">KnillDistill operation</span></span>

<span data-ttu-id="1f78e-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1f78e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1f78e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f78e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f78e-105">Knill マジック state 取り組みアルゴリズムを実装します。</span><span class="sxs-lookup"><span data-stu-id="1f78e-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="1f78e-106">説明</span><span class="sxs-lookup"><span data-stu-id="1f78e-106">Description</span></span>

<span data-ttu-id="1f78e-107">マジックステート $ $ \begin{align} \cos\frac{\pi} \ket + \ sin \frac{\pi} \ket \end{align} の15の概数コピーを指定すると {8} {0} {8} {1} 、$ $ により高品質のコピーが1つ生成されます。</span><span class="sxs-lookup"><span data-stu-id="1f78e-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="1f78e-108">入力</span><span class="sxs-lookup"><span data-stu-id="1f78e-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="1f78e-109">roughMagic: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="1f78e-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="1f78e-110">マジック状態の概数コピーを含む 15 qubits のレジスタ。</span><span class="sxs-lookup"><span data-stu-id="1f78e-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="1f78e-111">この取り組みプロシージャを適用する `roughMagic[0]` と、1つの高品質のコピーが含まれ、レジスタの残りの部分は $ \ket{00\cdots 0} $ 状態にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="1f78e-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1f78e-112">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1f78e-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1f78e-113">の場合、 `true` プロシージャは成功し、高品質のコピーが受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="1f78e-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="1f78e-114">の場合、 `false` プロシージャは失敗し、レジスタの状態は未定義であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="1f78e-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="1f78e-115">解説</span><span class="sxs-lookup"><span data-stu-id="1f78e-115">Remarks</span></span>

<span data-ttu-id="1f78e-116">Knill のアルゴリズムに従います。</span><span class="sxs-lookup"><span data-stu-id="1f78e-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="1f78e-117">ただし、現在の実装は、使用される qubits が多すぎるため、最適な実装ではありません。</span><span class="sxs-lookup"><span data-stu-id="1f78e-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="1f78e-118">このルーチンでは、マジック状態が挿入されます。この場合、より優れたプロトコルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f78e-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="1f78e-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f78e-119">References</span></span>

- [<span data-ttu-id="1f78e-120">Knill</span><span class="sxs-lookup"><span data-stu-id="1f78e-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)