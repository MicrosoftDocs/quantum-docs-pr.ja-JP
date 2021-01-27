---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: b1e7cf6324a2a90f10b6aa93811f2df60fe3afbd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840308"
---
# <a name="isresultzero-function"></a><span data-ttu-id="89970-102">IsResultZero 関数</span><span class="sxs-lookup"><span data-stu-id="89970-102">IsResultZero function</span></span>

<span data-ttu-id="89970-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="89970-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="89970-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89970-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89970-105">指定された結果値がと等しいかどうかをテスト `Zero` します。</span><span class="sxs-lookup"><span data-stu-id="89970-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="89970-106">入力</span><span class="sxs-lookup"><span data-stu-id="89970-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="89970-107">入力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="89970-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="89970-108">`Result` テストする値。</span><span class="sxs-lookup"><span data-stu-id="89970-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="89970-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="89970-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="89970-110">`true` `input` がに等しい場合は、を返し `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="89970-110">Returns `true` if `input` is equal to `Zero`.</span></span>