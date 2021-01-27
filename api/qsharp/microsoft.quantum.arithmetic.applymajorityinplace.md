---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843726"
---
# <a name="applymajorityinplace-operation"></a><span data-ttu-id="b31a9-102">ApplyMajorityInPlace 操作</span><span class="sxs-lookup"><span data-stu-id="b31a9-102">ApplyMajorityInPlace operation</span></span>

<span data-ttu-id="b31a9-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b31a9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b31a9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b31a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b31a9-105">Qubit のレジスタに対して、3つの qubit マジョリティ操作をインプレースで適用します。</span><span class="sxs-lookup"><span data-stu-id="b31a9-105">Applies the three-qubit majority operation in-place on a register of qubits.</span></span>

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b31a9-106">説明</span><span class="sxs-lookup"><span data-stu-id="b31a9-106">Description</span></span>

<span data-ttu-id="b31a9-107">この操作では、3つの qubits のインプレース関数を計算します。</span><span class="sxs-lookup"><span data-stu-id="b31a9-107">This operation computes the majority function in-place on 3 qubits.</span></span>

<span data-ttu-id="b31a9-108">出力 qubit を $z $、入力 qubit を $x $ および $y $ として示す場合、この操作では次の変換が実行されます: $ \ket{xyz} \rightarrow \ket{x-oplus z} \ket{y \ oplus z} \ket{\operatorname{MAJ} (x, y, z)} $。</span><span class="sxs-lookup"><span data-stu-id="b31a9-108">If we denote output qubit as $z$ and input qubits as $x$ and $y$, the operation performs the following transformation: $\ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x, y, z)}$.</span></span>

## <a name="input"></a><span data-ttu-id="b31a9-109">入力</span><span class="sxs-lookup"><span data-stu-id="b31a9-109">Input</span></span>

### <a name="output--qubit"></a><span data-ttu-id="b31a9-110">出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b31a9-110">output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b31a9-111">最初の入力 qubit。</span><span class="sxs-lookup"><span data-stu-id="b31a9-111">First input qubit.</span></span> <span data-ttu-id="b31a9-112">出力がインプレースで計算され、この qubit に格納されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b31a9-112">Note that the output is computed in-place and stored in this qubit.</span></span>


### <a name="input--qubit"></a><span data-ttu-id="b31a9-113">入力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b31a9-113">input : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b31a9-114">2番目と3番目の入力 qubits。</span><span class="sxs-lookup"><span data-stu-id="b31a9-114">Second and third input qubits.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b31a9-115">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b31a9-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

