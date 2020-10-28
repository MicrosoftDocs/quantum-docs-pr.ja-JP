---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: d003d83a84356ce52c5601135000813c7f119e4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721375"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="2747e-102">AssertPhaseLessThan 操作</span><span class="sxs-lookup"><span data-stu-id="2747e-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="2747e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2747e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2747e-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2747e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2747e-105">PhaseLittleEndian でエンコードされたが未満であることをアサート `number` `value` します。</span><span class="sxs-lookup"><span data-stu-id="2747e-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="2747e-106">入力</span><span class="sxs-lookup"><span data-stu-id="2747e-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2747e-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2747e-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2747e-108">`number` は、このより小さい必要があります。</span><span class="sxs-lookup"><span data-stu-id="2747e-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="2747e-109">数値: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2747e-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="2747e-110">と比較される符号なし整数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="2747e-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2747e-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2747e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2747e-112">解説</span><span class="sxs-lookup"><span data-stu-id="2747e-112">Remarks</span></span>

<span data-ttu-id="2747e-113">この操作の制御されたバージョンは、コントロールを無視します。</span><span class="sxs-lookup"><span data-stu-id="2747e-113">The controlled version of this operation ignores controls.</span></span>