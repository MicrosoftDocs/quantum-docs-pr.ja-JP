---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715309"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="4244d-102">Trotter2ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="4244d-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="4244d-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4244d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4244d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4244d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4244d-105">2番目の順序の Trotter – Suzuki インテグレーターの実装。</span><span class="sxs-lookup"><span data-stu-id="4244d-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="4244d-106">入力</span><span class="sxs-lookup"><span data-stu-id="4244d-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="4244d-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4244d-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4244d-108">時間ステップに分解される操作の数。</span><span class="sxs-lookup"><span data-stu-id="4244d-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="4244d-109">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="4244d-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4244d-110">分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="4244d-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="4244d-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4244d-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4244d-112">シミュレーションの各ステップのサイズに対する乗数。</span><span class="sxs-lookup"><span data-stu-id="4244d-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="4244d-113">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="4244d-113">target : 'T</span></span>

<span data-ttu-id="4244d-114">操作が動作するクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="4244d-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4244d-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4244d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4244d-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4244d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4244d-117">&</span><span class="sxs-lookup"><span data-stu-id="4244d-117">'T</span></span>

<span data-ttu-id="4244d-118">各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。</span><span class="sxs-lookup"><span data-stu-id="4244d-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>