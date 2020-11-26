---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 4faaf78f24fa28ae5e4f701b80d9297c910b975e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194221"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="7e7f5-102">MeasurePaulis 操作</span><span class="sxs-lookup"><span data-stu-id="7e7f5-102">MeasurePaulis operation</span></span>

<span data-ttu-id="7e7f5-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="7e7f5-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="7e7f5-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7e7f5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7e7f5-105">複数のマルチビット演算子の配列を指定すると、指定された測定ガジェットを使用してそれぞれを測定し、結果の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="7e7f5-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="7e7f5-106">入力</span><span class="sxs-lookup"><span data-stu-id="7e7f5-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="7e7f5-107">paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="7e7f5-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="7e7f5-108">測定するマルチ qubit の演算子の配列。</span><span class="sxs-lookup"><span data-stu-id="7e7f5-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="7e7f5-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7e7f5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7e7f5-110">指定された演算子を測定するための登録です。</span><span class="sxs-lookup"><span data-stu-id="7e7f5-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="7e7f5-111">ガジェット: ([p、li](xref:microsoft.quantum.lang-ref.pauli)[]、[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) =__無効 <Result>__></span><span class="sxs-lookup"><span data-stu-id="7e7f5-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="7e7f5-112">指定されたマルチ qubit 演算子の測定値を実行する演算。</span><span class="sxs-lookup"><span data-stu-id="7e7f5-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7e7f5-113">出力:__無効 <Result> な__[]</span><span class="sxs-lookup"><span data-stu-id="7e7f5-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="7e7f5-114">の各要素を測定して取得した結果の配列 `paulis` `target` 。</span><span class="sxs-lookup"><span data-stu-id="7e7f5-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>