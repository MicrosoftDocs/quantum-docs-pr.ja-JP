---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 79dcf65956ba9436fb6fdd452f22f35d4852d6f8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213703"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="56df2-102">AllEqualityFactB 関数</span><span class="sxs-lookup"><span data-stu-id="56df2-102">AllEqualityFactB function</span></span>

<span data-ttu-id="56df2-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="56df2-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="56df2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56df2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56df2-105">ブール値の2つの配列が等しいことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="56df2-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="56df2-106">入力</span><span class="sxs-lookup"><span data-stu-id="56df2-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="56df2-107">実際: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="56df2-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="56df2-108">対象のテストケースによって生成される配列。</span><span class="sxs-lookup"><span data-stu-id="56df2-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="56df2-109">必要: [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="56df2-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="56df2-110">対象のテストケースからの予期される配列。</span><span class="sxs-lookup"><span data-stu-id="56df2-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="56df2-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="56df2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="56df2-112">配列が等しくない場合に出力されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="56df2-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56df2-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56df2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

