---
uid: Microsoft.Quantum.Canon.IsResultOne
title: IsResultOne 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IsResultOne
qsharp.summary: Tests if a given Result value is equal to `One`.
ms.openlocfilehash: f259c21e6cc0a4886332e9ffcb546e527ec7def1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840328"
---
# <a name="isresultone-function"></a><span data-ttu-id="39f26-102">IsResultOne 関数</span><span class="sxs-lookup"><span data-stu-id="39f26-102">IsResultOne function</span></span>

<span data-ttu-id="39f26-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39f26-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39f26-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39f26-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39f26-105">指定された結果値がと等しいかどうかをテスト `One` します。</span><span class="sxs-lookup"><span data-stu-id="39f26-105">Tests if a given Result value is equal to `One`.</span></span>

```qsharp
function IsResultOne (input : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="39f26-106">入力</span><span class="sxs-lookup"><span data-stu-id="39f26-106">Input</span></span>

### <a name="input--__invalidresult__"></a><span data-ttu-id="39f26-107">入力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="39f26-107">input : __invalid<Result>__</span></span>

<span data-ttu-id="39f26-108">`Result` テストする値。</span><span class="sxs-lookup"><span data-stu-id="39f26-108">`Result` value to be tested.</span></span>



## <a name="output--bool"></a><span data-ttu-id="39f26-109">出力: [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="39f26-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="39f26-110">`true` `input` がに等しい場合は、を返し `One` ます。</span><span class="sxs-lookup"><span data-stu-id="39f26-110">Returns `true` if `input` is equal to `One`.</span></span>