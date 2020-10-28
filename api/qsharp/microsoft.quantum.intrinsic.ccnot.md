---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711538"
---
# <a name="ccnot-operation"></a><span data-ttu-id="a463e-102">CCNOT 操作</span><span class="sxs-lookup"><span data-stu-id="a463e-102">CCNOT operation</span></span>

<span data-ttu-id="a463e-103">名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a463e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a463e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a463e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a463e-105">ダブル制御された (CCNOT) ゲートを3つの qubits に適用します。</span><span class="sxs-lookup"><span data-stu-id="a463e-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="a463e-106">入力</span><span class="sxs-lookup"><span data-stu-id="a463e-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="a463e-107">control1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a463e-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a463e-108">CCNOT gate の最初の制御 qubit。</span><span class="sxs-lookup"><span data-stu-id="a463e-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="a463e-109">control2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a463e-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a463e-110">CCNOT gate の2番目のコントロール qubit。</span><span class="sxs-lookup"><span data-stu-id="a463e-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a463e-111">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a463e-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a463e-112">CCNOT gate のターゲット qubit。</span><span class="sxs-lookup"><span data-stu-id="a463e-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a463e-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a463e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a463e-114">解説</span><span class="sxs-lookup"><span data-stu-id="a463e-114">Remarks</span></span>

<span data-ttu-id="a463e-115">次と同じです。</span><span class="sxs-lookup"><span data-stu-id="a463e-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```