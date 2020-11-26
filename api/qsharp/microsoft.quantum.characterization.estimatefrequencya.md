---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204353"
---
# <a name="estimatefrequencya-operation"></a>EstimateFrequencyA 操作

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Adjointable と測定値の準備を行うと、は、 `Zero` 指定された数の試行を実行して、その測定が成功する頻度 (を返します) を推定します。

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>入力

### <a name="preparation--qubit--unit--is-adj"></a>準備: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞

入力レジスタに指定された状態 $ \rho $ を準備する adjointable 操作 ($ $P)。


### <a name="measurement--qubit--__invalidresult__"></a>測定値: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] =__無効 <Result>__> 

対象の測定値を表す $ $M 演算。


### <a name="nqubits--int"></a>nQubits: [Int](xref:microsoft.quantum.lang-ref.int)

準備と測定がそれぞれ作用する qubits の数。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

対象の頻度を推定するために測定を実行する回数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

\Hat{p} (P (\ket{00 \ ドット 0} \bra{00 \) $) $ が返さ $M れる頻度の推定 $ $ は、 `Zero` バイアスをかける二項分出し $ \hat{p} = n \_ {\uparrow}/n {\text{measurements}} $ を使用して取得し \_ ます。ここで、$n \_ {\uparrow} $ は観測された結果の数です `Zero` 。

## <a name="remarks"></a>解説

Adjointable 操作の場合、操作の呼び出しなどの特定の仮定を行うと、qubits がまったく同じ状態になるように準備することができます。これにより、ターゲットマシンでパフォーマンスを最適化することができます。