---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: 09de63d615a4d80e2b59deeddc07567aefe7660e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193830"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a><span data-ttu-id="b423c-102">ReflectionOracleFromDeterministicStateOracle 関数</span><span class="sxs-lookup"><span data-stu-id="b423c-102">ReflectionOracleFromDeterministicStateOracle function</span></span>

<span data-ttu-id="b423c-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="b423c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="b423c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b423c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b423c-105">Oracle から特定の状態に関するリフレクションを構築します。</span><span class="sxs-lookup"><span data-stu-id="b423c-105">Constructs reflection about a given state from an oracle.</span></span>

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a><span data-ttu-id="b423c-106">説明</span><span class="sxs-lookup"><span data-stu-id="b423c-106">Description</span></span>

<span data-ttu-id="b423c-107">配列 $O によって表される決定的な状態準備 oracle があるとします。この関数の結果は oracle で、oracle $O $; によって準備された状態 $ \ket{\psi} $ の周りにリフレクションが適用されます。つまり、$ \ket{\psi} $ という状態で、\ket {0} = \ket{\psi} $ という $O ます。</span><span class="sxs-lookup"><span data-stu-id="b423c-107">Given a deterministic state preparation oracle represented by a unitary matrix $O$, the result of this function is an oracle that applies a reflection around the state $\ket{\psi}$ prepared by the oracle $O$; that is, the state $\ket{\psi}$ such that $O\ket{0} = \ket{\psi}$.</span></span>

## <a name="input"></a><span data-ttu-id="b423c-108">入力</span><span class="sxs-lookup"><span data-stu-id="b423c-108">Input</span></span>

### <a name="oracle--deterministicstateoracle"></a><span data-ttu-id="b423c-109">oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="b423c-109">oracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="b423c-110">$ \Ket{\psi} $ の状態のコピーを準備する oracle。</span><span class="sxs-lookup"><span data-stu-id="b423c-110">An oracle that prepares copies of the state $\ket{\psi}$.</span></span>



## <a name="output--reflectionoracle"></a><span data-ttu-id="b423c-111">出力: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="b423c-111">Output : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="b423c-112">状態 $ \ket{\psi} $ を反映する oracle。</span><span class="sxs-lookup"><span data-stu-id="b423c-112">An oracle that reflects about the state $\ket{\psi}$.</span></span>

## <a name="see-also"></a><span data-ttu-id="b423c-113">参照</span><span class="sxs-lookup"><span data-stu-id="b423c-113">See Also</span></span>

- [<span data-ttu-id="b423c-114">Oracles. DeterministicStateOracle</span><span class="sxs-lookup"><span data-stu-id="b423c-114">Microsoft.Quantum.Oracles.DeterministicStateOracle</span></span>](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [<span data-ttu-id="b423c-115">Oracles. ReflectionOracle</span><span class="sxs-lookup"><span data-stu-id="b423c-115">Microsoft.Quantum.Oracles.ReflectionOracle</span></span>](xref:Microsoft.Quantum.Oracles.ReflectionOracle)