---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.Delay
title: 遅延操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: Delay
qsharp.summary: ''
ms.openlocfilehash: cfc53bda7e97e22f5ca234d8e4cf92f190a46104
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230771"
---
# <a name="delay-operation"></a><span data-ttu-id="94faf-102">遅延操作</span><span class="sxs-lookup"><span data-stu-id="94faf-102">Delay operation</span></span>

<span data-ttu-id="94faf-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="94faf-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="94faf-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="94faf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation Delay<'T> (op : ('T => Unit), arg : 'T, aux : Unit) : Unit
```


## <a name="input"></a><span data-ttu-id="94faf-105">入力</span><span class="sxs-lookup"><span data-stu-id="94faf-105">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="94faf-106">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94faf-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="arg--t"></a><span data-ttu-id="94faf-107">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="94faf-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="94faf-108">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94faf-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="94faf-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="94faf-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="94faf-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="94faf-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94faf-111">&</span><span class="sxs-lookup"><span data-stu-id="94faf-111">'T</span></span>

