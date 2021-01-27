---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858160"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="90603-102">BlockEncodingByLCU 関数</span><span class="sxs-lookup"><span data-stu-id="90603-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="90603-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="90603-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="90603-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90603-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90603-105">対象の演算子をにエンコード `BlockEncoding` します。</span><span class="sxs-lookup"><span data-stu-id="90603-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="90603-106">これにより、 `BlockEncoding` 一部の演算子 $H = \ sum_ {j} | \ alpha_j | をエンコードする、$U = P\ cdot V\ Cdot P ^/ダガー $ が構築されます。U_j $ は、unitaries います。</span><span class="sxs-lookup"><span data-stu-id="90603-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="90603-107">通常、$P $ は、$P \ket {0} \_ a = \ sum_j \ sqrt{\ alpha_j/ \| \ vec-alpha \| \_ 2} \ket{j} \_ a $、$V = \ sum_ {j} \ket{j}\bra{j} \_ aotimes U_j $ という状態の準備を行うためのものです。</span><span class="sxs-lookup"><span data-stu-id="90603-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="90603-108">入力</span><span class="sxs-lookup"><span data-stu-id="90603-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="90603-109">statePreparation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="90603-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="90603-110">いくつかのターゲット状態を準備する、$P の1つのユニタリ。</span><span class="sxs-lookup"><span data-stu-id="90603-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="90603-111">セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="90603-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="90603-112">$H $ のコンポーネント unitaries エンコードする、$V の $。</span><span class="sxs-lookup"><span data-stu-id="90603-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="90603-113">出力: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="90603-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="90603-114">$U $ はレジスタに対して共同で動作し、 `a` `s` $H $ をブロックエンコードし、$U ^ ダガー = U $ を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="90603-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="90603-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="90603-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="90603-116">&</span><span class="sxs-lookup"><span data-stu-id="90603-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="90603-117">Emc</span><span class="sxs-lookup"><span data-stu-id="90603-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="90603-118">解説</span><span class="sxs-lookup"><span data-stu-id="90603-118">Remarks</span></span>

<span data-ttu-id="90603-119">この `BlockEncoding` 実装は、のプロパティを提供 `BlockEncodingReflection` します。</span><span class="sxs-lookup"><span data-stu-id="90603-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="90603-120">参照</span><span class="sxs-lookup"><span data-stu-id="90603-120">See Also</span></span>

- [<span data-ttu-id="90603-121">Microsoft. クォンタム. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="90603-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="90603-122">BlockEncodingReflection です。</span><span class="sxs-lookup"><span data-stu-id="90603-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)