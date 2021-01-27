---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842499"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="585ce-102">StateOracleFromDeterministicStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="585ce-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="585ce-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="585ce-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="585ce-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="585ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="585ce-105">型の oracle `DeterministicStateOracle` をに変換 `StateOracle` します。</span><span class="sxs-lookup"><span data-stu-id="585ce-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="585ce-106">入力</span><span class="sxs-lookup"><span data-stu-id="585ce-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="585ce-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="585ce-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="585ce-108">型の状態準備 oracle $A $ `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="585ce-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="585ce-109">出力: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="585ce-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="585ce-110">同じ状態準備 oracle $A $ が、現在は型になって `StateOracle` います。</span><span class="sxs-lookup"><span data-stu-id="585ce-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="585ce-111">こののフラグインデックス `StateOracle` はダミー変数であり、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="585ce-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="585ce-112">参照</span><span class="sxs-lookup"><span data-stu-id="585ce-112">See Also</span></span>

- [<span data-ttu-id="585ce-113">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="585ce-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="585ce-114">Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="585ce-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)