---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: ApplyLEOperationOnPhaseLE 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 8c00890dea67e0beec356245e0794ee5ac697ada
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843788"
---
# <a name="applyleoperationonphasele-operation"></a><span data-ttu-id="eea94-102">ApplyLEOperationOnPhaseLE 操作</span><span class="sxs-lookup"><span data-stu-id="eea94-102">ApplyLEOperationOnPhaseLE operation</span></span>

<span data-ttu-id="eea94-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="eea94-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="eea94-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eea94-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eea94-105"><xref:microsoft.quantum.arithmetic.phaselittleendian>型のターゲットレジスタに対してレジスタを入力として受け取る操作を適用 <xref:microsoft.quantum.arithmetic.littleendian> します。</span><span class="sxs-lookup"><span data-stu-id="eea94-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="eea94-106">入力</span><span class="sxs-lookup"><span data-stu-id="eea94-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="eea94-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eea94-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="eea94-108">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="eea94-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="eea94-109">ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="eea94-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="eea94-110">操作が適用されるレジスタ。</span><span class="sxs-lookup"><span data-stu-id="eea94-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eea94-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eea94-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eea94-112">解説</span><span class="sxs-lookup"><span data-stu-id="eea94-112">Remarks</span></span>

<span data-ttu-id="eea94-113">レジスタは、を使用することによってに変換され、その後、 `LittleEndian` <xref:microsoft.quantum.canon.qftle> の適用後に元の表現に戻され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="eea94-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="eea94-114">参照</span><span class="sxs-lookup"><span data-stu-id="eea94-114">See Also</span></span>

- [<span data-ttu-id="eea94-115">Microsoft. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="eea94-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="eea94-116">Microsoft. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="eea94-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="eea94-117">Microsoft. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="eea94-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)