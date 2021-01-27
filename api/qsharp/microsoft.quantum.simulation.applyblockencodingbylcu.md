---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: ApplyBlockEncodingByLCU 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852822"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="3c895-102">ApplyBlockEncodingByLCU 操作</span><span class="sxs-lookup"><span data-stu-id="3c895-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="3c895-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3c895-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3c895-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c895-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c895-105">`BlockEncodingByLCU` の実装です。</span><span class="sxs-lookup"><span data-stu-id="3c895-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3c895-106">入力</span><span class="sxs-lookup"><span data-stu-id="3c895-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="3c895-107">statePreparation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="3c895-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="3c895-108">セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="3c895-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="3c895-109">補助: \</span><span class="sxs-lookup"><span data-stu-id="3c895-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="3c895-110">システム:</span><span class="sxs-lookup"><span data-stu-id="3c895-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="3c895-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c895-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c895-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c895-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c895-113">&</span><span class="sxs-lookup"><span data-stu-id="3c895-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="3c895-114">Emc</span><span class="sxs-lookup"><span data-stu-id="3c895-114">'S</span></span>

