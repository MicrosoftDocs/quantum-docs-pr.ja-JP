---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 不一致関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829361"
---
# <a name="contradiction-function"></a><span data-ttu-id="11252-102">不一致関数</span><span class="sxs-lookup"><span data-stu-id="11252-102">Contradiction function</span></span>

<span data-ttu-id="11252-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="11252-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="11252-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="11252-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="11252-105">クラシック条件が false であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="11252-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="11252-106">入力</span><span class="sxs-lookup"><span data-stu-id="11252-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="11252-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="11252-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="11252-108">宣言する条件。</span><span class="sxs-lookup"><span data-stu-id="11252-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="11252-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="11252-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="11252-110">クラシック条件が true の場合に印刷されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="11252-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="11252-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11252-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="11252-112">例</span><span class="sxs-lookup"><span data-stu-id="11252-112">Example</span></span>

<span data-ttu-id="11252-113">次の Q # コードは、"Hello, world" を出力します。</span><span class="sxs-lookup"><span data-stu-id="11252-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="11252-114">参照</span><span class="sxs-lookup"><span data-stu-id="11252-114">See Also</span></span>

- [<span data-ttu-id="11252-115">Microsoft... 診断</span><span class="sxs-lookup"><span data-stu-id="11252-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)