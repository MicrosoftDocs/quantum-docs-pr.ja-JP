---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 0fcfe553d7a0050a9ab35a43ac5fe2b1958514db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853362"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="b1c1e-102">EqualityFactC 関数</span><span class="sxs-lookup"><span data-stu-id="b1c1e-102">EqualityFactC function</span></span>

<span data-ttu-id="b1c1e-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b1c1e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b1c1e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1c1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1c1e-105">複素数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="b1c1e-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b1c1e-106">入力</span><span class="sxs-lookup"><span data-stu-id="b1c1e-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="b1c1e-107">実績: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b1c1e-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b1c1e-108">チェックする値。</span><span class="sxs-lookup"><span data-stu-id="b1c1e-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="b1c1e-109">必要: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="b1c1e-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="b1c1e-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="b1c1e-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b1c1e-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b1c1e-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b1c1e-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="b1c1e-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1c1e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1c1e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

