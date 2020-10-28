---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: Controlは Onint 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716415"
---
# <a name="controlledonint-function"></a><span data-ttu-id="431d3-102">Controlは Onint 関数</span><span class="sxs-lookup"><span data-stu-id="431d3-102">ControlledOnInt function</span></span>

<span data-ttu-id="431d3-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="431d3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="431d3-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="431d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="431d3-105">制御レジスタの状態が指定した正の整数に対応する場合に、ターゲットレジスタに oracle を適用する、ユニタリ演算子を返します。</span><span class="sxs-lookup"><span data-stu-id="431d3-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="431d3-106">入力</span><span class="sxs-lookup"><span data-stu-id="431d3-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="431d3-107">数値の状態: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="431d3-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="431d3-108">正の整数。</span><span class="sxs-lookup"><span data-stu-id="431d3-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="431d3-109">oracle: t => [ユニット](xref:microsoft.quantum.lang-ref.unit) の調整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="431d3-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="431d3-110">ユニタリ演算子。</span><span class="sxs-lookup"><span data-stu-id="431d3-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="431d3-111">出力: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], ' t) => [単位](xref:microsoft.quantum.lang-ref.unit) の形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="431d3-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="431d3-112">`oracle`コントロールの登録状態が数値の状態に対応している場合にターゲットレジスタに適用される、ユニタリ演算子 `numberState` 。</span><span class="sxs-lookup"><span data-stu-id="431d3-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="431d3-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="431d3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="431d3-114">&</span><span class="sxs-lookup"><span data-stu-id="431d3-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="431d3-115">解説</span><span class="sxs-lookup"><span data-stu-id="431d3-115">Remarks</span></span>

<span data-ttu-id="431d3-116">の値は、リトルエン `numberState` ディアンエンコーディングを使用して解釈されます。</span><span class="sxs-lookup"><span data-stu-id="431d3-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>