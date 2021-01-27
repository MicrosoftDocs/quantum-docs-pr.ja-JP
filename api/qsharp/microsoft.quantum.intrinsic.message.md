---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849375"
---
# <a name="message-function"></a><span data-ttu-id="72f76-102">Message 関数</span><span class="sxs-lookup"><span data-stu-id="72f76-102">Message function</span></span>

<span data-ttu-id="72f76-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="72f76-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="72f76-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="72f76-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="72f76-105">メッセージのログを記録します。</span><span class="sxs-lookup"><span data-stu-id="72f76-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="72f76-106">入力</span><span class="sxs-lookup"><span data-stu-id="72f76-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="72f76-107">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="72f76-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="72f76-108">報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="72f76-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72f76-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72f76-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="72f76-110">解説</span><span class="sxs-lookup"><span data-stu-id="72f76-110">Remarks</span></span>

<span data-ttu-id="72f76-111">この関数の特定の動作はシミュレーターに依存しますが、ほとんどの場合、指定されたメッセージはコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="72f76-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>