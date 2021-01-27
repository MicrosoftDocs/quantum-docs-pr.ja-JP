---
uid: Microsoft.Quantum.Canon.ApplyCurriedOp
title: ApplyCurriedOp 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOp
qsharp.summary: ''
ms.openlocfilehash: c252eceb6a307ea9514aaa8aa3a3de1f9fa1b698
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841930"
---
# <a name="applycurriedop-operation"></a><span data-ttu-id="289bc-102">ApplyCurriedOp 操作</span><span class="sxs-lookup"><span data-stu-id="289bc-102">ApplyCurriedOp operation</span></span>

<span data-ttu-id="289bc-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="289bc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="289bc-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="289bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="289bc-105">入力</span><span class="sxs-lookup"><span data-stu-id="289bc-105">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="289bc-106">curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="289bc-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="first--t"></a><span data-ttu-id="289bc-107">最初:</span><span class="sxs-lookup"><span data-stu-id="289bc-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="289bc-108">2番目: ' U</span><span class="sxs-lookup"><span data-stu-id="289bc-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="289bc-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="289bc-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="289bc-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="289bc-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="289bc-111">&</span><span class="sxs-lookup"><span data-stu-id="289bc-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="289bc-112">' U</span><span class="sxs-lookup"><span data-stu-id="289bc-112">'U</span></span>

