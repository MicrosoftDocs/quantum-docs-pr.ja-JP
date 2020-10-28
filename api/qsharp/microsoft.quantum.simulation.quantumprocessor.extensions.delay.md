---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.Delay
title: 遅延操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: Delay
qsharp.summary: ''
ms.openlocfilehash: e6d917946f37c97bbab412c13f977aadf1c118e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725668"
---
# <a name="delay-operation"></a><span data-ttu-id="80f96-102">遅延操作</span><span class="sxs-lookup"><span data-stu-id="80f96-102">Delay operation</span></span>

<span data-ttu-id="80f96-103">名前空間: [QuantumProcessor](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)を実行します。</span><span class="sxs-lookup"><span data-stu-id="80f96-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="80f96-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80f96-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation Delay<'T> (op : ('T => Unit), arg : 'T, aux : Unit) : Unit
```


## <a name="input"></a><span data-ttu-id="80f96-105">入力</span><span class="sxs-lookup"><span data-stu-id="80f96-105">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="80f96-106">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80f96-106">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="arg--t"></a><span data-ttu-id="80f96-107">arg: ' t '</span><span class="sxs-lookup"><span data-stu-id="80f96-107">arg : 'T</span></span>




### <a name="aux--unit"></a><span data-ttu-id="80f96-108">aux: [ユニット](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80f96-108">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="80f96-109">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80f96-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="80f96-110">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="80f96-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80f96-111">&</span><span class="sxs-lookup"><span data-stu-id="80f96-111">'T</span></span>

