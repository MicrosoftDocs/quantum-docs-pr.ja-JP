---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724212"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="2934b-102">ReflectionOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="2934b-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="2934b-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="2934b-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="2934b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2934b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2934b-105">リフレクション oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="2934b-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="2934b-106">リフレクション oracle ($O $) には、次の入力があります。</span><span class="sxs-lookup"><span data-stu-id="2934b-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="2934b-107">反映されたサブ空間の回転に使用するフェーズ $/phi $。</span><span class="sxs-lookup"><span data-stu-id="2934b-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="2934b-108">指定されたリフレクションを実行する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="2934b-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="2934b-109">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="2934b-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="2934b-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞と Ctl</span><span class="sxs-lookup"><span data-stu-id="2934b-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="2934b-111">解説</span><span class="sxs-lookup"><span data-stu-id="2934b-111">Remarks</span></span>

<span data-ttu-id="2934b-112">この oracle $O = \ bold 完了-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ は、単一の純粋な状態 $ \ket{\psi} $ について、フェーズ $ \ phi $ によって部分的なリフレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="2934b-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>