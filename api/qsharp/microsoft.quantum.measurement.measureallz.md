---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854668"
---
# <a name="measureallz-operation"></a><span data-ttu-id="7db63-102">MeasureAllZ 操作</span><span class="sxs-lookup"><span data-stu-id="7db63-102">MeasureAllZ operation</span></span>

<span data-ttu-id="7db63-103">名前空間: [Microsoft Quantum](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="7db63-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="7db63-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7db63-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7db63-105">によって、レジスタの qubits が Pに評価されます。</span><span class="sxs-lookup"><span data-stu-id="7db63-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="7db63-106">説明</span><span class="sxs-lookup"><span data-stu-id="7db63-106">Description</span></span>

<span data-ttu-id="7db63-107">は、レジスタ全体のパリティを表すために、$Z/otimes z ~ otimes/cドット/otimes Z $ ベースで qubits のレジスタを測定します。</span><span class="sxs-lookup"><span data-stu-id="7db63-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="7db63-108">入力</span><span class="sxs-lookup"><span data-stu-id="7db63-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="7db63-109">register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7db63-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="7db63-110">測定するレジスタ。</span><span class="sxs-lookup"><span data-stu-id="7db63-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="7db63-111">出力:__無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7db63-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="7db63-112">$Z/otimes z/otimes-cドット/otimes Z $ の測定結果。</span><span class="sxs-lookup"><span data-stu-id="7db63-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>