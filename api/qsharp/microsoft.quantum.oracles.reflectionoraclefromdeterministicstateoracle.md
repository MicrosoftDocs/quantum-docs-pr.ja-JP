---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842521"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="9e38b-102">ReflectionOracleFromDeterministicStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="9e38b-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="9e38b-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="9e38b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="9e38b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e38b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e38b-105">Oracle から特定の状態に関するリフレクションを構築します。</span><span class="sxs-lookup"><span data-stu-id="9e38b-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="9e38b-106">説明</span><span class="sxs-lookup"><span data-stu-id="9e38b-106">Description</span></span>

<span data-ttu-id="9e38b-107">配列 $O によって表される決定的な状態準備 oracle があるとします。この関数の結果は oracle で、oracle $O $; によって準備された状態 $ \ket{\psi} $ の周りにリフレクションが適用されます。つまり、$ \ket{\psi} $ という状態で、\ket {0} = \ket{\psi} $ という $O ます。</span><span class="sxs-lookup"><span data-stu-id="9e38b-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="9e38b-108">入力</span><span class="sxs-lookup"><span data-stu-id="9e38b-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="9e38b-109">oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="9e38b-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="9e38b-110">$ \Ket{\psi} $ の状態のコピーを準備する oracle。</span><span class="sxs-lookup"><span data-stu-id="9e38b-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="9e38b-111">出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="9e38b-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="9e38b-112">状態 $ \ket{\psi} $ を反映する oracle。</span><span class="sxs-lookup"><span data-stu-id="9e38b-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e38b-113">参照</span><span class="sxs-lookup"><span data-stu-id="9e38b-113">See Also</span></span>

- [<span data-ttu-id="9e38b-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="9e38b-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="9e38b-115">Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="9e38b-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)