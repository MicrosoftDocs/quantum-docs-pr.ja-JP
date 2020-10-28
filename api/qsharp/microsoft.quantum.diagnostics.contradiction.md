---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: 不一致関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712868"
---
# <a name="contradiction-function"></a><span data-ttu-id="d7d50-102">不一致関数</span><span class="sxs-lookup"><span data-stu-id="d7d50-102">Contradiction function</span></span>

<span data-ttu-id="d7d50-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d7d50-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d7d50-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d7d50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d7d50-105">クラシック条件が false であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="d7d50-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d7d50-106">入力</span><span class="sxs-lookup"><span data-stu-id="d7d50-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="d7d50-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d7d50-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d7d50-108">宣言する条件。</span><span class="sxs-lookup"><span data-stu-id="d7d50-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="d7d50-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d7d50-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d7d50-110">クラシック条件が true の場合に印刷されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="d7d50-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d7d50-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d7d50-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="d7d50-112">参照</span><span class="sxs-lookup"><span data-stu-id="d7d50-112">See Also</span></span>

- [<span data-ttu-id="d7d50-113">Microsoft... 診断</span><span class="sxs-lookup"><span data-stu-id="d7d50-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)