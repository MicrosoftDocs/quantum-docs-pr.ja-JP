---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201922"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="03af6-102">EqualityFactB 関数</span><span class="sxs-lookup"><span data-stu-id="03af6-102">EqualityFactB function</span></span>

<span data-ttu-id="03af6-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="03af6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="03af6-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03af6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03af6-105">クラシック Bool 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="03af6-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="03af6-106">入力</span><span class="sxs-lookup"><span data-stu-id="03af6-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="03af6-107">実際の値: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03af6-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03af6-108">チェックする変数。</span><span class="sxs-lookup"><span data-stu-id="03af6-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="03af6-109">必要: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="03af6-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="03af6-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="03af6-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="03af6-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="03af6-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="03af6-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="03af6-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="03af6-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="03af6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

