---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 1c094d09ac8bdd71a59ef57d8715a6f90f18efc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715290"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="d251f-102">TrotterArbitraryImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="d251f-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="d251f-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d251f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d251f-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d251f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d251f-105">Trotter – Suzuki インテグレーターの再帰的な実装。</span><span class="sxs-lookup"><span data-stu-id="d251f-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="d251f-106">入力</span><span class="sxs-lookup"><span data-stu-id="d251f-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="d251f-107">順序: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d251f-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d251f-108">Trotter-Suzuki インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="d251f-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="d251f-109">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d251f-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d251f-110">時間ステップに分解される操作の数。</span><span class="sxs-lookup"><span data-stu-id="d251f-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="d251f-111">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d251f-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d251f-112">分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="d251f-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="d251f-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="d251f-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="d251f-114">シミュレーションの各ステップのサイズに対する乗数。</span><span class="sxs-lookup"><span data-stu-id="d251f-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="d251f-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="d251f-115">target : 'T</span></span>

<span data-ttu-id="d251f-116">操作が動作するクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="d251f-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d251f-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d251f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d251f-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="d251f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d251f-119">&</span><span class="sxs-lookup"><span data-stu-id="d251f-119">'T</span></span>

<span data-ttu-id="d251f-120">各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。</span><span class="sxs-lookup"><span data-stu-id="d251f-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>