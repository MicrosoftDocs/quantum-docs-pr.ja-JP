---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: 8ce6eb16b1dc5a83dd3a9559592c20d6b7b999b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225484"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="7b4c0-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="7b4c0-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="7b4c0-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7b4c0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7b4c0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7b4c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7b4c0-105">`BlockEncodingByLCU` の実装です。</span><span class="sxs-lookup"><span data-stu-id="7b4c0-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7b4c0-106">入力</span><span class="sxs-lookup"><span data-stu-id="7b4c0-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="7b4c0-107">statePreparation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="7b4c0-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="7b4c0-108">セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="7b4c0-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="7b4c0-109">補助: \</span><span class="sxs-lookup"><span data-stu-id="7b4c0-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="7b4c0-110">システム:</span><span class="sxs-lookup"><span data-stu-id="7b4c0-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="7b4c0-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b4c0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b4c0-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b4c0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b4c0-113">&</span><span class="sxs-lookup"><span data-stu-id="7b4c0-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="7b4c0-114">Emc</span><span class="sxs-lookup"><span data-stu-id="7b4c0-114">'S</span></span>

