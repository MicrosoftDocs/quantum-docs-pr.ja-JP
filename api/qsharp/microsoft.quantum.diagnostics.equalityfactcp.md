---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712770"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="b2876-102">EqualityFactCP 関数</span><span class="sxs-lookup"><span data-stu-id="b2876-102">EqualityFactCP function</span></span>

<span data-ttu-id="b2876-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b2876-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b2876-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2876-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2876-105">複素数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="b2876-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b2876-106">入力</span><span class="sxs-lookup"><span data-stu-id="b2876-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="b2876-107">実績: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b2876-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b2876-108">チェックする値。</span><span class="sxs-lookup"><span data-stu-id="b2876-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="b2876-109">期待される結果: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="b2876-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="b2876-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="b2876-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b2876-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b2876-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b2876-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="b2876-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2876-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2876-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

