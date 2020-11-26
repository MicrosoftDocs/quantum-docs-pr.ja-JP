---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223886"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="7a9d5-102">AllEqualityFactI 関数</span><span class="sxs-lookup"><span data-stu-id="7a9d5-102">AllEqualityFactI function</span></span>

<span data-ttu-id="7a9d5-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7a9d5-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7a9d5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a9d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a9d5-105">整数値の2つの配列が等しいことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="7a9d5-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="7a9d5-106">入力</span><span class="sxs-lookup"><span data-stu-id="7a9d5-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="7a9d5-107">実際: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7a9d5-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7a9d5-108">対象のテストケースによって生成される配列。</span><span class="sxs-lookup"><span data-stu-id="7a9d5-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="7a9d5-109">[Int](xref:microsoft.quantum.lang-ref.int)[] が必要です</span><span class="sxs-lookup"><span data-stu-id="7a9d5-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7a9d5-110">対象のテストケースからの予期される配列。</span><span class="sxs-lookup"><span data-stu-id="7a9d5-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="7a9d5-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="7a9d5-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="7a9d5-112">配列が等しくない場合に出力されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="7a9d5-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7a9d5-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a9d5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

