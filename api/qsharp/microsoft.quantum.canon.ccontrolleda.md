---
uid: Microsoft.Quantum.Canon.CControlledA
title: Ccontrol/関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 823d80182621691f4fa6f42246b3d671f3adfc3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840987"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="01208-102">Ccontrol/関数</span><span class="sxs-lookup"><span data-stu-id="01208-102">CControlledA function</span></span>

<span data-ttu-id="01208-103">名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="01208-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="01208-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="01208-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="01208-105">操作 op が指定された場合、は、従来の制御ビットが true の場合に op を適用する新しい操作を返します。</span><span class="sxs-lookup"><span data-stu-id="01208-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="01208-106">`false`の場合、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="01208-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="01208-107">修飾子は、 `A` 操作が adjointable であることを示します。</span><span class="sxs-lookup"><span data-stu-id="01208-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="01208-108">入力</span><span class="sxs-lookup"><span data-stu-id="01208-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="01208-109">op: ' t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="01208-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="01208-110">条件付きで適用する操作。</span><span class="sxs-lookup"><span data-stu-id="01208-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit--is-adj"></a><span data-ttu-id="01208-111">出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t) => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞です</span><span class="sxs-lookup"><span data-stu-id="01208-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="01208-112">新しい操作。これは、クラシック制御ビットが true の場合の op です。</span><span class="sxs-lookup"><span data-stu-id="01208-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="01208-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="01208-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="01208-114">&</span><span class="sxs-lookup"><span data-stu-id="01208-114">'T</span></span>

<span data-ttu-id="01208-115">条件付きで適用される操作の入力型。</span><span class="sxs-lookup"><span data-stu-id="01208-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="01208-116">参照</span><span class="sxs-lookup"><span data-stu-id="01208-116">See Also</span></span>

- [<span data-ttu-id="01208-117">Microsoft.............</span><span class="sxs-lookup"><span data-stu-id="01208-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)