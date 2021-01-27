---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 34b60934b67c19b2d1d718d68b85a2f0fffeab5d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852015"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="e9acb-102">Trotter2ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="e9acb-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="e9acb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9acb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9acb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9acb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9acb-105">2番目の順序の Trotter – Suzuki インテグレーターの実装。</span><span class="sxs-lookup"><span data-stu-id="e9acb-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9acb-106">入力</span><span class="sxs-lookup"><span data-stu-id="e9acb-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="e9acb-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9acb-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9acb-108">時間ステップに分解される操作の数。</span><span class="sxs-lookup"><span data-stu-id="e9acb-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="e9acb-109">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="e9acb-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e9acb-110">分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="e9acb-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="e9acb-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9acb-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9acb-112">シミュレーションの各ステップのサイズに対する乗数。</span><span class="sxs-lookup"><span data-stu-id="e9acb-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="e9acb-113">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="e9acb-113">target : 'T</span></span>

<span data-ttu-id="e9acb-114">操作が動作するクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="e9acb-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9acb-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9acb-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e9acb-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e9acb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e9acb-117">&</span><span class="sxs-lookup"><span data-stu-id="e9acb-117">'T</span></span>

<span data-ttu-id="e9acb-118">各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。</span><span class="sxs-lookup"><span data-stu-id="e9acb-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="example"></a><span data-ttu-id="e9acb-119">例</span><span class="sxs-lookup"><span data-stu-id="e9acb-119">Example</span></span>

<span data-ttu-id="e9acb-120">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="e9acb-120">The following are equivalent:</span></span>

```qsharp
op(0, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(1, deltaT / 2.0, target);
op(0, deltaT / 2.0, target);
```

<span data-ttu-id="e9acb-121">and</span><span class="sxs-lookup"><span data-stu-id="e9acb-121">and</span></span>

```qsharp
Trotter2ImplCA((2, op), deltaT, target);
```