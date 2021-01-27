---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: bb93517a479ce344277bfe97d070e6630a8fccc0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840097"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="cd985-102">TrotterArbitraryImplCA 操作</span><span class="sxs-lookup"><span data-stu-id="cd985-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="cd985-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cd985-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cd985-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd985-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd985-105">Trotter – Suzuki インテグレーターの再帰的な実装。</span><span class="sxs-lookup"><span data-stu-id="cd985-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cd985-106">入力</span><span class="sxs-lookup"><span data-stu-id="cd985-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="cd985-107">順序: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd985-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd985-108">Trotter-Suzuki インテグレーターの順序。</span><span class="sxs-lookup"><span data-stu-id="cd985-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="cd985-109">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd985-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd985-110">時間ステップに分解される操作の数。</span><span class="sxs-lookup"><span data-stu-id="cd985-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="cd985-111">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="cd985-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="cd985-112">分解用のインデックス入力 (型 `Int` ) と時間入力 (型) `Double` およびクォンタムレジスタ (型) を受け入れる操作 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="cd985-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="cd985-113">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd985-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd985-114">シミュレーションの各ステップのサイズに対する乗数。</span><span class="sxs-lookup"><span data-stu-id="cd985-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="cd985-115">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="cd985-115">target : 'T</span></span>

<span data-ttu-id="cd985-116">操作が動作するクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="cd985-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd985-117">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd985-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cd985-118">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd985-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cd985-119">&</span><span class="sxs-lookup"><span data-stu-id="cd985-119">'T</span></span>

<span data-ttu-id="cd985-120">各時間ステップが動作する型。通常は、 `Qubit[]` またはのいずれか `Qubit` です。</span><span class="sxs-lookup"><span data-stu-id="cd985-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>