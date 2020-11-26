---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b4e9b62b20e12a8dce544ce16dcddcf15fdf2680
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206529"
---
# <a name="isresultzero-function"></a><span data-ttu-id="b69db-102">IsResultZero 関数</span><span class="sxs-lookup"><span data-stu-id="b69db-102">IsResultZero function</span></span>

<span data-ttu-id="b69db-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b69db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b69db-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b69db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b69db-105">指定された結果値がと等しいかどうかをテスト `Zero` します。</span><span class="sxs-lookup"><span data-stu-id="b69db-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="b69db-106">入力</span><span class="sxs-lookup"><span data-stu-id="b69db-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="b69db-107">入力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b69db-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="b69db-108">`Result` テストする値。</span><span class="sxs-lookup"><span data-stu-id="b69db-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b69db-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b69db-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b69db-110">`true` `input` がに等しい場合は、を返し `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="b69db-110">Returns `true` if `input` is equal to `Zero`.</span></span>