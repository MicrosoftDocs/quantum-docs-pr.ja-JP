---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846217"
---
# <a name="constantarray-function"></a><span data-ttu-id="0854e-102">ConstantArray 関数</span><span class="sxs-lookup"><span data-stu-id="0854e-102">ConstantArray function</span></span>

<span data-ttu-id="0854e-103">名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0854e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0854e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0854e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0854e-105">指定された値と等しいすべての要素を使用して、指定された長さの配列を作成します。</span><span class="sxs-lookup"><span data-stu-id="0854e-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0854e-106">入力</span><span class="sxs-lookup"><span data-stu-id="0854e-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="0854e-107">長さ: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0854e-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0854e-108">新しい配列の長さ。</span><span class="sxs-lookup"><span data-stu-id="0854e-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="0854e-109">値: ' t '</span><span class="sxs-lookup"><span data-stu-id="0854e-109">value : 'T</span></span>

<span data-ttu-id="0854e-110">新しい配列の各要素の値。</span><span class="sxs-lookup"><span data-stu-id="0854e-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="0854e-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="0854e-111">Output : 'T[]</span></span>

<span data-ttu-id="0854e-112">`length`すべての要素がである、長さの新しい配列 `value` 。</span><span class="sxs-lookup"><span data-stu-id="0854e-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0854e-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0854e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0854e-114">&</span><span class="sxs-lookup"><span data-stu-id="0854e-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="0854e-115">例</span><span class="sxs-lookup"><span data-stu-id="0854e-115">Example</span></span>

<span data-ttu-id="0854e-116">次のコードでは、3つのブール値の配列が作成されます。それぞれが次の値に等しく `true` なります。</span><span class="sxs-lookup"><span data-stu-id="0854e-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```