---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: SingleQubitProcessTomographyMeasurement 演算
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 3756040df8e34ecee1e968428b08387e0096ab7b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204200"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="a4190-102">SingleQubitProcessTomographyMeasurement 演算</span><span class="sxs-lookup"><span data-stu-id="a4190-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="a4190-103">名前空間: [Microsoft. 量子. 特性](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="a4190-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="a4190-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4190-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4190-105">特定の目的のチャネルを指定して、tomography の単一の qubit プロセス測定を実行します。</span><span class="sxs-lookup"><span data-stu-id="a4190-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="a4190-106">入力</span><span class="sxs-lookup"><span data-stu-id="a4190-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="a4190-107">準備: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a4190-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a4190-108">$P $ で、qubit を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4190-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="a4190-109">測定: [P# li](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="a4190-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="a4190-110">要素 $Q $ で、qubit が測定されます。</span><span class="sxs-lookup"><span data-stu-id="a4190-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="a4190-111">channel: [qubit](xref:microsoft.quantum.lang-ref.qubit) => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4190-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a4190-112">プロセス tomography で動作が推定される1つの qubit チャネル $ \ ラムダ $。</span><span class="sxs-lookup"><span data-stu-id="a4190-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="a4190-113">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a4190-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="a4190-114">`Zero`確率が $ $ \Begin{align} \ Pr (\texttt{Zero} | \ ラムダ; の結果P, Q) = \ 演算子名 {\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \ right] \ right)。</span><span class="sxs-lookup"><span data-stu-id="a4190-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="a4190-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="a4190-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="a4190-116">解説</span><span class="sxs-lookup"><span data-stu-id="a4190-116">Remarks</span></span>

<span data-ttu-id="a4190-117">この操作によって返される結果に対する分布は、2つの qubit 状態 tomography の特殊なケースです。</span><span class="sxs-lookup"><span data-stu-id="a4190-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="a4190-118">$ \Rho = J (\ ラムダ)/$2 を $ \ Lambda $ の Jamiłkowski 状態にします。</span><span class="sxs-lookup"><span data-stu-id="a4190-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="a4190-119">次に、上記の分布は $ $ \begin{align}/Pr (\texttt{Zero} | \rho; と同じになります。M) = \ 演算子 name{tr} (M \rho)、\end{align} $ $ where $M = 2 (\ bold done + P) ^ \mathrm{T}/2 \ cdot (\ done + Q)/$2 は、$P $ および $Q $ に対応する有効な測定値です。</span><span class="sxs-lookup"><span data-stu-id="a4190-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>