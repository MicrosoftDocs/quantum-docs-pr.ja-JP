---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: MeasureInteger 演算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720967"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="4fb77-102">MeasureInteger 演算</span><span class="sxs-lookup"><span data-stu-id="4fb77-102">MeasureInteger operation</span></span>

<span data-ttu-id="4fb77-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4fb77-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4fb77-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fb77-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fb77-105">クォンタムレジスタの内容を測定し、整数に変換します。</span><span class="sxs-lookup"><span data-stu-id="4fb77-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="4fb77-106">測定は、標準の計算基準 (つまり、の eigenbasis) に対して実行され `PauliZ` ます。</span><span class="sxs-lookup"><span data-stu-id="4fb77-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="4fb77-107">入力</span><span class="sxs-lookup"><span data-stu-id="4fb77-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="4fb77-108">ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4fb77-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4fb77-109">リトルエンディアンエンコーディングでのクォンタムレジスタ。</span><span class="sxs-lookup"><span data-stu-id="4fb77-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="4fb77-110">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fb77-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4fb77-111">の測定値を格納する符号なし整数 `target` 。</span><span class="sxs-lookup"><span data-stu-id="4fb77-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4fb77-112">解説</span><span class="sxs-lookup"><span data-stu-id="4fb77-112">Remarks</span></span>

<span data-ttu-id="4fb77-113">この操作では、入力レジスタが $ \ket{00\cdots 0} $ 状態にリセットされ、ターゲットコンピューターへの解放に適しています。</span><span class="sxs-lookup"><span data-stu-id="4fb77-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="4fb77-114">参照</span><span class="sxs-lookup"><span data-stu-id="4fb77-114">See Also</span></span>

- [<span data-ttu-id="4fb77-115">Microsoft...。</span><span class="sxs-lookup"><span data-stu-id="4fb77-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)