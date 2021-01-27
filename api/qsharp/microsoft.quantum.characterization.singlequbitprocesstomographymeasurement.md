---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 演算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839651"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>SingleQubitProcessTomographyMeasurement 演算

名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


特定の目的のチャネルを指定して、tomography の単一の qubit プロセス測定を実行します。

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>入力

### <a name="preparation--pauli"></a>準備: [P# li](xref:microsoft.quantum.lang-ref.pauli)

$P $ で、qubit を準備する必要があります。


### <a name="measurement--pauli"></a>測定: [P# li](xref:microsoft.quantum.lang-ref.pauli)

要素 $Q $ で、qubit が測定されます。


### <a name="channel--qubit--unit"></a>channel: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit) 

プロセス tomography で動作が推定される1つの qubit チャネル $ \ ラムダ $。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

`Zero`確率が $ $ \Begin{align} \ Pr (\texttt{Zero} | \ ラムダ; の結果P, Q) = \ 演算子名 {\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \ right] \ right)。
\end{align} $ $

## <a name="remarks"></a>解説

この操作によって返される結果に対する分布は、2つの qubit 状態 tomography の特殊なケースです。 $ \Rho = J (\ ラムダ)/$2 を $ \ Lambda $ の Jamiłkowski 状態にします。 次に、上記の分布は $ $ \begin{align}/Pr (\texttt{Zero} | \rho; と同じになります。M) = \ 演算子 name{tr} (M \rho)、\end{align} $ $ where $M = 2 (\ bold done + P) ^ \mathrm{T}/2 \ cdot (\ done + Q)/$2 は、$P $ および $Q $ に対応する有効な測定値です。