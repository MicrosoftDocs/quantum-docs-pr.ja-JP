---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229547"
---
# <a name="blockencodingbylcu-function"></a><span data-ttu-id="f8368-102">BlockEncodingByLCU 関数</span><span class="sxs-lookup"><span data-stu-id="f8368-102">BlockEncodingByLCU function</span></span>

<span data-ttu-id="f8368-103">名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="f8368-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="f8368-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f8368-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f8368-105">対象の演算子をにエンコード `BlockEncoding` します。</span><span class="sxs-lookup"><span data-stu-id="f8368-105">Encodes an operator of interest into a `BlockEncoding`.</span></span>

<span data-ttu-id="f8368-106">これにより、 `BlockEncoding` 一部の演算子 $H = \ sum_ {j} | \ alpha_j | をエンコードする、$U = P\ cdot V\ Cdot P ^/ダガー $ が構築されます。U_j $ は、unitaries います。</span><span class="sxs-lookup"><span data-stu-id="f8368-106">This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries.</span></span> <span data-ttu-id="f8368-107">通常、$P $ は、$P \ket {0} \_ a = \ sum_j \ sqrt{\ alpha_j/ \| \ vec-alpha \| \_ 2} \ket{j} \_ a $、$V = \ sum_ {j} \ket{j}\bra{j} \_ aotimes U_j $ という状態の準備を行うためのものです。</span><span class="sxs-lookup"><span data-stu-id="f8368-107">Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.</span></span>

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="f8368-108">入力</span><span class="sxs-lookup"><span data-stu-id="f8368-108">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="f8368-109">statePreparation: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="f8368-109">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f8368-110">いくつかのターゲット状態を準備する、$P の1つのユニタリ。</span><span class="sxs-lookup"><span data-stu-id="f8368-110">A unitary $P$ that prepares some target state.</span></span>


### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="f8368-111">セレクター: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="f8368-111">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f8368-112">$H $ のコンポーネント unitaries エンコードする、$V の $。</span><span class="sxs-lookup"><span data-stu-id="f8368-112">A unitary $V$ that encodes the component unitaries of $H$.</span></span>



## <a name="output--ts--unit--is-adj--ctl"></a><span data-ttu-id="f8368-113">出力: (' t, s) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="f8368-113">Output : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f8368-114">$U $ はレジスタに対して共同で動作し、 `a` `s` $H $ をブロックエンコードし、$U ^ ダガー = U $ を満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="f8368-114">A unitary $U$ acting jointly on registers `a` and `s` that block- encodes $H$, and satisfies $U^\dagger = U$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f8368-115">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8368-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f8368-116">&</span><span class="sxs-lookup"><span data-stu-id="f8368-116">'T</span></span>


### <a name="s"></a><span data-ttu-id="f8368-117">Emc</span><span class="sxs-lookup"><span data-stu-id="f8368-117">'S</span></span>



## <a name="remarks"></a><span data-ttu-id="f8368-118">解説</span><span class="sxs-lookup"><span data-stu-id="f8368-118">Remarks</span></span>

<span data-ttu-id="f8368-119">この `BlockEncoding` 実装は、のプロパティを提供 `BlockEncodingReflection` します。</span><span class="sxs-lookup"><span data-stu-id="f8368-119">This `BlockEncoding` implementation gives it the properties of a `BlockEncodingReflection`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8368-120">参照</span><span class="sxs-lookup"><span data-stu-id="f8368-120">See Also</span></span>

- [<span data-ttu-id="f8368-121">Microsoft. クォンタム. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="f8368-121">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="f8368-122">BlockEncodingReflection です。</span><span class="sxs-lookup"><span data-stu-id="f8368-122">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)