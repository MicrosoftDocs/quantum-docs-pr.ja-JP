---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201905"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="1cb93-102">EqualityFactC 関数</span><span class="sxs-lookup"><span data-stu-id="1cb93-102">EqualityFactC function</span></span>

<span data-ttu-id="1cb93-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1cb93-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1cb93-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cb93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cb93-105">複素数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="1cb93-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1cb93-106">入力</span><span class="sxs-lookup"><span data-stu-id="1cb93-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="1cb93-107">実績: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1cb93-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1cb93-108">チェックする値。</span><span class="sxs-lookup"><span data-stu-id="1cb93-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="1cb93-109">必要: [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="1cb93-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="1cb93-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="1cb93-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="1cb93-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1cb93-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1cb93-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="1cb93-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1cb93-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cb93-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

