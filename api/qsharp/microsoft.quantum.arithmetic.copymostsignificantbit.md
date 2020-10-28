---
uid: Microsoft.Quantum.Arithmetic.CopyMostSignificantBit
title: CopyMostSignificantBit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CopyMostSignificantBit
qsharp.summary: Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.
ms.openlocfilehash: 02119103fa7b5776f0e1681535115e0773a34c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721214"
---
# <a name="copymostsignificantbit-operation"></a><span data-ttu-id="6e39a-102">CopyMostSignificantBit 操作</span><span class="sxs-lookup"><span data-stu-id="6e39a-102">CopyMostSignificantBit operation</span></span>

<span data-ttu-id="6e39a-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6e39a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6e39a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e39a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e39a-105">符号なし整数を表す qubit レジスタの最上位ビットを `from` qubit にコピーし `target` ます。</span><span class="sxs-lookup"><span data-stu-id="6e39a-105">Copies the most significant bit of a qubit register `from` representing an unsigned integer into the qubit `target`.</span></span>

```qsharp
operation CopyMostSignificantBit (from : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="6e39a-106">入力</span><span class="sxs-lookup"><span data-stu-id="6e39a-106">Input</span></span>

### <a name="from--littleendian"></a><span data-ttu-id="6e39a-107">from: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6e39a-107">from : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6e39a-108">最上位ビットのコピー元の符号なし整数。</span><span class="sxs-lookup"><span data-stu-id="6e39a-108">The unsigned integer from which the highest bit is copied from.</span></span>
<span data-ttu-id="6e39a-109">整数は、リトルエンディアン形式でエンコードされます。</span><span class="sxs-lookup"><span data-stu-id="6e39a-109">the integer is encoded in little-endian format.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="6e39a-110">ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="6e39a-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="6e39a-111">最上位ビットがコピーされる qubit。</span><span class="sxs-lookup"><span data-stu-id="6e39a-111">The qubit in which the highest bit is being copied.</span></span> <span data-ttu-id="6e39a-112">ビットエンコードは計算に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6e39a-112">The bit encoding is in computational basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e39a-113">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e39a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="6e39a-114">参照</span><span class="sxs-lookup"><span data-stu-id="6e39a-114">See Also</span></span>

- [<span data-ttu-id="6e39a-115">LittleEndian です。</span><span class="sxs-lookup"><span data-stu-id="6e39a-115">Microsoft.Quantum.Arithmetic.LittleEndian</span></span>](xref:Microsoft.Quantum.Arithmetic.LittleEndian)