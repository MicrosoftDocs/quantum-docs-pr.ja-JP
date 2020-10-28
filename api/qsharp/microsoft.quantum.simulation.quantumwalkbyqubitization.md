---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725575"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="3b4fb-102">QuantumWalkByQubitization 関数</span><span class="sxs-lookup"><span data-stu-id="3b4fb-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="3b4fb-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3b4fb-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3b4fb-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b4fb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b4fb-105">ブロックエンコードのリフレクションをクォンタムウォークに変換します。</span><span class="sxs-lookup"><span data-stu-id="3b4fb-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="3b4fb-106">説明</span><span class="sxs-lookup"><span data-stu-id="3b4fb-106">Description</span></span>

<span data-ttu-id="3b4fb-107">$W `BlockEncodingReflection` 対象の $H 演算子をエンコードする $U $ で表されるが指定されている場合は、$-pm e ^ {\ pm i\ sin ^ {-1} (H)} $ の範囲を含むクォンタムウォーク $ に変換します。</span><span class="sxs-lookup"><span data-stu-id="3b4fb-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="3b4fb-108">入力</span><span class="sxs-lookup"><span data-stu-id="3b4fb-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="3b4fb-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="3b4fb-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="3b4fb-110">`BlockEncodingReflection`クォンタムウォークに変換するための、$U の ' $ ' を指定します。</span><span class="sxs-lookup"><span data-stu-id="3b4fb-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="3b4fb-111">出力: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="3b4fb-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="3b4fb-112">クォンタムウォーク $W $ はレジスタに対して共同で動作し、$ `a` `s` $H-pm e ^ {\ pm i\ sin ^ {-1} (H)} $ の範囲を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="3b4fb-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="3b4fb-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="3b4fb-113">References</span></span>

- <span data-ttu-id="3b4fb-114">Hamiltonian シミュレーション Qubitization Guang Hao Low、Isaac L. 語 https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="3b4fb-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="3b4fb-115">参照</span><span class="sxs-lookup"><span data-stu-id="3b4fb-115">See Also</span></span>

- [<span data-ttu-id="3b4fb-116">Microsoft. クォンタム. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="3b4fb-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="3b4fb-117">BlockEncodingReflection です。</span><span class="sxs-lookup"><span data-stu-id="3b4fb-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)