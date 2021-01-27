---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: b7d37b5115c51596c1b3ed93c53a29e9f36b811d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829141"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="ee1e4-102">EqualityFactL 関数</span><span class="sxs-lookup"><span data-stu-id="ee1e4-102">EqualityFactL function</span></span>

<span data-ttu-id="ee1e4-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ee1e4-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ee1e4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee1e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee1e4-105">古典 BigInt 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="ee1e4-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="ee1e4-106">入力</span><span class="sxs-lookup"><span data-stu-id="ee1e4-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="ee1e4-107">実際: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ee1e4-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ee1e4-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="ee1e4-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="ee1e4-109">予想される: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ee1e4-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ee1e4-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="ee1e4-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="ee1e4-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="ee1e4-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="ee1e4-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="ee1e4-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee1e4-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee1e4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

