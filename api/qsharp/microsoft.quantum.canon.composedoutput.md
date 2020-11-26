---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207464"
---
# <a name="composedoutput-function"></a><span data-ttu-id="8c79c-102">ComposedOutput 関数</span><span class="sxs-lookup"><span data-stu-id="8c79c-102">ComposedOutput function</span></span>

<span data-ttu-id="8c79c-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8c79c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8c79c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8c79c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8c79c-105">`inner`指定された入力に対するとの構成の出力を返し `outer` ます。</span><span class="sxs-lookup"><span data-stu-id="8c79c-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="8c79c-106">入力</span><span class="sxs-lookup"><span data-stu-id="8c79c-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="8c79c-107">外部: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="8c79c-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="8c79c-108">内部: > ' U</span><span class="sxs-lookup"><span data-stu-id="8c79c-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="8c79c-109">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="8c79c-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="8c79c-110">出力: ' V</span><span class="sxs-lookup"><span data-stu-id="8c79c-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8c79c-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="8c79c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8c79c-112">&</span><span class="sxs-lookup"><span data-stu-id="8c79c-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="8c79c-113">' U</span><span class="sxs-lookup"><span data-stu-id="8c79c-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="8c79c-114">' V</span><span class="sxs-lookup"><span data-stu-id="8c79c-114">'V</span></span>

