---
uid: Microsoft.Quantum.Canon.CControlledCA
title: Ccontrolを持つ Ca 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: cc1a783dfbf97afae50f4b42e66cba2b2a2ec833
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207430"
---
# <a name="ccontrolledca-function"></a><span data-ttu-id="39fe0-102">Ccontrolを持つ Ca 関数</span><span class="sxs-lookup"><span data-stu-id="39fe0-102">CControlledCA function</span></span>

<span data-ttu-id="39fe0-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39fe0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39fe0-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39fe0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39fe0-105">操作 op が指定された場合、は、従来の制御ビットが true の場合に op を適用する新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="39fe0-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="39fe0-106">`false`の場合、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="39fe0-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="39fe0-107">修飾子は、 `CA` 操作が制御可能であり、adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="39fe0-107">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="39fe0-108">入力</span><span class="sxs-lookup"><span data-stu-id="39fe0-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="39fe0-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl です</span><span class="sxs-lookup"><span data-stu-id="39fe0-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="39fe0-110">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="39fe0-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj--ctl"></a><span data-ttu-id="39fe0-111">出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="39fe0-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="39fe0-112">新しい操作。これは、クラシック制御ビットが true の場合の op です。</span><span class="sxs-lookup"><span data-stu-id="39fe0-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39fe0-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="39fe0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39fe0-114">&</span><span class="sxs-lookup"><span data-stu-id="39fe0-114">'T</span></span>

<span data-ttu-id="39fe0-115">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="39fe0-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="39fe0-116">参照</span><span class="sxs-lookup"><span data-stu-id="39fe0-116">See Also</span></span>

- [<span data-ttu-id="39fe0-117">Microsoft.............</span><span class="sxs-lookup"><span data-stu-id="39fe0-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)