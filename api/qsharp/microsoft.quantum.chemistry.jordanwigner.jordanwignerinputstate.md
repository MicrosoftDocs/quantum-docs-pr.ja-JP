---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713979"
---
# <a name="jordanwignerinputstate-user-defined-type"></a><span data-ttu-id="58a26-102">JordanWignerInputState ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="58a26-102">JordanWignerInputState user defined type</span></span>

<span data-ttu-id="58a26-103">名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="58a26-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="58a26-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58a26-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58a26-105">C# から Q # に渡されるデータの形式は、初期状態の準備を表すために、表示されるデータの意味はそれを受け取るアルゴリズムによって決まります。</span><span class="sxs-lookup"><span data-stu-id="58a26-105">Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

