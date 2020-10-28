---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpCA
title: ApplyCurriedOpCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpCA
qsharp.summary: ''
ms.openlocfilehash: 4e57772bc5440a473c28279ac125170caaa120f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718315"
---
# <a name="applycurriedopca-operation"></a><span data-ttu-id="1f7c2-102">ApplyCurriedOpCA 操作</span><span class="sxs-lookup"><span data-stu-id="1f7c2-102">ApplyCurriedOpCA operation</span></span>

<span data-ttu-id="1f7c2-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1f7c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1f7c2-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f7c2-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyCurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj)), first : 'T, second : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="1f7c2-105">入力</span><span class="sxs-lookup"><span data-stu-id="1f7c2-105">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="1f7c2-106">curriedOp: > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="1f7c2-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="1f7c2-107">最初:</span><span class="sxs-lookup"><span data-stu-id="1f7c2-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="1f7c2-108">2番目: ' U</span><span class="sxs-lookup"><span data-stu-id="1f7c2-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="1f7c2-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1f7c2-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f7c2-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f7c2-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1f7c2-111">&</span><span class="sxs-lookup"><span data-stu-id="1f7c2-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="1f7c2-112">' U</span><span class="sxs-lookup"><span data-stu-id="1f7c2-112">'U</span></span>

