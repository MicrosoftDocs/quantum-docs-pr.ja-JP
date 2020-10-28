---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721382"
---
# <a name="assertmostsignificantbit-operation"></a><span data-ttu-id="39aea-102">AssertMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="39aea-102">AssertMostSignificantBit operation</span></span>

<span data-ttu-id="39aea-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="39aea-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="39aea-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39aea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39aea-105">符号なし整数を表す qubit レジスタの最上位の qubit が特定の状態であることをアサートします。</span><span class="sxs-lookup"><span data-stu-id="39aea-105">Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.</span></span>

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="39aea-106">入力</span><span class="sxs-lookup"><span data-stu-id="39aea-106">Input</span></span>

### <a name="value--__invalidresult__"></a><span data-ttu-id="39aea-107">値: __無効 <Result>__</span><span class="sxs-lookup"><span data-stu-id="39aea-107">value : __invalid<Result>__</span></span>

<span data-ttu-id="39aea-108">アサートされる最上位ビットの値。</span><span class="sxs-lookup"><span data-stu-id="39aea-108">The value of the highest bit being asserted.</span></span>


### <a name="number--littleendian"></a><span data-ttu-id="39aea-109">数値: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="39aea-109">number : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="39aea-110">最上位ビットがチェックされる符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="39aea-110">Unsigned integer of which the highest bit is checked.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39aea-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39aea-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39aea-112">解説</span><span class="sxs-lookup"><span data-stu-id="39aea-112">Remarks</span></span>

<span data-ttu-id="39aea-113">この操作の制御されたバージョンは、コントロールを無視します。</span><span class="sxs-lookup"><span data-stu-id="39aea-113">The controlled version of this operation ignores controls.</span></span>

## <a name="see-also"></a><span data-ttu-id="39aea-114">参照</span><span class="sxs-lookup"><span data-stu-id="39aea-114">See Also</span></span>

- [<span data-ttu-id="39aea-115">Microsoft. Quantum. Assert</span><span class="sxs-lookup"><span data-stu-id="39aea-115">Microsoft.Quantum.Intrinsic.Assert</span></span>](xref:Microsoft.Quantum.Intrinsic.Assert)