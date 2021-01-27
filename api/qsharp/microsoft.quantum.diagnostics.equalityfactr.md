---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 86d2ddff79f0bca7badd95a2fe2156c558fa7f86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853329"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="55973-102">EqualityFactR 関数</span><span class="sxs-lookup"><span data-stu-id="55973-102">EqualityFactR function</span></span>

<span data-ttu-id="55973-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="55973-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="55973-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="55973-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="55973-105">古典的な結果変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="55973-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="55973-106">入力</span><span class="sxs-lookup"><span data-stu-id="55973-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="55973-107">実績:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="55973-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="55973-108">チェックする変数。</span><span class="sxs-lookup"><span data-stu-id="55973-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="55973-109">想定:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="55973-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="55973-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="55973-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="55973-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="55973-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="55973-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="55973-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55973-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55973-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

