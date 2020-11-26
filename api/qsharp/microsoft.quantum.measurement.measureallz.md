---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 6c44ab6a7983697644071f0e3cf106e9825661ee
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227082"
---
# <a name="measureallz-operation"></a><span data-ttu-id="dbd43-102">MeasureAllZ 操作</span><span class="sxs-lookup"><span data-stu-id="dbd43-102">MeasureAllZ operation</span></span>

<span data-ttu-id="dbd43-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="dbd43-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="dbd43-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dbd43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dbd43-105">によって、レジスタの qubits が Pに評価されます。</span><span class="sxs-lookup"><span data-stu-id="dbd43-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="dbd43-106">説明</span><span class="sxs-lookup"><span data-stu-id="dbd43-106">Description</span></span>

<span data-ttu-id="dbd43-107">は、レジスタ全体のパリティを表すために、$Z/otimes z ~ otimes/cドット/otimes Z $ ベースで qubits のレジスタを測定します。</span><span class="sxs-lookup"><span data-stu-id="dbd43-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="dbd43-108">入力</span><span class="sxs-lookup"><span data-stu-id="dbd43-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="dbd43-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="dbd43-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="dbd43-110">測定するレジスタ。</span><span class="sxs-lookup"><span data-stu-id="dbd43-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="dbd43-111">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="dbd43-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="dbd43-112">$Z/otimes z/otimes-cドット/otimes Z $ の測定結果。</span><span class="sxs-lookup"><span data-stu-id="dbd43-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>