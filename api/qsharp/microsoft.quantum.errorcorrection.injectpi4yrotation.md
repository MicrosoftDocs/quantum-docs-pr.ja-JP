---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: InjectPi4YRotation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 4ff0abe67a6d18204e417a45f8d8f1d092d02b88
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200800"
---
# <a name="injectpi4yrotation-operation"></a><span data-ttu-id="8d52d-102">InjectPi4YRotation 操作</span><span class="sxs-lookup"><span data-stu-id="8d52d-102">InjectPi4YRotation operation</span></span>

<span data-ttu-id="8d52d-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8d52d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8d52d-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d52d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d52d-105">Y 軸について1つの qubit をπ/4 で回転します。</span><span class="sxs-lookup"><span data-stu-id="8d52d-105">Rotates a single qubit by π/4 about the Y-axis.</span></span>

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="8d52d-106">説明</span><span class="sxs-lookup"><span data-stu-id="8d52d-106">Description</span></span>

<span data-ttu-id="8d52d-107">に対してπ/4 回転を実行 `Y` します。</span><span class="sxs-lookup"><span data-stu-id="8d52d-107">Performs a π/4 rotation about `Y`.</span></span>

<span data-ttu-id="8d52d-108">回転はマジック状態を使用して実行されます。つまり、$ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \ sin \frac{\pi} \ket という状態のコピー {8} です {1} 。</span><span class="sxs-lookup"><span data-stu-id="8d52d-108">The rotation is performed by consuming a magic state; that is, a copy of the state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1}.</span></span>
<span data-ttu-id="8d52d-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8d52d-109">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="8d52d-110">入力</span><span class="sxs-lookup"><span data-stu-id="8d52d-110">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="8d52d-111">データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d52d-111">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d52d-112">$Y $ ($ \ pi/$4) について回転する qubit。</span><span class="sxs-lookup"><span data-stu-id="8d52d-112">A qubit to be rotated about $Y$ by $\pi / 4$.</span></span>


### <a name="magic--qubit"></a><span data-ttu-id="8d52d-113">マジック: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8d52d-113">magic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8d52d-114">マジック状態の最初の qubit。</span><span class="sxs-lookup"><span data-stu-id="8d52d-114">A qubit initially in the magic state.</span></span> <span data-ttu-id="8d52d-115">この操作の次のアプリケーション `magic` は、$ \ket {0} $ 状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="8d52d-115">Following application of this operation, `magic` is returned to the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d52d-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d52d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8d52d-117">解説</span><span class="sxs-lookup"><span data-stu-id="8d52d-117">Remarks</span></span>

<span data-ttu-id="8d52d-118">同等のものを次に示します。</span><span class="sxs-lookup"><span data-stu-id="8d52d-118">The following are equivalent:</span></span>

```qsharp
Ry(PI() / 4.0, data);
```

<span data-ttu-id="8d52d-119">and</span><span class="sxs-lookup"><span data-stu-id="8d52d-119">and</span></span>

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

<span data-ttu-id="8d52d-120">この操作では、ファンクタがサポートされます。この `Adjoint` 場合、同じマジック状態が使用されますが、データ qubit への影響は $-\ pi/4 $ $Y $-ローテーションです。</span><span class="sxs-lookup"><span data-stu-id="8d52d-120">This operation supports the `Adjoint` functor, in which case the same magic state is consumed, but the effect on the data qubit is a $-\pi/4$ $Y$-rotation.</span></span>