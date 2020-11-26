---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 183b1108ead6239e26bb0b38144cb9374e7bf285
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226759"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a><span data-ttu-id="b72ea-102">DeterministicStateOracleFromStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="b72ea-102">DeterministicStateOracleFromStateOracle function</span></span>

<span data-ttu-id="b72ea-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="b72ea-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="b72ea-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b72ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b72ea-105">型の oracle `StateOracle` をに変換 `DeterministicStateOracle` します。</span><span class="sxs-lookup"><span data-stu-id="b72ea-105">Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.</span></span>

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a><span data-ttu-id="b72ea-106">入力</span><span class="sxs-lookup"><span data-stu-id="b72ea-106">Input</span></span>

### <a name="idxflagqubit--int"></a><span data-ttu-id="b72ea-107">idxFlagQubit: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b72ea-107">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b72ea-108">$A $ のフラグ qubit のインデックス。 `stateOracle` 2 つのレジスタを明示的に処理します。フラグ $f $、システム $s $ (例: $A \ket {0} \_ f\ket {\ psi} \_ s $)。</span><span class="sxs-lookup"><span data-stu-id="b72ea-108">The index to the flag qubit of the `stateOracle` $A$, which explicitly acts on two registers: the flag $f$ and the system $s$, e.g. $A\ket{0}\_f\ket{\psi}\_s$.</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="b72ea-109">stateOracle: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="b72ea-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="b72ea-110">型の状態準備 oracle $A $ `StateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="b72ea-110">A state preparation oracle $A$ of type `StateOracle`.</span></span>



## <a name="output--deterministicstateoracle"></a><span data-ttu-id="b72ea-111">出力: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="b72ea-111">Output : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="b72ea-112">同じ状態準備 oracle $A $ ですが、現在は型 `DeterministicStateOracle` であるため、$a、s $ は明示的に分離されています。たとえば、 \Ket{0\psi} \_ {as} $ を $A します。</span><span class="sxs-lookup"><span data-stu-id="b72ea-112">The same state preparation oracle $A$, but now of type `DeterministicStateOracle`, so it acts on a register where $a,s$ no longer explicitly separate, e.g.  $A\ket{0\psi}\_{as}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b72ea-113">参照</span><span class="sxs-lookup"><span data-stu-id="b72ea-113">See Also</span></span>

- [<span data-ttu-id="b72ea-114">Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="b72ea-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)
- [<span data-ttu-id="b72ea-115">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="b72ea-115">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)