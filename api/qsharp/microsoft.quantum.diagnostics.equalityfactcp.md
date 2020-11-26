---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201854"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="fa4a0-102">EqualityFactCP 関数</span><span class="sxs-lookup"><span data-stu-id="fa4a0-102">EqualityFactCP function</span></span>

<span data-ttu-id="fa4a0-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fa4a0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fa4a0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa4a0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa4a0-105">複素数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="fa4a0-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fa4a0-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa4a0-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="fa4a0-107">実績: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="fa4a0-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="fa4a0-108">チェックする値。</span><span class="sxs-lookup"><span data-stu-id="fa4a0-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="fa4a0-109">期待される結果: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="fa4a0-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="fa4a0-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="fa4a0-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="fa4a0-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fa4a0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fa4a0-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="fa4a0-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fa4a0-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fa4a0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

