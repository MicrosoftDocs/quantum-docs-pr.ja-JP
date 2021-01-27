---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839672"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="4a0ac-102">QuantumPhaseEstimation 操作</span><span class="sxs-lookup"><span data-stu-id="4a0ac-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="4a0ac-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="4a0ac-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="4a0ac-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4a0ac-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4a0ac-105">指定された oracle に対してクォンタムフェーズ推定アルゴリズムを実行し `U` `targetState` 、フェーズをビッグエンディアンクォンタムレジスタに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4a0ac-106">入力</span><span class="sxs-lookup"><span data-stu-id="4a0ac-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="4a0ac-107">oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="4a0ac-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="4a0ac-108">指定された整数の $U ^ m $ を実装する操作は、m を累乗します。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="4a0ac-109">targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4a0ac-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4a0ac-110">$U $ によって操作された状態 $ \ket{\phi} $ を表すクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="4a0ac-111">$ \Ket{\phi} $ が $U $ の eigenstate の場合、$U \ket{\phi} = e ^ {i\ phi} \ket{\phi} $ for $ \ phi \ in [0, 2 \ pi) $ 不明なフェーズです。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="4a0ac-112">controlRegister: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="4a0ac-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="4a0ac-113">指定された oracle の制御に使用できるビッグエンディアン表現整数レジスタ。このレジスタには、この操作の適用後に $ + phi $ の表現が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="4a0ac-114">ControlRegister は初期状態 $ \ket{00\cdots 0} $ で開始することを前提としています。レジスタの長さは、必要な有効桁数を示しています。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4a0ac-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a0ac-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

