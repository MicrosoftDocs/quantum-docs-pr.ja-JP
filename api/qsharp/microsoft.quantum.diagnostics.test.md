---
uid: Microsoft.Quantum.Diagnostics.Test
title: テストユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 2f1b521c4ef2bf8e672ca4fe7a5f380d744300b7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853269"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="32992-102">テストユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="32992-102">Test user defined type</span></span>

<span data-ttu-id="32992-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="32992-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="32992-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="32992-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="32992-105">単体テストをマークするために使用されるコンパイラ認識属性。</span><span class="sxs-lookup"><span data-stu-id="32992-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="32992-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="32992-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="32992-107">ExecutionTarget: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="32992-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

