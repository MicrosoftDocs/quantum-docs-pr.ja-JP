---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712686"
---
# <a name="fact-function"></a><span data-ttu-id="cb5b9-102">Fact 関数</span><span class="sxs-lookup"><span data-stu-id="cb5b9-102">Fact function</span></span>

<span data-ttu-id="cb5b9-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cb5b9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cb5b9-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb5b9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb5b9-105">クラシック条件が true であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="cb5b9-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cb5b9-106">入力</span><span class="sxs-lookup"><span data-stu-id="cb5b9-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="cb5b9-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cb5b9-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cb5b9-108">宣言する条件。</span><span class="sxs-lookup"><span data-stu-id="cb5b9-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="cb5b9-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cb5b9-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cb5b9-110">古典条件が false の場合に印刷されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="cb5b9-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cb5b9-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cb5b9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="cb5b9-112">参照</span><span class="sxs-lookup"><span data-stu-id="cb5b9-112">See Also</span></span>

- [<span data-ttu-id="cb5b9-113">Microsoft... 診断の不一致</span><span class="sxs-lookup"><span data-stu-id="cb5b9-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)