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
# <a name="oracletodiscrete-function"></a>OracleToDiscrete 関数

名前空間: [Oracles](xref:Microsoft.Quantum.Oracles)

パック [](https://nuget.org/packages/)


"ブラックボックス" oracle を表す操作が指定された場合、は、"ブラックボックス" の oracle が複数回繰り返されている不連続タイム oracle を返します。

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>入力

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [ユニット](xref:microsoft.quantum.lang-ref.unit) の形容詞と Ctl

累乗する操作。



## <a name="output--discreteoracle"></a>出力: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

"ブラックボックス" oracle に部分的に適用された操作で、離散タイム oracle を表します。