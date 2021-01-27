---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851782"
---
# <a name="hterm-user-defined-type"></a><span data-ttu-id="f3d2b-102">HTerm ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="f3d2b-102">HTerm user defined type</span></span>

<span data-ttu-id="f3d2b-103">名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f3d2b-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="f3d2b-104">パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f3d2b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f3d2b-105">Hamiltonian の用語を表すために、C# から Q # に渡されるデータの形式。</span><span class="sxs-lookup"><span data-stu-id="f3d2b-105">Format of data passed from C# to Q# to represent a term of the Hamiltonian.</span></span>
<span data-ttu-id="f3d2b-106">表されるデータの意味は、それを受け取るアルゴリズムによって決まります。</span><span class="sxs-lookup"><span data-stu-id="f3d2b-106">The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype HTerm = (Int[], Double[]);
```

