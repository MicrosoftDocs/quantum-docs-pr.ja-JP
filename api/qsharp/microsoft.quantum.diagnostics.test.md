---
uid: Microsoft.Quantum.Diagnostics.Test
title: テストユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Test
qsharp.summary: Compiler-recognized attribute used to mark a unit test.
ms.openlocfilehash: 8030f6378ac0cb393c7ed2b9e636a7561e8943a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712644"
---
# <a name="test-user-defined-type"></a><span data-ttu-id="652bf-102">テストユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="652bf-102">Test user defined type</span></span>

<span data-ttu-id="652bf-103">名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="652bf-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="652bf-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="652bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="652bf-105">単体テストをマークするために使用されるコンパイラ認識属性。</span><span class="sxs-lookup"><span data-stu-id="652bf-105">Compiler-recognized attribute used to mark a unit test.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a><span data-ttu-id="652bf-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="652bf-106">Named Items</span></span>

### <a name="executiontarget--string"></a><span data-ttu-id="652bf-107">ExecutionTarget: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="652bf-107">ExecutionTarget : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

