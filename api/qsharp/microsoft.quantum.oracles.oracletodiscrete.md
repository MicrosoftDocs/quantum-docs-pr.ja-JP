---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842535"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="b2025-102">OracleToDiscrete 関数</span><span class="sxs-lookup"><span data-stu-id="b2025-102">OracleToDiscrete function</span></span>

<span data-ttu-id="b2025-103">名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="b2025-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="b2025-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2025-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2025-105">"ブラックボックス" oracle を表す操作が指定された場合、は、"ブラックボックス" の oracle が複数回繰り返されている不連続タイム oracle を返します。</span><span class="sxs-lookup"><span data-stu-id="b2025-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="b2025-106">入力</span><span class="sxs-lookup"><span data-stu-id="b2025-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="b2025-107">blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="b2025-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b2025-108">累乗する操作。</span><span class="sxs-lookup"><span data-stu-id="b2025-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="b2025-109">出力: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="b2025-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="b2025-110">"ブラックボックス" oracle に部分的に適用された操作で、離散タイム oracle を表します。</span><span class="sxs-lookup"><span data-stu-id="b2025-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="b2025-111">例</span><span class="sxs-lookup"><span data-stu-id="b2025-111">Example</span></span>

<span data-ttu-id="b2025-112">`OracleToDiscrete(U)(3, target)` は、3回繰り返されると同じです `U(target)` 。</span><span class="sxs-lookup"><span data-stu-id="b2025-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>