---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZ
title: _JWOptimizedZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZ
qsharp.summary: Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.
ms.openlocfilehash: 8bbd4af0389a7b748be11dc50bacd2c178521adc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724632"
---
# <a name="_jwoptimizedz-operation"></a><span data-ttu-id="da92d-102">_JWOptimizedZ 操作</span><span class="sxs-lookup"><span data-stu-id="da92d-102">_JWOptimizedZ operation</span></span>

<span data-ttu-id="da92d-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="da92d-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="da92d-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="da92d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="da92d-105">フェーズの推定で、C ではなく C の Rz を2つのフェーズに回転させます。</span><span class="sxs-lookup"><span data-stu-id="da92d-105">Applies a Rz rotation, with a C-NOT trick to double phase in phase estimation.</span></span>

```qsharp
operation _JWOptimizedZ (angle : Double, parityQubit : Qubit, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="da92d-106">入力</span><span class="sxs-lookup"><span data-stu-id="da92d-106">Input</span></span>

### <a name="angle--double"></a><span data-ttu-id="da92d-107">angle: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="da92d-107">angle : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="da92d-108">Rz の回転角度。</span><span class="sxs-lookup"><span data-stu-id="da92d-108">Angle of Rz rotation.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="da92d-109">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da92d-109">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="da92d-110">タイム進化の符号を決定する qubit。</span><span class="sxs-lookup"><span data-stu-id="da92d-110">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="da92d-111">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="da92d-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="da92d-112">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da92d-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

