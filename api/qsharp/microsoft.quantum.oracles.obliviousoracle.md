---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842561"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="06a58-102">ObliviousOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="06a58-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="06a58-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="06a58-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="06a58-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06a58-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06a58-105">Oracle for 無関係の振幅増幅を表します。</span><span class="sxs-lookup"><span data-stu-id="06a58-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="06a58-106">Oracle $O $ への入力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06a58-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="06a58-107">$ Act $O ancilla register $a $。</span><span class="sxs-lookup"><span data-stu-id="06a58-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="06a58-108">システム登録 $s $ は、必要な $U $ が適用され、レジスタ $a $ が状態 $ \ket{t} a $ にあることを示しています \_ 。</span><span class="sxs-lookup"><span data-stu-id="06a58-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="06a58-109">解説</span><span class="sxs-lookup"><span data-stu-id="06a58-109">Remarks</span></span>

<span data-ttu-id="06a58-110">この oracle で定義されている $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \ ラムダ | ^ 2} \ket{t ^ \ perp} \_ a\ cドット $ $ \_ \ket{t} a $ でフラグが設定されたベースで、任意のシステム状態 $ \ket{\psi} s $ に対して、ancilla state $ \ket{s} a $ を使用して、任意のシステム状態 $ s \_ $ に対し \_ て、を実装します。 $U</span><span class="sxs-lookup"><span data-stu-id="06a58-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="06a58-111">最初のパラメーターは、$ \ket{s} a $ の qubit レジスタです \_ 。</span><span class="sxs-lookup"><span data-stu-id="06a58-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="06a58-112">2番目のパラメーターは、$ \ket{\psi} s $ の qubit レジスタです \_ 。</span><span class="sxs-lookup"><span data-stu-id="06a58-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>