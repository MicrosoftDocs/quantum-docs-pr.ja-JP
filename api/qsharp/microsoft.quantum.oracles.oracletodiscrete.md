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
# <a name="oracletodiscrete-function"></a>OracleToDiscrete 関数

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


"ブラックボックス" oracle を表す操作が指定された場合、は、"ブラックボックス" の oracle が複数回繰り返されている不連続タイム oracle を返します。

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>入力

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

累乗する操作。



## <a name="output--discreteoracle"></a>出力: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

"ブラックボックス" oracle に部分的に適用された操作で、離散タイム oracle を表します。

## <a name="example"></a>例

`OracleToDiscrete(U)(3, target)` は、3回繰り返されると同じです `U(target)` 。