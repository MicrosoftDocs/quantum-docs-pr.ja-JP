---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226793"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="0bc5a-102">ContinuousOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="0bc5a-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="0bc5a-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="0bc5a-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="0bc5a-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0bc5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0bc5a-105">連続した oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="0bc5a-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="0bc5a-106">これは、$U (\ delta t): \ket{\psi (t)} \ map\ket{\psi (t +-delta t)} $ を実装する oracle で、$ のすべての $t 時刻に対して $U $ は固定された操作で、$ \ delta t $ は負でない実数です。</span><span class="sxs-lookup"><span data-stu-id="0bc5a-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

