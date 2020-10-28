---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 8d4498647682026e9dec3fa96cfb69ba1e3214b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712504"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="15470-102">BitFlipCode 関数</span><span class="sxs-lookup"><span data-stu-id="15470-102">BitFlipCode function</span></span>

<span data-ttu-id="15470-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="15470-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="15470-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15470-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15470-105">⟦3、1、1⟧ビットフリップコードエンコーダー、および埋め込み先より隣人測定値を持つデコーダーを表す QECC 値を返します。</span><span class="sxs-lookup"><span data-stu-id="15470-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="15470-106">出力: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="15470-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="15470-107">型を指定して、クォンタムエラー修正コードの実装を返し `QECC` ます。</span><span class="sxs-lookup"><span data-stu-id="15470-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>