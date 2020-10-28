---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714870"
---
# <a name="hterm-user-defined-type"></a>HTerm ユーザー定義型

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)

パック [](https://nuget.org/packages/)


Hamiltonian の用語を表すために、C# から Q # に渡されるデータの形式。
表されるデータの意味は、それを受け取るアルゴリズムによって決まります。

```qsharp

newtype HTerm = (Int[], Double[]);
```

