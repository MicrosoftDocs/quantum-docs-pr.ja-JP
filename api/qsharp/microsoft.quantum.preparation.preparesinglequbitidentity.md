---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856863"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="815a2-102">PrepareSingleQubitIdentity 操作</span><span class="sxs-lookup"><span data-stu-id="815a2-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="815a2-103">名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="815a2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="815a2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="815a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="815a2-105">下回っ混合状態で qubit を準備します。</span><span class="sxs-lookup"><span data-stu-id="815a2-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="815a2-106">Depolarizing channel $ $ \begin{align}/オメガ (\rho) \mathrel{を適用して、指定された qubit を $-bold done/$2 状態で準備します。 =} & lt ac {1} {4} \ sum_ {\ mu \ in \{ 0, 1, 2, 3 \} }-シグマ \_ {\rho} \_ ^ {-dagger}, \end{align} $ $ ここで、$ \rho \_ $ は混合状態を表す密度演算子で、$ $ は、混合の状態を表しています。 $i</span><span class="sxs-lookup"><span data-stu-id="815a2-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="815a2-107">入力</span><span class="sxs-lookup"><span data-stu-id="815a2-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="815a2-108">qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="815a2-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="815a2-109">上で説明した方法で状態を depolarized する qubit。</span><span class="sxs-lookup"><span data-stu-id="815a2-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="815a2-110">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="815a2-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="815a2-111">解説</span><span class="sxs-lookup"><span data-stu-id="815a2-111">Remarks</span></span>

<span data-ttu-id="815a2-112">混合状態 $ \ bold done/$2 では、この操作を状態に適用した結果を示していますが、この操作で行われたランダムな選択に対する期待値が暗黙的に記述されています。</span><span class="sxs-lookup"><span data-stu-id="815a2-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="815a2-113">したがって、1つのアプリケーションでは、この操作によって純粋な状態が純粋な状態にマップされますが、想定どおりに動作します。</span><span class="sxs-lookup"><span data-stu-id="815a2-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="815a2-114">具体的には、この操作をプロセス tomography で使用して、チャネルの *非 unital* コンポーネントを測定できます。</span><span class="sxs-lookup"><span data-stu-id="815a2-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>