---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716485"
---
# <a name="composedoutput-function"></a><span data-ttu-id="c62ff-102">ComposedOutput 関数</span><span class="sxs-lookup"><span data-stu-id="c62ff-102">ComposedOutput function</span></span>

<span data-ttu-id="c62ff-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c62ff-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c62ff-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c62ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c62ff-105">`inner`指定された入力に対するとの構成の出力を返し `outer` ます。</span><span class="sxs-lookup"><span data-stu-id="c62ff-105">Returns the output of the composition of `inner` and `outer` for a given input.</span></span>

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a><span data-ttu-id="c62ff-106">入力</span><span class="sxs-lookup"><span data-stu-id="c62ff-106">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="c62ff-107">外部: ' U-> ' V</span><span class="sxs-lookup"><span data-stu-id="c62ff-107">outer : 'U -> 'V</span></span>




### <a name="inner--t---u"></a><span data-ttu-id="c62ff-108">内部: > ' U</span><span class="sxs-lookup"><span data-stu-id="c62ff-108">inner : 'T -> 'U</span></span>




### <a name="target--t"></a><span data-ttu-id="c62ff-109">ターゲット: \</span><span class="sxs-lookup"><span data-stu-id="c62ff-109">target : 'T</span></span>





## <a name="output--v"></a><span data-ttu-id="c62ff-110">出力: ' V</span><span class="sxs-lookup"><span data-stu-id="c62ff-110">Output : 'V</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c62ff-111">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="c62ff-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c62ff-112">&</span><span class="sxs-lookup"><span data-stu-id="c62ff-112">'T</span></span>


### <a name="u"></a><span data-ttu-id="c62ff-113">' U</span><span class="sxs-lookup"><span data-stu-id="c62ff-113">'U</span></span>


### <a name="v"></a><span data-ttu-id="c62ff-114">' V</span><span class="sxs-lookup"><span data-stu-id="c62ff-114">'V</span></span>

