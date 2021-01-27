---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLECA
title: ApplyLEOperationOnPhaseLECA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLECA
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 024eb923d8e09ecb75a95dd61d300fd0d643c7ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843751"
---
# <a name="applyleoperationonphaseleca-operation"></a><span data-ttu-id="de40e-102">ApplyLEOperationOnPhaseLECA 操作</span><span class="sxs-lookup"><span data-stu-id="de40e-102">ApplyLEOperationOnPhaseLECA operation</span></span>

<span data-ttu-id="de40e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="de40e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="de40e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de40e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de40e-105"><xref:microsoft.quantum.arithmetic.phaselittleendian>型のターゲットレジスタに対してレジスタを入力として受け取る操作を適用 <xref:microsoft.quantum.arithmetic.littleendian> します。</span><span class="sxs-lookup"><span data-stu-id="de40e-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLECA (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="de40e-106">入力</span><span class="sxs-lookup"><span data-stu-id="de40e-106">Input</span></span>

### <a name="op--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="de40e-107">op: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="de40e-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="de40e-108">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="de40e-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="de40e-109">ターゲット: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="de40e-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="de40e-110">操作が適用されるレジスタ。</span><span class="sxs-lookup"><span data-stu-id="de40e-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de40e-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de40e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="de40e-112">解説</span><span class="sxs-lookup"><span data-stu-id="de40e-112">Remarks</span></span>

<span data-ttu-id="de40e-113">レジスタは、を使用することによってに変換され、その後、 `LittleEndian` <xref:microsoft.quantum.canon.qftle> の適用後に元の表現に戻され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="de40e-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="de40e-114">参照</span><span class="sxs-lookup"><span data-stu-id="de40e-114">See Also</span></span>

- [<span data-ttu-id="de40e-115">Microsoft. ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="de40e-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="de40e-116">Microsoft. ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="de40e-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="de40e-117">Microsoft. ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="de40e-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)