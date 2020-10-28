---
uid: Microsoft.Quantum.Canon.IsResultZero
title: IsResultZero 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultZero
qsharp.summary: Tests if a given Result value is equal to `Zero`.
ms.openlocfilehash: 790551690cfba42df4cf7aa77e53e303050bdf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716032"
---
# <a name="isresultzero-function"></a><span data-ttu-id="b86a3-102">IsResultZero 関数</span><span class="sxs-lookup"><span data-stu-id="b86a3-102">IsResultZero function</span></span>

<span data-ttu-id="b86a3-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b86a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b86a3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b86a3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b86a3-105">指定された結果値がと等しいかどうかをテスト `Zero` します。</span><span class="sxs-lookup"><span data-stu-id="b86a3-105">Tests if a given Result value is equal to `Zero`.</span></span>

```qsharp
function IsResultZero (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="b86a3-106">入力</span><span class="sxs-lookup"><span data-stu-id="b86a3-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="b86a3-107">入力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b86a3-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="b86a3-108">`Result` テストする値。</span><span class="sxs-lookup"><span data-stu-id="b86a3-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b86a3-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b86a3-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b86a3-110">`true` `input` がに等しい場合は、を返し `Zero` ます。</span><span class="sxs-lookup"><span data-stu-id="b86a3-110">Returns `true` if `input` is equal to `Zero`.</span></span>