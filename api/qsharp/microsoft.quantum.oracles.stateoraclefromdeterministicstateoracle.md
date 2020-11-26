---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: f3c225ee185b4b70ab0ea60af6f0fb154288d9bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193813"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="a322f-102">StateOracleFromDeterministicStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="a322f-102">StateOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="a322f-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="a322f-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="a322f-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a322f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a322f-105">型の oracle `DeterministicStateOracle` をに変換 `StateOracle` します。</span><span class="sxs-lookup"><span data-stu-id="a322f-105">Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.</span></span>

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a><span data-ttu-id="a322f-106">入力</span><span class="sxs-lookup"><span data-stu-id="a322f-106">Input</span></span>

### <a name="deterministicstateoracle--deterministicstateoracle"></a><span data-ttu-id="a322f-107">deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="a322f-107">deterministicStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="a322f-108">型の状態準備 oracle $A $ `DeterministicStateOracle` 。</span><span class="sxs-lookup"><span data-stu-id="a322f-108">A state preparation oracle $A$ of type `DeterministicStateOracle`.</span></span>



## <a name="output--stateoracle"></a><span data-ttu-id="a322f-109">出力: [Stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="a322f-109">Output : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="a322f-110">同じ状態準備 oracle $A $ が、現在は型になって `StateOracle` います。</span><span class="sxs-lookup"><span data-stu-id="a322f-110">The same state preparation oracle $A$, but now of type `StateOracle`.</span></span> <span data-ttu-id="a322f-111">こののフラグインデックス `StateOracle` はダミー変数であり、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="a322f-111">Note that the flag index in this `StateOracle` is a dummy variable and has no effect.</span></span>

## <a name="see-also"></a><span data-ttu-id="a322f-112">参照</span><span class="sxs-lookup"><span data-stu-id="a322f-112">See Also</span></span>

- [<span data-ttu-id="a322f-113">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="a322f-113">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="a322f-114">Oracles. StateOracle</span><span class="sxs-lookup"><span data-stu-id="a322f-114">Microsoft.Quantum.Oracles.StateOracle</span></span>](xref:Microsoft.Quantum.Oracles.StateOracle)