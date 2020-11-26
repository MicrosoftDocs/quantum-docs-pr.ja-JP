---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193847"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="c5edd-102">OracleToDiscrete 関数</span><span class="sxs-lookup"><span data-stu-id="c5edd-102">OracleToDiscrete function</span></span>

<span data-ttu-id="c5edd-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c5edd-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c5edd-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5edd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5edd-105">"ブラックボックス" oracle を表す操作が指定された場合、は、"ブラックボックス" の oracle が複数回繰り返されている不連続タイム oracle を返します。</span><span class="sxs-lookup"><span data-stu-id="c5edd-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="c5edd-106">入力</span><span class="sxs-lookup"><span data-stu-id="c5edd-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="c5edd-107">blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="c5edd-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c5edd-108">累乗する操作。</span><span class="sxs-lookup"><span data-stu-id="c5edd-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="c5edd-109">出力: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="c5edd-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="c5edd-110">"ブラックボックス" oracle に部分的に適用された操作で、離散タイム oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="c5edd-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>