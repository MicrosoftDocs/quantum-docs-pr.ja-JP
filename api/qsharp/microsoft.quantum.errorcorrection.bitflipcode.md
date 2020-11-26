---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 2d0b50bd2467fc01caacbbcb22f98c59a2d13922
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201225"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="696d2-102">BitFlipCode 関数</span><span class="sxs-lookup"><span data-stu-id="696d2-102">BitFlipCode function</span></span>

<span data-ttu-id="696d2-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="696d2-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="696d2-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="696d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="696d2-105">⟦3、1、1⟧ビットフリップコードエンコーダー、および埋め込み先より隣人測定値を持つデコーダーを表す QECC 値を返します。</span><span class="sxs-lookup"><span data-stu-id="696d2-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="696d2-106">出力: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="696d2-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="696d2-107">型を指定して、クォンタムエラー修正コードの実装を返し `QECC` ます。</span><span class="sxs-lookup"><span data-stu-id="696d2-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>