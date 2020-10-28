---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Ccontrolを持つ Ca 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716569"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="0bde0-102">Ccontrolを持つ Ca 関数</span><span class="sxs-lookup"><span data-stu-id="0bde0-102">CControlledCA function</span></span>

<span data-ttu-id="0bde0-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0bde0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0bde0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0bde0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0bde0-105">操作 op が指定された場合、は、従来の制御ビットが true の場合に op を適用する新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="0bde0-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="0bde0-106">`false`の場合、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="0bde0-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="0bde0-107">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0bde0-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="0bde0-108">入力</span><span class="sxs-lookup"><span data-stu-id="0bde0-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="0bde0-109">op: ' t => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="0bde0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="0bde0-110">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="0bde0-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-ctl--adj"></a><span data-ttu-id="0bde0-111">出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容詞</span><span class="sxs-lookup"><span data-stu-id="0bde0-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="0bde0-112">新しい操作。これは、クラシック制御ビットが true の場合の op です。</span><span class="sxs-lookup"><span data-stu-id="0bde0-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0bde0-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="0bde0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0bde0-114">&</span><span class="sxs-lookup"><span data-stu-id="0bde0-114">'T</span></span>

<span data-ttu-id="0bde0-115">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="0bde0-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bde0-116">参照</span><span class="sxs-lookup"><span data-stu-id="0bde0-116">See Also</span></span>

- [<span data-ttu-id="0bde0-117">Microsoft.............</span><span class="sxs-lookup"><span data-stu-id="0bde0-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)