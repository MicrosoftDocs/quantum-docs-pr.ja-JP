---
uid: Microsoft.Quantum.Arrays.Padded
title: 埋め込み関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845563"
---
# <a name="padded-function"></a><span data-ttu-id="e42f0-102">埋め込み関数</span><span class="sxs-lookup"><span data-stu-id="e42f0-102">Padded function</span></span>

<span data-ttu-id="e42f0-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e42f0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e42f0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e42f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e42f0-105">指定された値で指定した長さまで、に埋め込まれた配列を返します。</span><span class="sxs-lookup"><span data-stu-id="e42f0-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e42f0-106">入力</span><span class="sxs-lookup"><span data-stu-id="e42f0-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="e42f0-107">nElementsTotal: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e42f0-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e42f0-108">埋め込まれた配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="e42f0-108">The length of the padded array.</span></span> <span data-ttu-id="e42f0-109">正の場合、 `inputArray` はヘッドに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="e42f0-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="e42f0-110">負の値の場合、 `inputArray` は末尾に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="e42f0-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="e42f0-111">defaultElement: ' t</span><span class="sxs-lookup"><span data-stu-id="e42f0-111">defaultElement : 'T</span></span>

<span data-ttu-id="e42f0-112">要素の埋め込みに使用する既定値。</span><span class="sxs-lookup"><span data-stu-id="e42f0-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="e42f0-113">inputArray: ' t []</span><span class="sxs-lookup"><span data-stu-id="e42f0-113">inputArray : 'T[]</span></span>

<span data-ttu-id="e42f0-114">値が出力配列の先頭にある配列。</span><span class="sxs-lookup"><span data-stu-id="e42f0-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e42f0-115">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="e42f0-115">Output : 'T[]</span></span>

<span data-ttu-id="e42f0-116">`output` `inputArray` `defaultElement` がの長さになるまで、s に埋め込まれた配列。 `output``nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="e42f0-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e42f0-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e42f0-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e42f0-118">&</span><span class="sxs-lookup"><span data-stu-id="e42f0-118">'T</span></span>

<span data-ttu-id="e42f0-119">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="e42f0-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="e42f0-120">例</span><span class="sxs-lookup"><span data-stu-id="e42f0-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```