---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: ApplyPhaseLEOperationOnLE 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721550"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="fe4cb-102">ApplyPhaseLEOperationOnLE 操作</span><span class="sxs-lookup"><span data-stu-id="fe4cb-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="fe4cb-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="fe4cb-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="fe4cb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe4cb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe4cb-105"><xref:microsoft.quantum.arithmetic.littleendian>型のターゲットレジスタに対してレジスタを入力として受け取る操作を適用 <xref:microsoft.quantum.arithmetic.phaselittleendian> します。</span><span class="sxs-lookup"><span data-stu-id="fe4cb-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="fe4cb-106">入力</span><span class="sxs-lookup"><span data-stu-id="fe4cb-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="fe4cb-107">op: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe4cb-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fe4cb-108">適用する操作。</span><span class="sxs-lookup"><span data-stu-id="fe4cb-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="fe4cb-109">ターゲット: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fe4cb-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fe4cb-110">操作が適用されるレジスタ。</span><span class="sxs-lookup"><span data-stu-id="fe4cb-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fe4cb-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fe4cb-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="fe4cb-112">解説</span><span class="sxs-lookup"><span data-stu-id="fe4cb-112">Remarks</span></span>

<span data-ttu-id="fe4cb-113">レジスタは、を使用することによってに変換され、その後、 `PhaseLittleEndian` <xref:microsoft.quantum.canon.qftle> の適用後に元の表現に戻され `op` ます。</span><span class="sxs-lookup"><span data-stu-id="fe4cb-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe4cb-114">参照</span><span class="sxs-lookup"><span data-stu-id="fe4cb-114">See Also</span></span>

- [<span data-ttu-id="fe4cb-115">Microsoft. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="fe4cb-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="fe4cb-116">Microsoft. ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="fe4cb-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="fe4cb-117">Microsoft. ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="fe4cb-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)