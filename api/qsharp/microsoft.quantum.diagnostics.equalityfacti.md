---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 27c0642f6d89aaa715526092813240e11b9ab530
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201837"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="8e8d1-102">EqualityFactI 関数</span><span class="sxs-lookup"><span data-stu-id="8e8d1-102">EqualityFactI function</span></span>

<span data-ttu-id="8e8d1-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="8e8d1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="8e8d1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8e8d1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8e8d1-105">クラシック Int 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="8e8d1-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="8e8d1-106">入力</span><span class="sxs-lookup"><span data-stu-id="8e8d1-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="8e8d1-107">実際の: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e8d1-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e8d1-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="8e8d1-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="8e8d1-109">予期される値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8e8d1-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8e8d1-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="8e8d1-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="8e8d1-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8e8d1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8e8d1-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="8e8d1-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8e8d1-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8e8d1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

