---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Applywithinputトランス c 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d877fedbc0caa1a9ebc87d80cbce9ab54ca20d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850354"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="67b02-102">Applywithinputトランス c 操作</span><span class="sxs-lookup"><span data-stu-id="67b02-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="67b02-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67b02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67b02-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67b02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67b02-105">入力を受け入れる操作、その操作と互換性のある出力を返す関数、およびその関数への入力を指定すると、関数を使用して操作が適用され、操作によって予期される形式に入力が変換されます。</span><span class="sxs-lookup"><span data-stu-id="67b02-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="67b02-106">入力</span><span class="sxs-lookup"><span data-stu-id="67b02-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="67b02-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="67b02-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="67b02-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="67b02-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="67b02-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="67b02-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="67b02-110">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="67b02-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="67b02-111">入力: ' U</span><span class="sxs-lookup"><span data-stu-id="67b02-111">input : 'U</span></span>

<span data-ttu-id="67b02-112">関数への入力。</span><span class="sxs-lookup"><span data-stu-id="67b02-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67b02-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67b02-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="67b02-114">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="67b02-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67b02-115">&</span><span class="sxs-lookup"><span data-stu-id="67b02-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="67b02-116">' U</span><span class="sxs-lookup"><span data-stu-id="67b02-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="67b02-117">例</span><span class="sxs-lookup"><span data-stu-id="67b02-117">Example</span></span>

<span data-ttu-id="67b02-118">次の呼び出しでは、を使用し @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" て、型の入力に対する入力用に設計された操作を適用し @"Microsoft.Quantum.Arithmetic.BigEndian" @"Microsoft.Quantum.Arithmetic.LittleEndian" ます。</span><span class="sxs-lookup"><span data-stu-id="67b02-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="67b02-119">参照</span><span class="sxs-lookup"><span data-stu-id="67b02-119">See Also</span></span>

- [<span data-ttu-id="67b02-120">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="67b02-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="67b02-121">Microsoft.........。</span><span class="sxs-lookup"><span data-stu-id="67b02-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="67b02-122">Microsoft......。</span><span class="sxs-lookup"><span data-stu-id="67b02-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="67b02-123">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="67b02-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)