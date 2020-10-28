---
uid: Microsoft.Quantum.Core.Deprecated
title: 非推奨のユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: b1fcae9647b2a655d25773386ecffa826515516e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713274"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="a565c-102">非推奨のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="a565c-102">Deprecated user defined type</span></span>

<span data-ttu-id="a565c-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a565c-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a565c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a565c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a565c-105">型をマークしたり、非推奨として呼び出し可能にしたりするために使用される、コンパイラが認識する属性。</span><span class="sxs-lookup"><span data-stu-id="a565c-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="a565c-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="a565c-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="a565c-107">NewName: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a565c-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a565c-108">代わりに使用する型の完全名または呼び出し可能な名前。</span><span class="sxs-lookup"><span data-stu-id="a565c-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="a565c-109">型または呼び出し可能なが置換なしで非推奨になった場合、は空の文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a565c-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>