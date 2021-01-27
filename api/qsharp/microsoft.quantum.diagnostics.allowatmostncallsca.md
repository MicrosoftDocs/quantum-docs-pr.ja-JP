---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853536"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="0d3be-102">AllowAtMostNCallsCA 操作</span><span class="sxs-lookup"><span data-stu-id="0d3be-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="0d3be-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0d3be-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0d3be-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0d3be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0d3be-105">この操作とその adjoint の呼び出しの間に、指定された操作が特定の回数だけ呼び出されることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="0d3be-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="0d3be-106">入力</span><span class="sxs-lookup"><span data-stu-id="0d3be-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="0d3be-107">nTimes: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d3be-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0d3be-108">を `op` 呼び出すことができる最大回数。</span><span class="sxs-lookup"><span data-stu-id="0d3be-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="0d3be-109">op: ' TInput => ' TOutput is 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0d3be-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="0d3be-110">呼び出しが制限される操作。</span><span class="sxs-lookup"><span data-stu-id="0d3be-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="0d3be-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="0d3be-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="0d3be-112">失敗したときに表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0d3be-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0d3be-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0d3be-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0d3be-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d3be-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="0d3be-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="0d3be-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="0d3be-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="0d3be-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="0d3be-117">例</span><span class="sxs-lookup"><span data-stu-id="0d3be-117">Example</span></span>

<span data-ttu-id="0d3be-118">次のスニペットは、この診断をサポートするコンピューターで実行すると失敗します。</span><span class="sxs-lookup"><span data-stu-id="0d3be-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="0d3be-119">解説</span><span class="sxs-lookup"><span data-stu-id="0d3be-119">Remarks</span></span>

<span data-ttu-id="0d3be-120">この操作は、サポートされていない非 op ターゲットに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="0d3be-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>