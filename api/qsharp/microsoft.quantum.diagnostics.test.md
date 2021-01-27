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
# <a name="test-user-defined-type"></a>テストユーザー定義型

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


単体テストをマークするために使用されるコンパイラ認識属性。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>名前付き項目

### <a name="executiontarget--string"></a>ExecutionTarget: [文字列](xref:microsoft.quantum.lang-ref.string)

