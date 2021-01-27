---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842589"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="0ed93-102">DeterministicStateOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="0ed93-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="0ed93-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0ed93-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0ed93-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ed93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ed93-105">決定的な状態の準備のための oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="0ed93-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="0ed93-106">Oracle $O $ への入力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ed93-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="0ed93-107">目的のクォンタム状態 $ \ket{\psi} s $ を格納するレジスタ \_ 。</span><span class="sxs-lookup"><span data-stu-id="0ed93-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="0ed93-108">解説</span><span class="sxs-lookup"><span data-stu-id="0ed93-108">Remarks</span></span>

<span data-ttu-id="0ed93-109">$O \ket = \ket{\psi} $ によって定義されたこの oracle {0} は、コンピューティングベースの状態 $ \ket $ で動作し、 {0} 状態 $ \ket{\psi} $ を作成します。</span><span class="sxs-lookup"><span data-stu-id="0ed93-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="0ed93-110">最初のパラメーターは $ \ket{\psi} $ の qubit レジスタです。</span><span class="sxs-lookup"><span data-stu-id="0ed93-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>