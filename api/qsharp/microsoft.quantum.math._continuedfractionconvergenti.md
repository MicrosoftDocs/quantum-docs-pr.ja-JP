---
uid: Microsoft.Quantum.Math._ContinuedFractionConvergentI
title: _ContinuedFractionConvergentI 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: _ContinuedFractionConvergentI
qsharp.summary: Internal recursive call to calculate the GCD with a bound
ms.openlocfilehash: ffe2236b29fd193e25b6f2cd599a465043cba946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846950"
---
# <a name="_continuedfractionconvergenti-function"></a><span data-ttu-id="32b1c-102">_ContinuedFractionConvergentI 関数</span><span class="sxs-lookup"><span data-stu-id="32b1c-102">_ContinuedFractionConvergentI function</span></span>

<span data-ttu-id="32b1c-103">名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="32b1c-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="32b1c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32b1c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32b1c-105">バインドされたを使用して GCD を計算するための内部再帰呼び出し</span><span class="sxs-lookup"><span data-stu-id="32b1c-105">Internal recursive call to calculate the GCD with a bound</span></span>

```qsharp
function _ContinuedFractionConvergentI (signA : Int, signB : Int, r : (Int, Int), s : (Int, Int), t : (Int, Int), denominatorBound : Int) : Microsoft.Quantum.Math.Fraction
```


## <a name="input"></a><span data-ttu-id="32b1c-106">入力</span><span class="sxs-lookup"><span data-stu-id="32b1c-106">Input</span></span>

### <a name="signa--int"></a><span data-ttu-id="32b1c-107">signA: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32b1c-107">signA : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="signb--int"></a><span data-ttu-id="32b1c-108">signB: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32b1c-108">signB : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="r--intint"></a><span data-ttu-id="32b1c-109">r: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="32b1c-109">r : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="s--intint"></a><span data-ttu-id="32b1c-110">s: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="32b1c-110">s : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="t--intint"></a><span data-ttu-id="32b1c-111">t: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="32b1c-111">t : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>




### <a name="denominatorbound--int"></a><span data-ttu-id="32b1c-112">denominatorBound: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32b1c-112">denominatorBound : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--fraction"></a><span data-ttu-id="32b1c-113">出力: [分数](xref:Microsoft.Quantum.Math.Fraction)</span><span class="sxs-lookup"><span data-stu-id="32b1c-113">Output : [Fraction](xref:Microsoft.Quantum.Math.Fraction)</span></span>

