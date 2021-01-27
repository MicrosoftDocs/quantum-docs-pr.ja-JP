---
uid: Microsoft.Quantum.Arithmetic.AssertPhaseLessThan
title: AssertPhaseLessThan 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertPhaseLessThan
qsharp.summary: Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.
ms.openlocfilehash: 7b7a4fea8973727da4dcab6f739c6db8da835a2f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843446"
---
# <a name="assertphaselessthan-operation"></a><span data-ttu-id="98e23-102">AssertPhaseLessThan 操作</span><span class="sxs-lookup"><span data-stu-id="98e23-102">AssertPhaseLessThan operation</span></span>

<span data-ttu-id="98e23-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="98e23-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="98e23-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="98e23-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="98e23-105">PhaseLittleEndian でエンコードされたが未満であることをアサート `number` `value` します。</span><span class="sxs-lookup"><span data-stu-id="98e23-105">Asserts that the `number` encoded in PhaseLittleEndian is less than `value`.</span></span>

```qsharp
operation AssertPhaseLessThan (value : Int, number : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="98e23-106">入力</span><span class="sxs-lookup"><span data-stu-id="98e23-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="98e23-107">値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="98e23-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="98e23-108">`number` は、このより小さい必要があります。</span><span class="sxs-lookup"><span data-stu-id="98e23-108">`number` must be less than this.</span></span>


### <a name="number--phaselittleendian"></a><span data-ttu-id="98e23-109">数値: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="98e23-109">number : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="98e23-110">と比較される符号なし整数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="98e23-110">Unsigned integer which is compared to `value`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="98e23-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="98e23-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="98e23-112">解説</span><span class="sxs-lookup"><span data-stu-id="98e23-112">Remarks</span></span>

<span data-ttu-id="98e23-113">この操作の制御されたバージョンは、コントロールを無視します。</span><span class="sxs-lookup"><span data-stu-id="98e23-113">The controlled version of this operation ignores controls.</span></span>