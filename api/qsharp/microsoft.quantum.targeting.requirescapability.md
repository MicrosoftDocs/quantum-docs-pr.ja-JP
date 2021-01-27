---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855151"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="88deb-102">RequiresCapability ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="88deb-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="88deb-103">名前空間: [Microsoft. Quantum. ターゲット](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="88deb-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="88deb-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="88deb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="88deb-105">コンパイラが必要とするランタイム機能で呼び出し可能をマークするために使用される、コンパイラが認識する属性。</span><span class="sxs-lookup"><span data-stu-id="88deb-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="88deb-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="88deb-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="88deb-107">Level: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="88deb-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="88deb-108">呼び出し可能で必要なランタイム機能レベルの名前。</span><span class="sxs-lookup"><span data-stu-id="88deb-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="88deb-109">理由: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="88deb-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="88deb-110">呼び出し可能にこのランタイム機能が必要な理由についての説明。</span><span class="sxs-lookup"><span data-stu-id="88deb-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="88deb-111">解説</span><span class="sxs-lookup"><span data-stu-id="88deb-111">Remarks</span></span>

<span data-ttu-id="88deb-112">この属性は、呼び出し可能なにこの属性のインスタンスが既に存在していない限り、コンパイラによって生成可能な呼び出しに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="88deb-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="88deb-113">使用しないでください。ただし、コンパイラが必要な機能を正しく推論できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="88deb-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="88deb-114">機能レベル名の一覧を次に示します。機能が強化されるか、制限が減少します。</span><span class="sxs-lookup"><span data-stu-id="88deb-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="88deb-115">測定結果を等しいかどうかを比較することはできません。</span><span class="sxs-lookup"><span data-stu-id="88deb-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="88deb-116">演算では、if ステートメントの条件式でのみ等しいかどうかを比較できます。</span><span class="sxs-lookup"><span data-stu-id="88deb-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="88deb-117">結果に依存する if ステートメントのブロックには、ブロックの外側で宣言された変更可能な変数の set ステートメント、または return ステートメントを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="88deb-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="88deb-118">実行時の制限はありません。</span><span class="sxs-lookup"><span data-stu-id="88deb-118">No runtime restrictions.</span></span> <span data-ttu-id="88deb-119">任意の Q # プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="88deb-119">Any Q# program can be executed.</span></span>