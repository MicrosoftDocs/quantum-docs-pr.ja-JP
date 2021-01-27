---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: _assertEqualOnBasisVector 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853582"
---
# <a name="_assertequalonbasisvector-operation"></a><span data-ttu-id="2cb66-102">_assertEqualOnBasisVector 操作</span><span class="sxs-lookup"><span data-stu-id="2cb66-102">_assertEqualOnBasisVector operation</span></span>

<span data-ttu-id="2cb66-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2cb66-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2cb66-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="2cb66-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="2cb66-105">2つの操作を適用した結果が同じであるかどうかを確認し `givenU` `expectedU` ます。</span><span class="sxs-lookup"><span data-stu-id="2cb66-105">Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same.</span></span> <span data-ttu-id="2cb66-106">ベース状態は、パラメーターによって記述され `basis` ます。</span><span class="sxs-lookup"><span data-stu-id="2cb66-106">The basis state is described by `basis` parameter.</span></span>
<span data-ttu-id="2cb66-107"><xref:microsoft.quantum.extensions.fliptobasis>この説明の詳細については、「関数」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2cb66-107">See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.</span></span>

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="2cb66-108">入力</span><span class="sxs-lookup"><span data-stu-id="2cb66-108">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="2cb66-109">ベース: [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2cb66-109">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2cb66-110">$N $ qubit のそれぞれに対して、単一 qubit basis 状態 ID (0 <= ID <= 3) で指定された基礎状態。</span><span class="sxs-lookup"><span data-stu-id="2cb66-110">Basis state specified by a single-qubit basis state ID (0 <= id <= 3) for each of $n$ qubits.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="2cb66-111">与え u: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cb66-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2cb66-112">$N $ qubits の操作を確認します。</span><span class="sxs-lookup"><span data-stu-id="2cb66-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="2cb66-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="2cb66-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="2cb66-114">$N $ qubits に対する参照操作が、と比較されます。</span><span class="sxs-lookup"><span data-stu-id="2cb66-114">Reference operation on $n$ qubits that givenU is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2cb66-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2cb66-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

