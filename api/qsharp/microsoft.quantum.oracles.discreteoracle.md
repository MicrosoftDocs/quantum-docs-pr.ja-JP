---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842567"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="5d534-102">DiscreteOracle ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="5d534-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="5d534-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5d534-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5d534-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d534-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d534-105">不連続タイム oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="5d534-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="5d534-106">これは $U ^ m $ を実装する oracle で、$ と負でない整数 $m $ $U 固定操作に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5d534-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

