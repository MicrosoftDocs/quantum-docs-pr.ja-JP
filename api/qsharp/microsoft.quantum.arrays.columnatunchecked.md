---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: ColumnAtUnchecked 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719450"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="fc7da-102">ColumnAtUnchecked 関数</span><span class="sxs-lookup"><span data-stu-id="fc7da-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="fc7da-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fc7da-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fc7da-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fc7da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fc7da-105">この関数は、マトリックス図形を確認しません</span><span class="sxs-lookup"><span data-stu-id="fc7da-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="fc7da-106">説明</span><span class="sxs-lookup"><span data-stu-id="fc7da-106">Description</span></span>

<span data-ttu-id="fc7da-107">この関数は、入力行列が有効な四角形の形で既にチェックされている他の多次元関数で使用できます。</span><span class="sxs-lookup"><span data-stu-id="fc7da-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="fc7da-108">入力</span><span class="sxs-lookup"><span data-stu-id="fc7da-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="fc7da-109">列: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fc7da-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="fc7da-110">マトリックス: ' t [] []</span><span class="sxs-lookup"><span data-stu-id="fc7da-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="fc7da-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="fc7da-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fc7da-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc7da-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fc7da-113">&</span><span class="sxs-lookup"><span data-stu-id="fc7da-113">'T</span></span>

