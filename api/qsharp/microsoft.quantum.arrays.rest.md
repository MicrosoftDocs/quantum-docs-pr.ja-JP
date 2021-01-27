---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845474"
---
# <a name="rest-function"></a><span data-ttu-id="4a580-102">Rest 関数</span><span class="sxs-lookup"><span data-stu-id="4a580-102">Rest function</span></span>

<span data-ttu-id="4a580-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4a580-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4a580-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a580-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a580-105">最初の配列要素が削除される点を除いて、入力配列と等しい配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="4a580-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4a580-106">入力</span><span class="sxs-lookup"><span data-stu-id="4a580-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="4a580-107">配列: ' t []</span><span class="sxs-lookup"><span data-stu-id="4a580-107">array : 'T[]</span></span>

<span data-ttu-id="4a580-108">最後の要素が出力配列を形成する配列。</span><span class="sxs-lookup"><span data-stu-id="4a580-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="4a580-109">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="4a580-109">Output : 'T[]</span></span>

<span data-ttu-id="4a580-110">要素を格納している配列 `array[1..Length(array) - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="4a580-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4a580-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a580-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a580-112">&</span><span class="sxs-lookup"><span data-stu-id="4a580-112">'T</span></span>

<span data-ttu-id="4a580-113">配列要素の型。</span><span class="sxs-lookup"><span data-stu-id="4a580-113">The type of the array elements.</span></span>