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