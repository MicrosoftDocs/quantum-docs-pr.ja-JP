---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712756"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="89d60-102">EqualityFactL 関数</span><span class="sxs-lookup"><span data-stu-id="89d60-102">EqualityFactL function</span></span>

<span data-ttu-id="89d60-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="89d60-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="89d60-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="89d60-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="89d60-105">古典 BigInt 変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="89d60-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="89d60-106">入力</span><span class="sxs-lookup"><span data-stu-id="89d60-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="89d60-107">実際: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="89d60-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="89d60-108">確認する数値。</span><span class="sxs-lookup"><span data-stu-id="89d60-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="89d60-109">予想される: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="89d60-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="89d60-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="89d60-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="89d60-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="89d60-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="89d60-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="89d60-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89d60-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89d60-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

