---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720326"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="88b56-102">MeasureWithScratch 操作</span><span class="sxs-lookup"><span data-stu-id="88b56-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="88b56-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="88b56-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="88b56-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88b56-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88b56-105">明示的なスクラッチ qubit を使用して測定を実行し、指定された Pan Li 演算子を測定します。</span><span class="sxs-lookup"><span data-stu-id="88b56-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="88b56-106">入力</span><span class="sxs-lookup"><span data-stu-id="88b56-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="88b56-107">[p# li []](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="88b56-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="88b56-108">シングル qubit の P# li 演算子の配列として指定されたマルチ qubit の Pan Li 演算子。</span><span class="sxs-lookup"><span data-stu-id="88b56-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="88b56-109">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="88b56-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="88b56-110">測定する qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="88b56-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="88b56-111">出力: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="88b56-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="88b56-112">レジスタに対して指定された P# li 演算子を測定した結果 `target` 。</span><span class="sxs-lookup"><span data-stu-id="88b56-112">The result of measuring the given Pauli operator on the `target` register.</span></span>