---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713512"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="a4a71-102">FunctionAsOperation 関数</span><span class="sxs-lookup"><span data-stu-id="a4a71-102">FunctionAsOperation function</span></span>

<span data-ttu-id="a4a71-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="a4a71-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="a4a71-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a4a71-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a4a71-105">関数を操作に変換します。</span><span class="sxs-lookup"><span data-stu-id="a4a71-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="a4a71-106">説明</span><span class="sxs-lookup"><span data-stu-id="a4a71-106">Description</span></span>

<span data-ttu-id="a4a71-107">関数を指定した場合、その関数を呼び出す操作を返します。それ以外は何も行いません。</span><span class="sxs-lookup"><span data-stu-id="a4a71-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="a4a71-108">入力</span><span class="sxs-lookup"><span data-stu-id="a4a71-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="a4a71-109">fn: ' Input-> ' 出力</span><span class="sxs-lookup"><span data-stu-id="a4a71-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="a4a71-110">操作に変換される関数。</span><span class="sxs-lookup"><span data-stu-id="a4a71-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="a4a71-111">出力: ' Input => ' 出力</span><span class="sxs-lookup"><span data-stu-id="a4a71-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="a4a71-112">`op` `op(input)` すべてのと同一の操作 `fn(input)` `input` 。</span><span class="sxs-lookup"><span data-stu-id="a4a71-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a4a71-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4a71-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="a4a71-114">' 入力</span><span class="sxs-lookup"><span data-stu-id="a4a71-114">'Input</span></span>

<span data-ttu-id="a4a71-115">変換する関数の入力型。</span><span class="sxs-lookup"><span data-stu-id="a4a71-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="a4a71-116">' 出力</span><span class="sxs-lookup"><span data-stu-id="a4a71-116">'Output</span></span>

<span data-ttu-id="a4a71-117">変換する関数の出力の種類。</span><span class="sxs-lookup"><span data-stu-id="a4a71-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4a71-118">解説</span><span class="sxs-lookup"><span data-stu-id="a4a71-118">Remarks</span></span>

<span data-ttu-id="a4a71-119">これは主に、操作を入力として受け取る関数または操作に関数を渡す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="a4a71-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>