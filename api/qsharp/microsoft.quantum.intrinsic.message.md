---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199014"
---
# <a name="message-function"></a><span data-ttu-id="d5721-102">Message 関数</span><span class="sxs-lookup"><span data-stu-id="d5721-102">Message function</span></span>

<span data-ttu-id="d5721-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="d5721-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="d5721-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="d5721-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d5721-105">メッセージのログを記録します。</span><span class="sxs-lookup"><span data-stu-id="d5721-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d5721-106">入力</span><span class="sxs-lookup"><span data-stu-id="d5721-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="d5721-107">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d5721-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d5721-108">報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="d5721-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5721-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5721-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d5721-110">解説</span><span class="sxs-lookup"><span data-stu-id="d5721-110">Remarks</span></span>

<span data-ttu-id="d5721-111">この関数の特定の動作はシミュレーターに依存しますが、ほとんどの場合、指定されたメッセージはコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d5721-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>