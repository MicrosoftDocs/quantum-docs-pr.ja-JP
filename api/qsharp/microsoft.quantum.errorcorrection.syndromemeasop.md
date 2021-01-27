---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: Syn% Memeasop ユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850052"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="45634-102">Syn% Memeasop ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="45634-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="45634-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="45634-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="45634-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45634-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45634-105">エラー修正コードブロックのより隣人を測定するために使用される操作を表します。</span><span class="sxs-lookup"><span data-stu-id="45634-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="45634-106">例</span><span class="sxs-lookup"><span data-stu-id="45634-106">Example</span></span>

<span data-ttu-id="45634-107">ビットフリップコード $S = \ langle ZZI、IZZ \rangle $ のメジャー syndromes を、非フォールトトレラントな方法でスクラッチ qubits を使用して測定します。</span><span class="sxs-lookup"><span data-stu-id="45634-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="45634-108">解説</span><span class="sxs-lookup"><span data-stu-id="45634-108">Remarks</span></span>

<span data-ttu-id="45634-109">このシグネチャは、 `(LogicalRegister => Syndrome)` の qubits と、補助 qubits `LogicalRegister` の後に補助 qubits の測定値を指定して、 `Syndrome` これらの測定値を表す値を抽出する操作を表し `Result[]` ます。</span><span class="sxs-lookup"><span data-stu-id="45634-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="45634-110">参照</span><span class="sxs-lookup"><span data-stu-id="45634-110">See Also</span></span>

- [<span data-ttu-id="45634-111">Microsoft... ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="45634-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="45634-112">より隣人を修正します。</span><span class="sxs-lookup"><span data-stu-id="45634-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)