---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712677"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="b3adf-102">FormattedFailure 関数</span><span class="sxs-lookup"><span data-stu-id="b3adf-102">FormattedFailure function</span></span>

<span data-ttu-id="b3adf-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b3adf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b3adf-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3adf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3adf-105">意味のあるエラーメッセージで失敗するために使用される内部関数です。</span><span class="sxs-lookup"><span data-stu-id="b3adf-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b3adf-106">入力</span><span class="sxs-lookup"><span data-stu-id="b3adf-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="b3adf-107">実際の:</span><span class="sxs-lookup"><span data-stu-id="b3adf-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="b3adf-108">' t ' が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3adf-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="b3adf-109">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b3adf-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="b3adf-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b3adf-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b3adf-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3adf-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b3adf-112">&</span><span class="sxs-lookup"><span data-stu-id="b3adf-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b3adf-113">解説</span><span class="sxs-lookup"><span data-stu-id="b3adf-113">Remarks</span></span>

<span data-ttu-id="b3adf-114">この関数は、書式設定された矛盾削除を転送できるように、シミュレーションランタイムによってエミュレートされることを目的としています。</span><span class="sxs-lookup"><span data-stu-id="b3adf-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>