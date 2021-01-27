---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: P# liblockencoding 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848018"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="45533-102">P# liblockencoding 関数</span><span class="sxs-lookup"><span data-stu-id="45533-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="45533-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="45533-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="45533-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45533-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45533-105">Hamiltonian のブロックエンコードのユニタリを作成します。</span><span class="sxs-lookup"><span data-stu-id="45533-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="45533-106">Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ は、$ $ \ $P $ という実数の合計によって記述されます。</span><span class="sxs-lookup"><span data-stu-id="45533-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="45533-107">入力</span><span class="sxs-lookup"><span data-stu-id="45533-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="45533-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="45533-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="45533-109">`GeneratorSystem`$ $H を、P# li 用語の合計として記述する。</span><span class="sxs-lookup"><span data-stu-id="45533-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="45533-110">出力: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="45533-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="45533-111">最初のパラメーター</span><span class="sxs-lookup"><span data-stu-id="45533-111">First parameter</span></span>

<span data-ttu-id="45533-112">係数 $ \ alpha = \ sum_ {j} | \ alpha_j | $ の1つの基準です。</span><span class="sxs-lookup"><span data-stu-id="45533-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="45533-113">2番目のパラメーター</span><span class="sxs-lookup"><span data-stu-id="45533-113">Second parameter</span></span>

<span data-ttu-id="45533-114">`BlockEncodingReflection`Hamiltonian $H $ の1つの $U ($) です。</span><span class="sxs-lookup"><span data-stu-id="45533-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="45533-115">このユニタリは $U ^ 2 = I $ に一致するので、リフレクションでもあります。</span><span class="sxs-lookup"><span data-stu-id="45533-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="45533-116">解説</span><span class="sxs-lookup"><span data-stu-id="45533-116">Remarks</span></span>

<span data-ttu-id="45533-117">これを取得するには、状態 $ \ sum_ {j} \ sqrt{\ alpha_j/\alpha}\ket{j} $ を準備して準備を解除し、乗算によって制御されるユニタリおよびを構築し <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> ます。</span><span class="sxs-lookup"><span data-stu-id="45533-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>