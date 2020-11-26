---
uid: Microsoft.Quantum.Convert.Call
title: 操作の呼び出し
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214213"
---
# <a name="call-operation"></a><span data-ttu-id="640a3-102">操作の呼び出し</span><span class="sxs-lookup"><span data-stu-id="640a3-102">Call operation</span></span>

<span data-ttu-id="640a3-103">名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="640a3-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="640a3-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="640a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="640a3-105">指定された入力を使用して関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="640a3-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="640a3-106">説明</span><span class="sxs-lookup"><span data-stu-id="640a3-106">Description</span></span>

<span data-ttu-id="640a3-107">関数とその関数への入力を指定すると、は関数を呼び出し、その出力を返します。</span><span class="sxs-lookup"><span data-stu-id="640a3-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="640a3-108">入力</span><span class="sxs-lookup"><span data-stu-id="640a3-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="640a3-109">fn: ' Input-> ' 出力</span><span class="sxs-lookup"><span data-stu-id="640a3-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="640a3-110">呼び出される関数。</span><span class="sxs-lookup"><span data-stu-id="640a3-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="640a3-111">入力: ' 入力</span><span class="sxs-lookup"><span data-stu-id="640a3-111">input : 'Input</span></span>

<span data-ttu-id="640a3-112">関数に渡される入力。</span><span class="sxs-lookup"><span data-stu-id="640a3-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="640a3-113">出力: ' 出力</span><span class="sxs-lookup"><span data-stu-id="640a3-113">Output : 'Output</span></span>

<span data-ttu-id="640a3-114">`fn` の呼び出しの結果。</span><span class="sxs-lookup"><span data-stu-id="640a3-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="640a3-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="640a3-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="640a3-116">' 入力</span><span class="sxs-lookup"><span data-stu-id="640a3-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="640a3-117">' 出力</span><span class="sxs-lookup"><span data-stu-id="640a3-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="640a3-118">解説</span><span class="sxs-lookup"><span data-stu-id="640a3-118">Remarks</span></span>

<span data-ttu-id="640a3-119">この操作は、主に、操作内の特定の場所で関数を呼び出す場合や、操作が必要な関数を呼び出す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="640a3-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>