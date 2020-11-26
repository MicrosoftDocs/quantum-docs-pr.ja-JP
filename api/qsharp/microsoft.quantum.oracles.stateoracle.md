---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226606"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="8d1fe-102">StateOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="8d1fe-102">StateOracle user defined type</span></span>

<span data-ttu-id="8d1fe-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="8d1fe-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="8d1fe-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d1fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d1fe-105">状態の準備のための oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="8d1fe-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="8d1fe-106">Oracle $O $ への入力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8d1fe-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="8d1fe-107">フラグ qubit $f $ にインデックスを付ける整数。</span><span class="sxs-lookup"><span data-stu-id="8d1fe-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="8d1fe-108">必要なクォンタムの状態 $ \ket{\psi} s $ を格納する $s $ がシステムに登録され \_ ます。</span><span class="sxs-lookup"><span data-stu-id="8d1fe-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="8d1fe-109">解説</span><span class="sxs-lookup"><span data-stu-id="8d1fe-109">Remarks</span></span>

<span data-ttu-id="8d1fe-110">$ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \ ラムダ | ^ 2} \ket fcドット $ $ によって定義されているこの oracle {0} \_ は、計算ベースの状態 $ \ket {0} \_ {f} \ket s $ を使用して、 {0} \_ \_ $ \ket{\psi} {1} f $ によってフラグが設定されたターゲットの状態 $ \ket s $ \_</span><span class="sxs-lookup"><span data-stu-id="8d1fe-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="8d1fe-111">最初のパラメーターは、$ \ket f $ の qubit レジスタのインデックスです {0} \_ 。</span><span class="sxs-lookup"><span data-stu-id="8d1fe-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="8d1fe-112">2番目のパラメーターには、両方のレジスタがあります。</span><span class="sxs-lookup"><span data-stu-id="8d1fe-112">The second parameter encompassed both registers.</span></span>