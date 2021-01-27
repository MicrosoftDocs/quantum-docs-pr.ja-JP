---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840136"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="b95fb-102">TransformedOperationA 関数</span><span class="sxs-lookup"><span data-stu-id="b95fb-102">TransformedOperationA function</span></span>

<span data-ttu-id="b95fb-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b95fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b95fb-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b95fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b95fb-105">関数と操作が指定された場合、指定された関数によって入力が変換される新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="b95fb-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="b95fb-106">入力</span><span class="sxs-lookup"><span data-stu-id="b95fb-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="b95fb-107">fn: ' U > ' ではありません</span><span class="sxs-lookup"><span data-stu-id="b95fb-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="b95fb-108">指定された入力を操作によって予期される形式に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="b95fb-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b95fb-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="b95fb-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b95fb-110">変換する操作。</span><span class="sxs-lookup"><span data-stu-id="b95fb-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="b95fb-111">出力: ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="b95fb-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b95fb-112">新しい操作 tbat は、 `fn` 入力を使用してを呼び出し、その結果の出力をに渡し `op` ます。</span><span class="sxs-lookup"><span data-stu-id="b95fb-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b95fb-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b95fb-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b95fb-114">&</span><span class="sxs-lookup"><span data-stu-id="b95fb-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="b95fb-115">' U</span><span class="sxs-lookup"><span data-stu-id="b95fb-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="b95fb-116">例</span><span class="sxs-lookup"><span data-stu-id="b95fb-116">Example</span></span>

<span data-ttu-id="b95fb-117">次の呼び出しでは、を使用して、入力用に設計された操作を、 @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" @"Microsoft.Quantum.Arithmetic.BigEndian" 型の入力を受け入れる操作に変換し @"Microsoft.Quantum.Arithmetic.LittleEndian" ます。</span><span class="sxs-lookup"><span data-stu-id="b95fb-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="b95fb-118">参照</span><span class="sxs-lookup"><span data-stu-id="b95fb-118">See Also</span></span>

- [<span data-ttu-id="b95fb-119">Microsoft. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="b95fb-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="b95fb-120">Microsoft. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="b95fb-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="b95fb-121">Microsoft. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="b95fb-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="b95fb-122">Microsoft...........。</span><span class="sxs-lookup"><span data-stu-id="b95fb-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="b95fb-123">Microsoft... Canon.</span><span class="sxs-lookup"><span data-stu-id="b95fb-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)