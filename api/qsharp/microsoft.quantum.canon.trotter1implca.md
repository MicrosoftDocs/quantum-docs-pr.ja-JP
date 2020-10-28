---
uid: Microsoft.Quantum.Canon.Trotter1ImplCA
title: Trotter1ImplCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter1ImplCA
qsharp.summary: Implementation of the first-order Trotter–Suzuki integrator.
ms.openlocfilehash: 250b80729530a5d3054e037d9dd653904a57f6d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715304"
---
# <a name="trotter1implca-operation"></a><span data-ttu-id="5d6da-102">Trotter1ImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="5d6da-102">Trotter1ImplCA operation</span></span>

<span data-ttu-id="5d6da-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5d6da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5d6da-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5d6da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5d6da-105">最初の順序の Trotter – Suzuki インテグレーターの実装。</span><span class="sxs-lookup"><span data-stu-id="5d6da-105">Implementation of the first-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter1ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="5d6da-106">入力</span><span class="sxs-lookup"><span data-stu-id="5d6da-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="5d6da-107">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5d6da-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5d6da-108">時間ステップに分解される操作の数。</span><span class="sxs-lookup"><span data-stu-id="5d6da-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="5d6da-109">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="5d6da-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="5d6da-110">分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="5d6da-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="5d6da-111">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d6da-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d6da-112">シミュレーションの各ステップのサイズに対する乗数。</span><span class="sxs-lookup"><span data-stu-id="5d6da-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="5d6da-113">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="5d6da-113">target : 'T</span></span>

<span data-ttu-id="5d6da-114">操作が動作するクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="5d6da-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d6da-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d6da-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5d6da-116">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d6da-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d6da-117">&</span><span class="sxs-lookup"><span data-stu-id="5d6da-117">'T</span></span>

<span data-ttu-id="5d6da-118">各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。</span><span class="sxs-lookup"><span data-stu-id="5d6da-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>