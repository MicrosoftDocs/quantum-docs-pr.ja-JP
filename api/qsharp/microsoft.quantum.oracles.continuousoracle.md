---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724315"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="602a8-102">ContinuousOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="602a8-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="602a8-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="602a8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="602a8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="602a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="602a8-105">連続した oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="602a8-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="602a8-106">これは、$U (\ delta t): \ket{\psi (t)} \ map\ket{\psi (t +-delta t)} $ を実装する oracle で、$ のすべての $t 時刻に対して $U $ は固定された操作で、$ \ delta t $ は負でない実数です。</span><span class="sxs-lookup"><span data-stu-id="602a8-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

