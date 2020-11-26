---
uid: Microsoft.Quantum.Diagnostics.Test
title: テストユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 80821cb46d773d84085838d9ee539a8a45c43e61
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201497"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="53629-102">テストユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="53629-102">Test user defined type</span></span>

<span data-ttu-id="53629-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="53629-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="53629-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="53629-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="53629-105">単体テストをマークするために使用されるコンパイラ認識属性。</span><span class="sxs-lookup"><span data-stu-id="53629-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="53629-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="53629-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="53629-107">ExecutionTarget: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="53629-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

