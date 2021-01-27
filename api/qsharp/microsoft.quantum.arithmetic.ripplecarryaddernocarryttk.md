---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 0e131204d3eaff7f99aa9ff7c3c1ae93a1bf611b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846339"
---
# <a name="ripplecarryaddernocarryttk-operation"></a><span data-ttu-id="d79f4-102">RippleCarryAdderNoCarryTTK 操作</span><span class="sxs-lookup"><span data-stu-id="d79f4-102">RippleCarryAdderNoCarryTTK operation</span></span>

<span data-ttu-id="d79f4-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d79f4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d79f4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d79f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d79f4-105">元に戻すことができ、インプレースリップは実行されずに2つの整数を追加します。</span><span class="sxs-lookup"><span data-stu-id="d79f4-105">Reversible, in-place ripple-carry addition of two integers without carry out.</span></span>

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d79f4-106">説明</span><span class="sxs-lookup"><span data-stu-id="d79f4-106">Description</span></span>

<span data-ttu-id="d79f4-107">LittleEndian レジスタおよびでエンコードされた2つの $n $ bit 整数が指定されている場合、この `xs` `ys` 操作は2つの整数剰余 $ 2 ^ n $ の合計を計算し `xs` ます。ここで $n $ は入力とのビットサイズです `ys` 。</span><span class="sxs-lookup"><span data-stu-id="d79f4-107">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, the operation computes the sum of the two integers modulo $2^n$, where $n$ is the bit size of the inputs `xs` and `ys`.</span></span> <span data-ttu-id="d79f4-108">実行ビットは計算されません。</span><span class="sxs-lookup"><span data-stu-id="d79f4-108">It does not compute the carry out bit.</span></span>

## <a name="input"></a><span data-ttu-id="d79f4-109">入力</span><span class="sxs-lookup"><span data-stu-id="d79f4-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d79f4-110">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d79f4-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d79f4-111">LittleEndian qubit レジスタは、最初の整数 summand をエンコードします。</span><span class="sxs-lookup"><span data-stu-id="d79f4-111">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d79f4-112">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d79f4-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d79f4-113">LittleEndian qubit レジスタエンコーディング2番目の整数 summand は、合計の最下位のビット $n を保持するように変更されています。</span><span class="sxs-lookup"><span data-stu-id="d79f4-113">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d79f4-114">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d79f4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d79f4-115">解説</span><span class="sxs-lookup"><span data-stu-id="d79f4-115">Remarks</span></span>

<span data-ttu-id="d79f4-116">この操作には RippleCarryAdderTTK と同じ機能がありますが、キャリービットは返されません。</span><span class="sxs-lookup"><span data-stu-id="d79f4-116">This operation has the same functionality as RippleCarryAdderTTK but does not return the carry bit.</span></span>

## <a name="references"></a><span data-ttu-id="d79f4-117">References</span><span class="sxs-lookup"><span data-stu-id="d79f4-117">References</span></span>

- <span data-ttu-id="d79f4-118">Yasuhiro Takahashi、Seiichiro Tani、Noboru Kunihiro: "クォンタムの追加回路と無制限のファンアウト"、クォンタムの情報と計算、Vol. 10、2010。</span><span class="sxs-lookup"><span data-stu-id="d79f4-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530