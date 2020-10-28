---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712775"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="f8dda-102">EqualityFactB 関数</span><span class="sxs-lookup"><span data-stu-id="f8dda-102">EqualityFactB function</span></span>

<span data-ttu-id="f8dda-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="f8dda-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="f8dda-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f8dda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f8dda-105">クラシック Bool 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="f8dda-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="f8dda-106">入力</span><span class="sxs-lookup"><span data-stu-id="f8dda-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="f8dda-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8dda-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8dda-108">チェックする変数。</span><span class="sxs-lookup"><span data-stu-id="f8dda-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="f8dda-109">必要: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f8dda-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f8dda-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="f8dda-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="f8dda-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f8dda-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f8dda-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="f8dda-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f8dda-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f8dda-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

