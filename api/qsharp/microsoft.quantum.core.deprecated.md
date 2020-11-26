---
uid: Microsoft.Quantum.Core.Deprecated
title: 非推奨のユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224090"
---
# <a name="deprecated-user-defined-type"></a>非推奨のユーザー定義型

名前空間: [Microsoft. Quantum. コア](xref:Microsoft.Quantum.Core)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


型をマークしたり、非推奨として呼び出し可能にしたりするために使用される、コンパイラが認識する属性。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>名前付き項目

### <a name="newname--string"></a>NewName: [文字列](xref:microsoft.quantum.lang-ref.string)

代わりに使用する型の完全名または呼び出し可能な名前。
型または呼び出し可能なが置換なしで非推奨になった場合、は空の文字列に設定されます。