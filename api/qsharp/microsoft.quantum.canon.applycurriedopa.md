---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpA
title: ApplyCurriedOpA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpA
qsharp.summary: ''
ms.openlocfilehash: db3f63cbe2ee5ef048c7e378864d68696f55331f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218956"
---
# <a name="applycurriedopa-operation"></a><span data-ttu-id="79865-102">ApplyCurriedOpA 操作</span><span class="sxs-lookup"><span data-stu-id="79865-102">ApplyCurriedOpA operation</span></span>

<span data-ttu-id="79865-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="79865-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="79865-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79865-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj)), first : 'T, second : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="79865-105">入力</span><span class="sxs-lookup"><span data-stu-id="79865-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="79865-106">curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="79865-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="first--t"></a><span data-ttu-id="79865-107">最初:</span><span class="sxs-lookup"><span data-stu-id="79865-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="79865-108">2番目: ' U</span><span class="sxs-lookup"><span data-stu-id="79865-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="79865-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79865-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="79865-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="79865-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79865-111">&</span><span class="sxs-lookup"><span data-stu-id="79865-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="79865-112">' U</span><span class="sxs-lookup"><span data-stu-id="79865-112">'U</span></span>

