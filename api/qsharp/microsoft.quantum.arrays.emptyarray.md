---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846172"
---
# <a name="emptyarray-function"></a><span data-ttu-id="78ec1-102">EmptyArray 関数</span><span class="sxs-lookup"><span data-stu-id="78ec1-102">EmptyArray function</span></span>

<span data-ttu-id="78ec1-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="78ec1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="78ec1-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="78ec1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="78ec1-105">指定された型の空の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="78ec1-105">Returns the empty array of a given type.</span></span>

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a><span data-ttu-id="78ec1-106">出力: ' TElement []</span><span class="sxs-lookup"><span data-stu-id="78ec1-106">Output : 'TElement[]</span></span>

<span data-ttu-id="78ec1-107">空の配列。</span><span class="sxs-lookup"><span data-stu-id="78ec1-107">The empty array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="78ec1-108">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="78ec1-108">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="78ec1-109">' TElement '</span><span class="sxs-lookup"><span data-stu-id="78ec1-109">'TElement</span></span>

<span data-ttu-id="78ec1-110">配列の要素の型。</span><span class="sxs-lookup"><span data-stu-id="78ec1-110">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="78ec1-111">例</span><span class="sxs-lookup"><span data-stu-id="78ec1-111">Example</span></span>

```qsharp
let empty = EmptyArray<Int>();
```