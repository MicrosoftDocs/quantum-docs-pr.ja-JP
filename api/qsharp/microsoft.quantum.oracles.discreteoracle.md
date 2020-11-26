---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: accbd7b88cc2f6522da20ec1959492310ff0e743
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193898"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="8b883-102">DiscreteOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="8b883-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="8b883-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="8b883-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="8b883-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b883-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b883-105">不連続タイム oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="8b883-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="8b883-106">これは $U ^ m $ を実装する oracle で、$ と負でない整数 $m $ $U 固定操作に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8b883-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

