---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: eb4116b60bb415465375e374ad84e990135c231c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206546"
---
# <a name="isresultone-function"></a><span data-ttu-id="e338c-102">IsResultOne 関数</span><span class="sxs-lookup"><span data-stu-id="e338c-102">IsResultOne function</span></span>

<span data-ttu-id="e338c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e338c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e338c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e338c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e338c-105">指定された結果値がと等しいかどうかをテスト `One` します。</span><span class="sxs-lookup"><span data-stu-id="e338c-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="e338c-106">入力</span><span class="sxs-lookup"><span data-stu-id="e338c-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="e338c-107">入力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="e338c-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="e338c-108">`Result` テストする値。</span><span class="sxs-lookup"><span data-stu-id="e338c-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e338c-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e338c-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e338c-110">`true` `input` がに等しい場合は、を返し `One` ます。</span><span class="sxs-lookup"><span data-stu-id="e338c-110">Returns `true` if `input` is equal to `One`.</span></span>