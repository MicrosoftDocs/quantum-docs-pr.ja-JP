---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 2065c767b341241d32e5ac06bcff0071cbadb266
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843343"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="31e4b-102">CarryOutCoreCDKM 操作</span><span class="sxs-lookup"><span data-stu-id="31e4b-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="31e4b-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="31e4b-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="31e4b-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31e4b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="31e4b-105">上の ApplyOuterCDKMAdder 操作と共に使用される RippleCarryAdderCDKM のコア操作。つまり、この操作で RippleCarryAdderCDKM の内部操作を取得します。</span><span class="sxs-lookup"><span data-stu-id="31e4b-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="31e4b-106">この操作では、繰越 qubit を計算し、入力の一部ではないゲートのシーケンスを適用し `ys` ます。</span><span class="sxs-lookup"><span data-stu-id="31e4b-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="31e4b-107">入力</span><span class="sxs-lookup"><span data-stu-id="31e4b-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="31e4b-108">xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="31e4b-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="31e4b-109">最初の qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="31e4b-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="31e4b-110">y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="31e4b-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="31e4b-111">2番目の qubit レジスタ。</span><span class="sxs-lookup"><span data-stu-id="31e4b-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="31e4b-112">ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31e4b-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="31e4b-113">この操作に渡された RippleCarryAdderCDKM で使用される ancilla qubit。</span><span class="sxs-lookup"><span data-stu-id="31e4b-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="31e4b-114">キャリー: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="31e4b-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="31e4b-115">RippleCarryAdderCDKM 操作で qubit を実行します。</span><span class="sxs-lookup"><span data-stu-id="31e4b-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31e4b-116">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31e4b-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="31e4b-117">References</span><span class="sxs-lookup"><span data-stu-id="31e4b-117">References</span></span>

- <span data-ttu-id="31e4b-118">Cuccaro、Draper、Samuel、Kutin、David Petrie の: "新しいクォンタム ripple-キャリー追加回路", 2004 ですが、このようになります。</span><span class="sxs-lookup"><span data-stu-id="31e4b-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1