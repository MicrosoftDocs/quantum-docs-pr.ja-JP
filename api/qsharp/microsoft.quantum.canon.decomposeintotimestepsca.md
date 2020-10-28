---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: b6f3fe0ececc58d86b916841c513377fbcb59054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716331"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="0d4fa-102">DecomposeIntoTimeStepsCA 関数</span><span class="sxs-lookup"><span data-stu-id="0d4fa-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="0d4fa-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0d4fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0d4fa-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d4fa-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="0d4fa-105">DecomposeIntoTimeStepsCA は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="0d4fa-106">代わりに、<xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0d4fa-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="0d4fa-107">入力</span><span class="sxs-lookup"><span data-stu-id="0d4fa-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="0d4fa-108">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d4fa-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="0d4fa-109">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0d4fa-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="0d4fa-110">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0d4fa-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="0d4fa-111">出力: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0d4fa-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0d4fa-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d4fa-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0d4fa-113">&</span><span class="sxs-lookup"><span data-stu-id="0d4fa-113">'T</span></span>

