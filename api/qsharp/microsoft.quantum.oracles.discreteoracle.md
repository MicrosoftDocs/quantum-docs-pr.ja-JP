---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724926"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="2d71c-102">DiscreteOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="2d71c-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="2d71c-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="2d71c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="2d71c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2d71c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2d71c-105">不連続タイム oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="2d71c-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="2d71c-106">これは $U ^ m $ を実装する oracle で、$ と負でない整数 $m $ $U 固定操作に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2d71c-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

