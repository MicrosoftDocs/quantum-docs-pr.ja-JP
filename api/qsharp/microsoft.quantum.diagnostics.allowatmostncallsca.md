---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202568"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="cd31c-102">AllowAtMostNCallsCA 操作</span><span class="sxs-lookup"><span data-stu-id="cd31c-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="cd31c-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cd31c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cd31c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd31c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd31c-105">この操作とその adjoint の呼び出しの間に、指定された操作が特定の回数だけ呼び出されることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="cd31c-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="cd31c-106">入力</span><span class="sxs-lookup"><span data-stu-id="cd31c-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="cd31c-107">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cd31c-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cd31c-108">を `op` 呼び出すことができる最大回数。</span><span class="sxs-lookup"><span data-stu-id="cd31c-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="cd31c-109">op: ' TInput => ' TOutput is 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="cd31c-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="cd31c-110">呼び出しが制限される操作。</span><span class="sxs-lookup"><span data-stu-id="cd31c-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="cd31c-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cd31c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cd31c-112">失敗したときに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="cd31c-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd31c-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd31c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cd31c-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="cd31c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="cd31c-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="cd31c-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="cd31c-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="cd31c-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="cd31c-117">解説</span><span class="sxs-lookup"><span data-stu-id="cd31c-117">Remarks</span></span>

<span data-ttu-id="cd31c-118">この操作は、サポートされていない非 op ターゲットに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="cd31c-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>