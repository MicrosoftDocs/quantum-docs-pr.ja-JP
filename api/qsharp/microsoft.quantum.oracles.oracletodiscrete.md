---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724245"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="31a63-102">OracleToDiscrete 関数</span><span class="sxs-lookup"><span data-stu-id="31a63-102">OracleToDiscrete function</span></span>

<span data-ttu-id="31a63-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="31a63-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="31a63-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31a63-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31a63-105">"ブラックボックス" oracle を表す操作が指定された場合、は、"ブラックボックス" の oracle が複数回繰り返されている不連続タイム oracle を返します。</span><span class="sxs-lookup"><span data-stu-id="31a63-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="31a63-106">入力</span><span class="sxs-lookup"><span data-stu-id="31a63-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="31a63-107">blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞と Ctl</span><span class="sxs-lookup"><span data-stu-id="31a63-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="31a63-108">累乗する操作。</span><span class="sxs-lookup"><span data-stu-id="31a63-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="31a63-109">出力: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="31a63-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="31a63-110">"ブラックボックス" oracle に部分的に適用された操作で、離散タイム oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="31a63-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>