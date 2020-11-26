---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224379"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="e7767-102">FunctionAsOperation 関数</span><span class="sxs-lookup"><span data-stu-id="e7767-102">FunctionAsOperation function</span></span>

<span data-ttu-id="e7767-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e7767-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e7767-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7767-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7767-105">関数を操作に変換します。</span><span class="sxs-lookup"><span data-stu-id="e7767-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="e7767-106">説明</span><span class="sxs-lookup"><span data-stu-id="e7767-106">Description</span></span>

<span data-ttu-id="e7767-107">関数を指定した場合、その関数を呼び出す操作を返します。それ以外は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="e7767-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="e7767-108">入力</span><span class="sxs-lookup"><span data-stu-id="e7767-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="e7767-109">fn: ' Input-> ' 出力</span><span class="sxs-lookup"><span data-stu-id="e7767-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="e7767-110">操作に変換される関数。</span><span class="sxs-lookup"><span data-stu-id="e7767-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="e7767-111">出力: ' Input => ' 出力</span><span class="sxs-lookup"><span data-stu-id="e7767-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="e7767-112">`op` `op(input)` すべてのと同一の操作 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="e7767-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e7767-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e7767-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="e7767-114">' 入力</span><span class="sxs-lookup"><span data-stu-id="e7767-114">'Input</span></span>

<span data-ttu-id="e7767-115">変換する関数の入力型。</span><span class="sxs-lookup"><span data-stu-id="e7767-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="e7767-116">' 出力</span><span class="sxs-lookup"><span data-stu-id="e7767-116">'Output</span></span>

<span data-ttu-id="e7767-117">変換する関数の出力の種類。</span><span class="sxs-lookup"><span data-stu-id="e7767-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7767-118">解説</span><span class="sxs-lookup"><span data-stu-id="e7767-118">Remarks</span></span>

<span data-ttu-id="e7767-119">これは主に、操作を入力として受け取る関数または操作に関数を渡す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e7767-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>