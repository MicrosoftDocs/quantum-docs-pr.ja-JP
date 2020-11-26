---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: da809c04059d4fd0f0ec92412a3094f5b582fd91
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201701"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="5238c-102">FormattedFailure 関数</span><span class="sxs-lookup"><span data-stu-id="5238c-102">FormattedFailure function</span></span>

<span data-ttu-id="5238c-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="5238c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="5238c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5238c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5238c-105">意味のあるエラーメッセージで失敗するために使用される内部関数です。</span><span class="sxs-lookup"><span data-stu-id="5238c-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="5238c-106">入力</span><span class="sxs-lookup"><span data-stu-id="5238c-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="5238c-107">実際の:</span><span class="sxs-lookup"><span data-stu-id="5238c-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="5238c-108">' t ' が必要です。</span><span class="sxs-lookup"><span data-stu-id="5238c-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="5238c-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="5238c-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="5238c-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5238c-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5238c-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="5238c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5238c-112">&</span><span class="sxs-lookup"><span data-stu-id="5238c-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5238c-113">解説</span><span class="sxs-lookup"><span data-stu-id="5238c-113">Remarks</span></span>

<span data-ttu-id="5238c-114">この関数は、書式設定された矛盾削除を転送できるように、シミュレーションランタイムによってエミュレートされることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="5238c-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>