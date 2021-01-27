---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856805"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="a6aa2-102">QuantumROMQubitCount 関数</span><span class="sxs-lookup"><span data-stu-id="a6aa2-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="a6aa2-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="a6aa2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="a6aa2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a6aa2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="a6aa2-105">QuantumROMQubitCount は非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="a6aa2-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="a6aa2-106">代わりに、<xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> を使用してください。</span><span class="sxs-lookup"><span data-stu-id="a6aa2-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="a6aa2-107">によって返された操作に割り当てる必要がある qubits の合計数を返し `QuantumROM` ます。</span><span class="sxs-lookup"><span data-stu-id="a6aa2-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="a6aa2-108">入力</span><span class="sxs-lookup"><span data-stu-id="a6aa2-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="a6aa2-109">targetError: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a6aa2-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a6aa2-110">ターゲットエラー $ \ イプシロン $。</span><span class="sxs-lookup"><span data-stu-id="a6aa2-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="a6aa2-111">nCoeffs: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6aa2-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6aa2-112">で指定された係数の数 `QuantumROM` 。</span><span class="sxs-lookup"><span data-stu-id="a6aa2-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="a6aa2-113">出力: ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="a6aa2-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="a6aa2-114">最初のパラメーター</span><span class="sxs-lookup"><span data-stu-id="a6aa2-114">First parameter</span></span>

<span data-ttu-id="a6aa2-115">は、 `(x,(y,z))` `x = y + z` 割り当てられた qubits の合計数、は `y` レジスタの qubits の数、は `LittleEndian` `z` ガベージ qubits の数であるタプルです。</span><span class="sxs-lookup"><span data-stu-id="a6aa2-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>