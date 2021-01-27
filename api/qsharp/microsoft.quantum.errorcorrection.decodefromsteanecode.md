---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827387"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="7830c-102">DecodeFromSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="7830c-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="7830c-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7830c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7830c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7830c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7830c-105">エンコードされていないクォンタムレジスタを⟦7、1、3⟧ Steane 量子コードでエンコードされたクォンタムレジスタにマップする逆エンコード操作。</span><span class="sxs-lookup"><span data-stu-id="7830c-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="7830c-106">入力</span><span class="sxs-lookup"><span data-stu-id="7830c-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="7830c-107">logicalRegister: [Logicalregister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="7830c-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="7830c-108">エンコードされた 5-qubits コードの論理状態を表す qubits の配列。</span><span class="sxs-lookup"><span data-stu-id="7830c-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="7830c-109">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span><span class="sxs-lookup"><span data-stu-id="7830c-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="7830c-110">2番目のパラメーターの補助 qubit と共に、最初のパラメーターのエンコードされていない状態を表す、値1の qubit 配列。</span><span class="sxs-lookup"><span data-stu-id="7830c-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="7830c-111">解説</span><span class="sxs-lookup"><span data-stu-id="7830c-111">Remarks</span></span>

<span data-ttu-id="7830c-112">選択したデコーダーは、⟦7、1、3⟧ Steane code の CSS コードプロパティを使用します。つまり、X エラーと Z エラーを個別に修正します。</span><span class="sxs-lookup"><span data-stu-id="7830c-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="7830c-113">コードのプロパティとして、X の位置 (それぞれ、適用される Z 補正) は X の3ビットエンコーディング、それぞれ Z より隣人は整数であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="7830c-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="7830c-114">References</span><span class="sxs-lookup"><span data-stu-id="7830c-114">References</span></span>

- <span data-ttu-id="7830c-115">D.</span><span class="sxs-lookup"><span data-stu-id="7830c-115">D.</span></span> <span data-ttu-id="7830c-116">Gottesman、"安定板のコードとクォンタムのエラーの修正" 博士、Thesis、Caltech、1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="7830c-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="7830c-117">参照</span><span class="sxs-lookup"><span data-stu-id="7830c-117">See Also</span></span>

- [<span data-ttu-id="7830c-118">SteaneCodeEncoder を修正します。</span><span class="sxs-lookup"><span data-stu-id="7830c-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="7830c-119">SteaneCodeDecoder を修正します。</span><span class="sxs-lookup"><span data-stu-id="7830c-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="7830c-120">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="7830c-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)