---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 0cc16dddc27a000dbc30de6ae27976a01fd9f4ed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721219"
---
# <a name="dividei-operation"></a><span data-ttu-id="c5108-102">DivideI 操作</span><span class="sxs-lookup"><span data-stu-id="c5108-102">DivideI operation</span></span>

<span data-ttu-id="c5108-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c5108-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c5108-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5108-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5108-105">2つのクォンタム整数を除算します。</span><span class="sxs-lookup"><span data-stu-id="c5108-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="c5108-106">説明</span><span class="sxs-lookup"><span data-stu-id="c5108-106">Description</span></span>

<span data-ttu-id="c5108-107">`xs` は残りを保持し、を `xs - floor(xs/ys) * ys` `result` 保持 `floor(xs/ys)` します。</span><span class="sxs-lookup"><span data-stu-id="c5108-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="c5108-108">入力</span><span class="sxs-lookup"><span data-stu-id="c5108-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="c5108-109">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5108-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5108-110">$n $-bit 被除数は、剰余に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c5108-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="c5108-111">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5108-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5108-112">$n $-bit 除数</span><span class="sxs-lookup"><span data-stu-id="c5108-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="c5108-113">結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c5108-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c5108-114">$ bit の結果 $n は、最初は状態 $ \ket $ である必要があり、 {0} 整数除算の結果に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="c5108-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c5108-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c5108-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c5108-116">解説</span><span class="sxs-lookup"><span data-stu-id="c5108-116">Remarks</span></span>

<span data-ttu-id="c5108-117">は、標準のシフトと減算のアプローチを使用して除算を実装します。</span><span class="sxs-lookup"><span data-stu-id="c5108-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="c5108-118">コントロールバージョンは特化されているので、減算には追加の制御は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c5108-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>