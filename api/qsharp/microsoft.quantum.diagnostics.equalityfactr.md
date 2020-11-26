---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201769"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="89302-102">EqualityFactR 関数</span><span class="sxs-lookup"><span data-stu-id="89302-102">EqualityFactR function</span></span>

<span data-ttu-id="89302-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="89302-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="89302-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="89302-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="89302-105">古典的な結果変数に予期される値があることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="89302-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="89302-106">入力</span><span class="sxs-lookup"><span data-stu-id="89302-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="89302-107">実績:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="89302-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="89302-108">チェックする変数。</span><span class="sxs-lookup"><span data-stu-id="89302-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="89302-109">想定:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="89302-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="89302-110">予期される値。</span><span class="sxs-lookup"><span data-stu-id="89302-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="89302-111">message: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="89302-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="89302-112">アサーションがトリガーされたときに使用されるエラーメッセージ文字列。</span><span class="sxs-lookup"><span data-stu-id="89302-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="89302-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="89302-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

