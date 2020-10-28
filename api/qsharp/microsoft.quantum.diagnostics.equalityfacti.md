---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: 34bb38a9447f71372ec0b234731f31a5818d3af1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712761"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="1c7bc-102">EqualityFactI 関数</span><span class="sxs-lookup"><span data-stu-id="1c7bc-102">EqualityFactI function</span></span>

<span data-ttu-id="1c7bc-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1c7bc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1c7bc-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1c7bc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1c7bc-105">クラシック Int 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="1c7bc-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1c7bc-106">入力</span><span class="sxs-lookup"><span data-stu-id="1c7bc-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="1c7bc-107">実際の: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c7bc-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c7bc-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="1c7bc-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="1c7bc-109">予期される値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1c7bc-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1c7bc-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="1c7bc-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1c7bc-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1c7bc-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1c7bc-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="1c7bc-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1c7bc-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1c7bc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

