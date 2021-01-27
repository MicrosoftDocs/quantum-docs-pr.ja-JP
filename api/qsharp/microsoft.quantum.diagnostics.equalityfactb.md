---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: cb1d4c471c528d2d3c08c92619fafd532a88c8f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829216"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="49ea0-102">EqualityFactB 関数</span><span class="sxs-lookup"><span data-stu-id="49ea0-102">EqualityFactB function</span></span>

<span data-ttu-id="49ea0-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="49ea0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="49ea0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49ea0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49ea0-105">クラシック Bool 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="49ea0-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="49ea0-106">入力</span><span class="sxs-lookup"><span data-stu-id="49ea0-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="49ea0-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="49ea0-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="49ea0-108">チェックする変数。</span><span class="sxs-lookup"><span data-stu-id="49ea0-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="49ea0-109">必要: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="49ea0-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="49ea0-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="49ea0-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="49ea0-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="49ea0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="49ea0-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="49ea0-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="49ea0-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="49ea0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

