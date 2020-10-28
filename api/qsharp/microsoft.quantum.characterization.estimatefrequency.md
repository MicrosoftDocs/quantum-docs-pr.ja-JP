---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715085"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パック [](https://nuget.org/packages/)


準備と測定値を指定すると、指定された数の試行回数を実行することで、測定が成功する頻度 (を返します) を推定し `Zero` ます。

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>入力

### <a name="preparation--qubit--unit"></a>準備: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

入力レジスタに特定の状態 $ \rho $ を準備する、$ $P の操作。


### <a name="measurement--qubit--__invalidresult__"></a>測定値: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = __無効 <Result>__ > 

対象の測定値を表す $ $M 演算。


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

準備と測定がそれぞれ作用する qubits の数。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

対象の頻度を推定するために測定を実行する回数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

\Hat{p} (P (\ket{00 \ ドット 0} \bra{00 \) $) $ が返さ $M れる頻度の推定 $ $ は、 `Zero` バイアスをかける二項分出し $ \hat{p} = n \_ {\uparrow}/n {\text{measurements}} $ を使用して取得し \_ ます。ここで、$n \_ {\uparrow} $ は観測された結果の数です `Zero` 。

これは、物理的な制限を尊重するターゲットコンピューターでは特に重要であり、確率を測定できないようにします。