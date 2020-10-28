---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 1575b93b6c3242e1dffafb330c44cc017a72a8b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722126"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="0c7be-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="0c7be-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="0c7be-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0c7be-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0c7be-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c7be-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c7be-105">`BlockEncodingByLCU` の実装です。</span><span class="sxs-lookup"><span data-stu-id="0c7be-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit
```


## <a name="input"></a><span data-ttu-id="0c7be-106">入力</span><span class="sxs-lookup"><span data-stu-id="0c7be-106">Input</span></span>

### <a name="statepreparation--t--unit-adj--ctl"></a><span data-ttu-id="0c7be-107">statePreparation: ' t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0c7be-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="selector--ts--unit-adj--ctl"></a><span data-ttu-id="0c7be-108">セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="0c7be-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="0c7be-109">補助: \</span><span class="sxs-lookup"><span data-stu-id="0c7be-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="0c7be-110">システム:</span><span class="sxs-lookup"><span data-stu-id="0c7be-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="0c7be-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0c7be-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0c7be-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c7be-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0c7be-113">&</span><span class="sxs-lookup"><span data-stu-id="0c7be-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="0c7be-114">Emc</span><span class="sxs-lookup"><span data-stu-id="0c7be-114">'S</span></span>

