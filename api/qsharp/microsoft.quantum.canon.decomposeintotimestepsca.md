---
uid: Microsoft.Quantum.Canon.DecomposeIntoTimeStepsCA
title: DecomposeIntoTimeStepsCA 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposeIntoTimeStepsCA
qsharp.summary: >-
  > [!WARNING]

  > DecomposeIntoTimeStepsCA has been deprecated. Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.
ms.openlocfilehash: aa004098cbc805126109d3356f0f6550b85cd60b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840715"
---
# <a name="decomposeintotimestepsca-function"></a><span data-ttu-id="b9e39-102">DecomposeIntoTimeStepsCA 関数</span><span class="sxs-lookup"><span data-stu-id="b9e39-102">DecomposeIntoTimeStepsCA function</span></span>

<span data-ttu-id="b9e39-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b9e39-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b9e39-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9e39-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="b9e39-105">DecomposeIntoTimeStepsCA は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="b9e39-105">DecomposeIntoTimeStepsCA has been deprecated.</span></span> <span data-ttu-id="b9e39-106">代わりに、<xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="b9e39-106">Please use <xref:Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA> instead.</span></span>



```qsharp
function DecomposeIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b9e39-107">入力</span><span class="sxs-lookup"><span data-stu-id="b9e39-107">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="b9e39-108">nSteps: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b9e39-108">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="b9e39-109">op: ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="b9e39-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="trotterorder--int"></a><span data-ttu-id="b9e39-110">trotterOrder: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b9e39-110">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--doublet--unit--is-adj--ctl"></a><span data-ttu-id="b9e39-111">出力: ([Double](xref:microsoft.quantum.lang-ref.double), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b9e39-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b9e39-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9e39-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b9e39-113">&</span><span class="sxs-lookup"><span data-stu-id="b9e39-113">'T</span></span>

