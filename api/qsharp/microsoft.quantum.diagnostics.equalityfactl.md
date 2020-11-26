---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201803"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="dc4b1-102">EqualityFactL 関数</span><span class="sxs-lookup"><span data-stu-id="dc4b1-102">EqualityFactL function</span></span>

<span data-ttu-id="dc4b1-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="dc4b1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="dc4b1-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc4b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc4b1-105">古典 BigInt 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="dc4b1-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="dc4b1-106">入力</span><span class="sxs-lookup"><span data-stu-id="dc4b1-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="dc4b1-107">実際: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dc4b1-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dc4b1-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="dc4b1-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="dc4b1-109">予想される: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="dc4b1-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="dc4b1-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="dc4b1-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="dc4b1-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="dc4b1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="dc4b1-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="dc4b1-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc4b1-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc4b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

