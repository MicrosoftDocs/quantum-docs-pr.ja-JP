---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226657"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="c8ff9-102">ReflectionOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="c8ff9-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="c8ff9-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c8ff9-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c8ff9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8ff9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c8ff9-105">リフレクション oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="c8ff9-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="c8ff9-106">リフレクション oracle ($O $) には、次の入力があります。</span><span class="sxs-lookup"><span data-stu-id="c8ff9-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="c8ff9-107">反映されたサブ空間の回転に使用するフェーズ $/phi $。</span><span class="sxs-lookup"><span data-stu-id="c8ff9-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="c8ff9-108">指定されたリフレクションを実行する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="c8ff9-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="c8ff9-109">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="c8ff9-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="c8ff9-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="c8ff9-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="c8ff9-111">解説</span><span class="sxs-lookup"><span data-stu-id="c8ff9-111">Remarks</span></span>

<span data-ttu-id="c8ff9-112">この oracle $O = \ bold 完了-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ は、単一の純粋な状態 $ \ket{\psi} $ について、フェーズ $ \ phi $ によって部分的なリフレクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8ff9-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>