---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: c90eac291ebe718d10377399184ad705bb51673e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824691"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="8b19c-102">SteaneCodeRecoveryX 関数</span><span class="sxs-lookup"><span data-stu-id="8b19c-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="8b19c-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8b19c-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8b19c-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b19c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b19c-105">⟦7、1、3⟧ Steane 量子コードの安定板グループの X 部分のデコーダー。</span><span class="sxs-lookup"><span data-stu-id="8b19c-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="8b19c-106">入力</span><span class="sxs-lookup"><span data-stu-id="8b19c-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="8b19c-107">より隣人: [より隣人](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="8b19c-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="8b19c-108">安定板の X 部を測定して取得したより隣人配列。</span><span class="sxs-lookup"><span data-stu-id="8b19c-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="8b19c-109">出力: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="8b19c-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="8b19c-110">エンコードされたクォンタムシステムに適用されるときに、に対応するエラーを修正する、Pan Li 操作の配列 `syndrome` 。</span><span class="sxs-lookup"><span data-stu-id="8b19c-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="8b19c-111">解説</span><span class="sxs-lookup"><span data-stu-id="8b19c-111">Remarks</span></span>

<span data-ttu-id="8b19c-112">選択したデコーダーは、⟦7、1、3⟧ Steane code の CSS コードプロパティを使用します。つまり、X エラーと Z エラーを個別に修正します。</span><span class="sxs-lookup"><span data-stu-id="8b19c-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="8b19c-113">コードのプロパティとして、X の位置 (それぞれ、適用される Z 補正) は X の3ビットエンコーディング、それぞれ Z より隣人は整数であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="8b19c-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="8b19c-114">References</span><span class="sxs-lookup"><span data-stu-id="8b19c-114">References</span></span>

- <span data-ttu-id="8b19c-115">D.</span><span class="sxs-lookup"><span data-stu-id="8b19c-115">D.</span></span> <span data-ttu-id="8b19c-116">Gottesman、"安定板のコードとクォンタムのエラーの修正" 博士、Thesis、Caltech、1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="8b19c-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="8b19c-117">参照</span><span class="sxs-lookup"><span data-stu-id="8b19c-117">See Also</span></span>

- [<span data-ttu-id="8b19c-118">SteaneCodeRecoveryX を修正します。</span><span class="sxs-lookup"><span data-stu-id="8b19c-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="8b19c-119">SteaneCodeRecoveryFns を修正します。</span><span class="sxs-lookup"><span data-stu-id="8b19c-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)