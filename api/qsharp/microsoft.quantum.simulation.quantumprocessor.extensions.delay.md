---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.Delay
title: 遅延操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: Delay
qsharp.summary: ''
ms.openlocfilehash: 8584867f148c23e744a6fe7d1c187972287ead5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854157"
---
# <a name="delay-operation"></a><span data-ttu-id="ff745-102">遅延操作</span><span class="sxs-lookup"><span data-stu-id="ff745-102">Delay operation</span></span>

<span data-ttu-id="ff745-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="ff745-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="ff745-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="ff745-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation Delay<'T> (op : ('T => Unit), arg : 'T, aux : Unit) : Unit
```


## <a name="input"></a><span data-ttu-id="ff745-105">入力</span><span class="sxs-lookup"><span data-stu-id="ff745-105">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ff745-106">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff745-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="arg--t"></a><span data-ttu-id="ff745-107">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="ff745-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="ff745-108">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff745-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ff745-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff745-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff745-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff745-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff745-111">&</span><span class="sxs-lookup"><span data-stu-id="ff745-111">'T</span></span>

