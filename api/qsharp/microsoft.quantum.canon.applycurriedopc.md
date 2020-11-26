---
uid: Microsoft.Quantum.Canon.ApplyCurriedOpC
title: ApplyCurriedOpC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCurriedOpC
qsharp.summary: ''
ms.openlocfilehash: faca9b3f6d9a132b591a532c9e2ce54af1f0b182
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218939"
---
# <a name="applycurriedopc-operation"></a><span data-ttu-id="0f164-102">ApplyCurriedOpC 操作</span><span class="sxs-lookup"><span data-stu-id="0f164-102">ApplyCurriedOpC operation</span></span>

<span data-ttu-id="0f164-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0f164-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0f164-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0f164-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation ApplyCurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl)), first : 'T, second : 'U) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="0f164-105">入力</span><span class="sxs-lookup"><span data-stu-id="0f164-105">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="0f164-106">curriedOp: > ' U => [単位](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="0f164-106">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>




### <a name="first--t"></a><span data-ttu-id="0f164-107">最初:</span><span class="sxs-lookup"><span data-stu-id="0f164-107">first : 'T</span></span>




### <a name="second--u"></a><span data-ttu-id="0f164-108">2番目: ' U</span><span class="sxs-lookup"><span data-stu-id="0f164-108">second : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="0f164-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f164-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0f164-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f164-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0f164-111">&</span><span class="sxs-lookup"><span data-stu-id="0f164-111">'T</span></span>


### <a name="u"></a><span data-ttu-id="0f164-112">' U</span><span class="sxs-lookup"><span data-stu-id="0f164-112">'U</span></span>

