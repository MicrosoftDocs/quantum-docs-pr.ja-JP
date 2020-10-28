---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: b8eff9d207752213ccdf42a9ad80fefb2da07216
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723918"
---
# <a name="blockencodingreflectionbylcu-function"></a><span data-ttu-id="798b8-102">BlockEncodingReflectionByLCU 関数</span><span class="sxs-lookup"><span data-stu-id="798b8-102">BlockEncodingReflectionByLCU function</span></span>

<span data-ttu-id="798b8-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="798b8-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="798b8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="798b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="798b8-105">対象の演算子をにエンコード `BlockEncodingReflection` します。</span><span class="sxs-lookup"><span data-stu-id="798b8-105">Encodes an operator of interest into a `BlockEncodingReflection`.</span></span>

<span data-ttu-id="798b8-106">これにより、 `BlockEncodingReflection` 一部の演算子 $H = \ sum_ {j} | \ alpha_j | をエンコードする、$U = P\ cdot V\ Cdot P ^/ダガー $ が構築されます。U_j $ は、unitaries います。</span><span class="sxs-lookup"><span data-stu-id="798b8-106">This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="798b8-107">通常、$P $ は、$P \ket {0} \_ a \ sum_j \ sqrt{\ alpha_j/ \| \ vec-alpha \| \_ 2} \ket{j} \_ a $、$V = \ sum_ {j} \ket{j}\bra{j} \_ aotimes U_j $ という状態の準備を行うためのものです。</span><span class="sxs-lookup"><span data-stu-id="798b8-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a><span data-ttu-id="798b8-108">入力</span><span class="sxs-lookup"><span data-stu-id="798b8-108">Input</span></span>

### <a name="statepreparation--qubit--unit-adj--ctl"></a><span data-ttu-id="798b8-109">statePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="798b8-109">statePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="798b8-110">いくつかのターゲット状態を準備する、$P の1つのユニタリ。</span><span class="sxs-lookup"><span data-stu-id="798b8-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="798b8-111">セレクター: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [単位](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="798b8-111">selector : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="798b8-112">$H $ のコンポーネント unitaries エンコードする、$V の $。</span><span class="sxs-lookup"><span data-stu-id="798b8-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--blockencodingreflection"></a><span data-ttu-id="798b8-113">出力: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="798b8-113">Output : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="798b8-114">レジスタに対して共同で動作し `a` 、 `s` $H $ をブロックエンコードし、$U ' ^ = U $ を満たす $U の、1つのユニタリ {-1} です。</span><span class="sxs-lookup"><span data-stu-id="798b8-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U'^{-1} = U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="798b8-115">解説</span><span class="sxs-lookup"><span data-stu-id="798b8-115">Remarks</span></span>

<span data-ttu-id="798b8-116">この `BlockEncoding` 実装は、のプロパティを提供 `BlockEncodingReflection` します。</span><span class="sxs-lookup"><span data-stu-id="798b8-116">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="798b8-117">参照</span><span class="sxs-lookup"><span data-stu-id="798b8-117">See Also</span></span>

- [<span data-ttu-id="798b8-118">Microsoft. クォンタム. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="798b8-118">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="798b8-119">BlockEncodingReflection です。</span><span class="sxs-lookup"><span data-stu-id="798b8-119">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)