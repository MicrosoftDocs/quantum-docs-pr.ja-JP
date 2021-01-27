---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: 適用操作の適用
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 077e6dedee68b0bd05a668387b22f8bec87a4041
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850437"
---
# <a name="applytotail-operation"></a><span data-ttu-id="6b73c-102">適用操作の適用</span><span class="sxs-lookup"><span data-stu-id="6b73c-102">ApplyToTail operation</span></span>

<span data-ttu-id="6b73c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b73c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b73c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b73c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b73c-105">配列の最後の要素に操作を適用します。</span><span class="sxs-lookup"><span data-stu-id="6b73c-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="6b73c-106">説明</span><span class="sxs-lookup"><span data-stu-id="6b73c-106">Description</span></span>

<span data-ttu-id="6b73c-107">指定された操作 `op` とターゲットの配列が適用され `targets` `op(Tail(targets))` ます。</span><span class="sxs-lookup"><span data-stu-id="6b73c-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="6b73c-108">入力</span><span class="sxs-lookup"><span data-stu-id="6b73c-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="6b73c-109">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b73c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="6b73c-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="6b73c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="6b73c-111">ターゲット: ' t []</span><span class="sxs-lookup"><span data-stu-id="6b73c-111">targets : 'T[]</span></span>

<span data-ttu-id="6b73c-112">最後のが適用されるターゲットの配列 `op` 。</span><span class="sxs-lookup"><span data-stu-id="6b73c-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b73c-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b73c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b73c-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="6b73c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b73c-115">&</span><span class="sxs-lookup"><span data-stu-id="6b73c-115">'T</span></span>

<span data-ttu-id="6b73c-116">適用する操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="6b73c-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="6b73c-117">例</span><span class="sxs-lookup"><span data-stu-id="6b73c-117">Example</span></span>

<span data-ttu-id="6b73c-118">次の Q # スニペットは同等です。</span><span class="sxs-lookup"><span data-stu-id="6b73c-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToTail(H, register);
H(Tail(register));
```

## <a name="see-also"></a><span data-ttu-id="6b73c-119">参照</span><span class="sxs-lookup"><span data-stu-id="6b73c-119">See Also</span></span>

- [<span data-ttu-id="6b73c-120">Microsoft.... "</span><span class="sxs-lookup"><span data-stu-id="6b73c-120">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="6b73c-121">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="6b73c-121">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="6b73c-122">Microsoft... の証明機関</span><span class="sxs-lookup"><span data-stu-id="6b73c-122">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)