---
uid: Microsoft.Quantum.Arrays.Padded
title: 埋め込み関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718982"
---
# <a name="padded-function"></a><span data-ttu-id="58b88-102">埋め込み関数</span><span class="sxs-lookup"><span data-stu-id="58b88-102">Padded function</span></span>

<span data-ttu-id="58b88-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="58b88-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="58b88-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58b88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58b88-105">指定された値で指定した長さまで、に埋め込まれた配列を返します。</span><span class="sxs-lookup"><span data-stu-id="58b88-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="58b88-106">入力</span><span class="sxs-lookup"><span data-stu-id="58b88-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="58b88-107">nElementsTotal: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="58b88-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="58b88-108">埋め込まれた配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="58b88-108">The length of the padded array.</span></span> <span data-ttu-id="58b88-109">正の場合、 `inputArray` はヘッドに埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="58b88-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="58b88-110">負の値の場合、 `inputArray` は末尾に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="58b88-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="58b88-111">defaultElement: ' t</span><span class="sxs-lookup"><span data-stu-id="58b88-111">defaultElement : 'T</span></span>

<span data-ttu-id="58b88-112">要素の埋め込みに使用する既定値。</span><span class="sxs-lookup"><span data-stu-id="58b88-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="58b88-113">inputArray: ' t []</span><span class="sxs-lookup"><span data-stu-id="58b88-113">inputArray : 'T[]</span></span>

<span data-ttu-id="58b88-114">値が出力配列の先頭にある配列。</span><span class="sxs-lookup"><span data-stu-id="58b88-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="58b88-115">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="58b88-115">Output : 'T[]</span></span>

<span data-ttu-id="58b88-116">`output` `inputArray` `defaultElement` がの長さになるまで、s に埋め込まれた配列。 `output``nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="58b88-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="58b88-117">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="58b88-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58b88-118">&</span><span class="sxs-lookup"><span data-stu-id="58b88-118">'T</span></span>

<span data-ttu-id="58b88-119">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="58b88-119">The type of the array elements.</span></span>