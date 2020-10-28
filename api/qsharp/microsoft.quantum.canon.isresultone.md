---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: fa8845fd92e5c16b4ff15436caf42df4f1e151cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716051"
---
# <a name="isresultone-function"></a><span data-ttu-id="9802b-102">IsResultOne 関数</span><span class="sxs-lookup"><span data-stu-id="9802b-102">IsResultOne function</span></span>

<span data-ttu-id="9802b-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9802b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9802b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9802b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9802b-105">指定された結果値がと等しいかどうかをテスト `One` します。</span><span class="sxs-lookup"><span data-stu-id="9802b-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="9802b-106">入力</span><span class="sxs-lookup"><span data-stu-id="9802b-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="9802b-107">入力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9802b-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="9802b-108">`Result` テストする値。</span><span class="sxs-lookup"><span data-stu-id="9802b-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="9802b-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9802b-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9802b-110">`true` `input` がに等しい場合は、を返し `One` ます。</span><span class="sxs-lookup"><span data-stu-id="9802b-110">Returns `true` if `input` is equal to `One`.</span></span>