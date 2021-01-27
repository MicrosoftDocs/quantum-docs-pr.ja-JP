---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: f18536a056935220feedc4ea50531c5def61d650
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850507"
---
# <a name="applytorest-operation"></a><span data-ttu-id="4b083-102">ApplyToRest 操作</span><span class="sxs-lookup"><span data-stu-id="4b083-102">ApplyToRest operation</span></span>

<span data-ttu-id="4b083-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b083-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b083-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b083-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b083-105">配列の最初の要素以外のすべてに操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="4b083-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4b083-106">説明</span><span class="sxs-lookup"><span data-stu-id="4b083-106">Description</span></span>

<span data-ttu-id="4b083-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Rest(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="4b083-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4b083-108">入力</span><span class="sxs-lookup"><span data-stu-id="4b083-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4b083-109">op: ' t [] => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b083-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4b083-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="4b083-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4b083-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="4b083-111">targets : 'T[]</span></span>

<span data-ttu-id="4b083-112">ターゲットの配列。すべてのものが最初に適用され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="4b083-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b083-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b083-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4b083-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b083-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b083-115">&</span><span class="sxs-lookup"><span data-stu-id="4b083-115">'T</span></span>

<span data-ttu-id="4b083-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="4b083-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="4b083-117">例</span><span class="sxs-lookup"><span data-stu-id="4b083-117">Example</span></span>

<span data-ttu-id="4b083-118">次の Q # スニペットは同等です。</span><span class="sxs-lookup"><span data-stu-id="4b083-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToRest(ApplyCNOTChain, register);
ApplyCNOTChain(Rest(register));
```

## <a name="see-also"></a><span data-ttu-id="4b083-119">参照</span><span class="sxs-lookup"><span data-stu-id="4b083-119">See Also</span></span>

- [<span data-ttu-id="4b083-120">Microsoft. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="4b083-120">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="4b083-121">Microsoft....。</span><span class="sxs-lookup"><span data-stu-id="4b083-121">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="4b083-122">Microsoft. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="4b083-122">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)