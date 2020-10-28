---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 0428a46bc639bc8a0697f5bd392f85b8b9f40ee5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711426"
---
# <a name="message-function"></a><span data-ttu-id="07bf6-102">Message 関数</span><span class="sxs-lookup"><span data-stu-id="07bf6-102">Message function</span></span>

<span data-ttu-id="07bf6-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="07bf6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="07bf6-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07bf6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07bf6-105">メッセージのログを記録します。</span><span class="sxs-lookup"><span data-stu-id="07bf6-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="07bf6-106">入力</span><span class="sxs-lookup"><span data-stu-id="07bf6-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="07bf6-107">msg: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="07bf6-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="07bf6-108">報告されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="07bf6-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07bf6-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07bf6-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="07bf6-110">解説</span><span class="sxs-lookup"><span data-stu-id="07bf6-110">Remarks</span></span>

<span data-ttu-id="07bf6-111">この関数の特定の動作はシミュレーターに依存しますが、ほとんどの場合、指定されたメッセージはコンソールに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="07bf6-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>