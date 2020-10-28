---
uid: Microsoft.Quantum.Convert.Call
title: 操作の呼び出し
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713531"
---
# <a name="call-operation"></a><span data-ttu-id="87ee9-102">操作の呼び出し</span><span class="sxs-lookup"><span data-stu-id="87ee9-102">Call operation</span></span>

<span data-ttu-id="87ee9-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="87ee9-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="87ee9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87ee9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87ee9-105">指定された入力を使用して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="87ee9-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="87ee9-106">説明</span><span class="sxs-lookup"><span data-stu-id="87ee9-106">Description</span></span>

<span data-ttu-id="87ee9-107">関数とその関数への入力を指定すると、は関数を呼び出し、その出力を返します。</span><span class="sxs-lookup"><span data-stu-id="87ee9-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="87ee9-108">入力</span><span class="sxs-lookup"><span data-stu-id="87ee9-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="87ee9-109">fn: ' Input-> ' 出力</span><span class="sxs-lookup"><span data-stu-id="87ee9-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="87ee9-110">呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="87ee9-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="87ee9-111">入力: ' 入力</span><span class="sxs-lookup"><span data-stu-id="87ee9-111">input : 'Input</span></span>

<span data-ttu-id="87ee9-112">関数に渡される入力。</span><span class="sxs-lookup"><span data-stu-id="87ee9-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="87ee9-113">出力: ' 出力</span><span class="sxs-lookup"><span data-stu-id="87ee9-113">Output : 'Output</span></span>

<span data-ttu-id="87ee9-114">`fn` の呼び出しの結果。</span><span class="sxs-lookup"><span data-stu-id="87ee9-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="87ee9-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="87ee9-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="87ee9-116">' 入力</span><span class="sxs-lookup"><span data-stu-id="87ee9-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="87ee9-117">' 出力</span><span class="sxs-lookup"><span data-stu-id="87ee9-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="87ee9-118">解説</span><span class="sxs-lookup"><span data-stu-id="87ee9-118">Remarks</span></span>

<span data-ttu-id="87ee9-119">この操作は、主に、操作内の特定の場所で関数を呼び出す場合や、操作が必要な関数を呼び出す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="87ee9-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>