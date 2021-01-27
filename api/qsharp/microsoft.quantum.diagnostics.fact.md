---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853319"
---
# <a name="fact-function"></a><span data-ttu-id="88a04-102">Fact 関数</span><span class="sxs-lookup"><span data-stu-id="88a04-102">Fact function</span></span>

<span data-ttu-id="88a04-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="88a04-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="88a04-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="88a04-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="88a04-105">クラシック条件が true であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="88a04-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="88a04-106">入力</span><span class="sxs-lookup"><span data-stu-id="88a04-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="88a04-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="88a04-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="88a04-108">宣言する条件。</span><span class="sxs-lookup"><span data-stu-id="88a04-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="88a04-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="88a04-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="88a04-110">古典条件が false の場合に印刷されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="88a04-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88a04-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88a04-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="88a04-112">例</span><span class="sxs-lookup"><span data-stu-id="88a04-112">Example</span></span>

<span data-ttu-id="88a04-113">次の Q # スニペットは失敗します。</span><span class="sxs-lookup"><span data-stu-id="88a04-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="88a04-114">参照</span><span class="sxs-lookup"><span data-stu-id="88a04-114">See Also</span></span>

- [<span data-ttu-id="88a04-115">Microsoft... 診断の不一致</span><span class="sxs-lookup"><span data-stu-id="88a04-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)