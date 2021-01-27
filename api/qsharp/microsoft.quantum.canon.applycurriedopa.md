---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: 100d8a42d6475d3cdda349a2e685a6fbfff23cdc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845085"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="93f60-102">ApplyCurriedOpA 操作</span><span class="sxs-lookup"><span data-stu-id="93f60-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="93f60-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93f60-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93f60-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93f60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="93f60-105">入力</span><span class="sxs-lookup"><span data-stu-id="93f60-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="93f60-106">curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="93f60-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="93f60-107">最初:</span><span class="sxs-lookup"><span data-stu-id="93f60-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="93f60-108">2番目: ' U</span><span class="sxs-lookup"><span data-stu-id="93f60-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="93f60-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93f60-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93f60-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="93f60-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93f60-111">&</span><span class="sxs-lookup"><span data-stu-id="93f60-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="93f60-112">' U</span><span class="sxs-lookup"><span data-stu-id="93f60-112">'U</span></span>

