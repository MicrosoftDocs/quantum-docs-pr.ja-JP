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
# <a name="test-user-defined-type"></a>テストユーザー定義型

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


単体テストをマークするために使用されるコンパイラ認識属性。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Test = (ExecutionTarget : String);
```



## <a name="named-items"></a>名前付き項目

### <a name="executiontarget--string"></a>ExecutionTarget: [文字列](xref:microsoft.quantum.lang-ref.string)

