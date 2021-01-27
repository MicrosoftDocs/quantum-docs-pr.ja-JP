---
uid: Microsoft.Quantum.Core.Deprecated
title: 非推奨のユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 1a32d98f5d034c2673d42301b45379da1302ca7f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832079"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="434dd-102">非推奨のユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="434dd-102">Deprecated user defined type</span></span>

<span data-ttu-id="434dd-103">名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="434dd-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="434dd-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="434dd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="434dd-105">型をマークしたり、非推奨として呼び出し可能にしたりするために使用される、コンパイラが認識する属性。</span><span class="sxs-lookup"><span data-stu-id="434dd-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="434dd-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="434dd-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="434dd-107">NewName: [文字列](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="434dd-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="434dd-108">代わりに使用する型の完全名または呼び出し可能な名前。</span><span class="sxs-lookup"><span data-stu-id="434dd-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="434dd-109">型または呼び出し可能なが置換なしで非推奨になった場合、は空の文字列に設定されます。</span><span class="sxs-lookup"><span data-stu-id="434dd-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>