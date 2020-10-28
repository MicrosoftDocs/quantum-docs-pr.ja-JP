---
uid: Microsoft.Quantum.Diagnostics.EnableTestingViaName
title: EnableTestingViaName ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EnableTestingViaName
qsharp.summary: Compiler-recognized attribute via which an alternative name can be defined that may be used when loading a type or callable for testing purposes.
ms.openlocfilehash: ee4f32a5af4243ad85994c2edd006737a5131931
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712845"
---
# <a name="enabletestingvianame-user-defined-type"></a>EnableTestingViaName ユーザー定義型

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

パック [](https://nuget.org/packages/)


型を読み込むとき、またはテスト目的で呼び出すことができる代替名を定義できる、コンパイラで認識される属性。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype EnableTestingViaName = (String);
```

