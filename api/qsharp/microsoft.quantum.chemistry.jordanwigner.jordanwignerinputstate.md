---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 18adf28b4e99c825f14e9271791ded069e687901
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837689"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState ユーザー定義型

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


C# から Q # に渡されるデータの形式は、初期状態の準備を表すために、表示されるデータの意味はそれを受け取るアルゴリズムによって決まります。

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

