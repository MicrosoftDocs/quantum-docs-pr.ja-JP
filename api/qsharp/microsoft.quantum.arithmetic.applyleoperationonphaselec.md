---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEC
title: ApplyLEOperationOnPhaseLEC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEC
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: dafe27f66f967fb641a8898672e124c0a51fe687
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190838"
---
# <a name="applyleoperationonphaselec-operation"></a><span data-ttu-id="b0b46-102">ApplyLEOperationOnPhaseLEC 操作</span><span class="sxs-lookup"><span data-stu-id="b0b46-102">ApplyLEOperationOnPhaseLEC operation</span></span>

<span data-ttu-id="b0b46-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b0b46-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b0b46-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b0b46-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b0b46-105"><xref:microsoft.quantum.arithmetic.phaselittleendian>型のターゲットレジスタに対してレジスタを入力として受け取る操作を適用 <xref:microsoft.quantum.arithmetic.littleendian> します。</span><span class="sxs-lookup"><span data-stu-id="b0b46-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="b0b46-106">入力</span><span class="sxs-lookup"><span data-stu-id="b0b46-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="b0b46-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は Ctl です</span><span class="sxs-lookup"><span data-stu-id="b0b46-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b0b46-108">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="b0b46-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="b0b46-109">ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b0b46-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="b0b46-110">操作が適用されるレジスタ。</span><span class="sxs-lookup"><span data-stu-id="b0b46-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b0b46-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b0b46-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b0b46-112">解説</span><span class="sxs-lookup"><span data-stu-id="b0b46-112">Remarks</span></span>

<span data-ttu-id="b0b46-113">レジスタは、を使用することによってに変換され、その後、 `LittleEndian` <xref:microsoft.quantum.canon.qftle> の適用後に元の表現に戻され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="b0b46-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0b46-114">参照</span><span class="sxs-lookup"><span data-stu-id="b0b46-114">See Also</span></span>

- [<span data-ttu-id="b0b46-115">Microsoft. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="b0b46-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="b0b46-116">Microsoft. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="b0b46-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="b0b46-117">Microsoft. ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="b0b46-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)