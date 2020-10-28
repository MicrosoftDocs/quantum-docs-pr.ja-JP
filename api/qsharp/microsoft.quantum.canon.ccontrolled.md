---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716592"
---
# <a name="ccontrolled-function"></a><span data-ttu-id="daa00-102">CControlled 関数</span><span class="sxs-lookup"><span data-stu-id="daa00-102">CControlled function</span></span>

<span data-ttu-id="daa00-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="daa00-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="daa00-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="daa00-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="daa00-105">操作 op が指定された場合、は、従来の制御ビットが true の場合に op を適用する新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="daa00-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="daa00-106">`false`の場合、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="daa00-106">If `false`, nothing happens.</span></span>

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a><span data-ttu-id="daa00-107">入力</span><span class="sxs-lookup"><span data-stu-id="daa00-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="daa00-108">op: t => [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="daa00-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="daa00-109">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="daa00-109">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit"></a><span data-ttu-id="daa00-110">出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="daa00-110">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="daa00-111">新しい操作。これは、クラシック制御ビットが true の場合の op です。</span><span class="sxs-lookup"><span data-stu-id="daa00-111">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="daa00-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="daa00-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="daa00-113">&</span><span class="sxs-lookup"><span data-stu-id="daa00-113">'T</span></span>

<span data-ttu-id="daa00-114">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="daa00-114">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="daa00-115">参照</span><span class="sxs-lookup"><span data-stu-id="daa00-115">See Also</span></span>

- [<span data-ttu-id="daa00-116">Microsoft......................</span><span class="sxs-lookup"><span data-stu-id="daa00-116">Microsoft.Quantum.Canon.CControlledC</span></span>](xref:Microsoft.Quantum.Canon.CControlledC)
- [<span data-ttu-id="daa00-117">Microsoft............</span><span class="sxs-lookup"><span data-stu-id="daa00-117">Microsoft.Quantum.Canon.CControlledA</span></span>](xref:Microsoft.Quantum.Canon.CControlledA)
- [<span data-ttu-id="daa00-118">Microsoft......................</span><span class="sxs-lookup"><span data-stu-id="daa00-118">Microsoft.Quantum.Canon.CControlledCA</span></span>](xref:Microsoft.Quantum.Canon.CControlledCA)