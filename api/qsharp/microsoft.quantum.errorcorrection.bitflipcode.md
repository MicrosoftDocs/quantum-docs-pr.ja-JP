---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipCode
title: BitFlipCode 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipCode
qsharp.summary: Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 0a5a028f85b80575b754b93a797a1460d21bb552
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853188"
---
# <a name="bitflipcode-function"></a><span data-ttu-id="51683-102">BitFlipCode 関数</span><span class="sxs-lookup"><span data-stu-id="51683-102">BitFlipCode function</span></span>

<span data-ttu-id="51683-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="51683-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="51683-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51683-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51683-105">⟦3、1、1⟧ビットフリップコードエンコーダー、および埋め込み先より隣人測定値を持つデコーダーを表す QECC 値を返します。</span><span class="sxs-lookup"><span data-stu-id="51683-105">Returns a QECC value representing the ⟦3, 1, 1⟧ bit flip code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function BitFlipCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="51683-106">出力: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="51683-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="51683-107">型を指定して、クォンタムエラー修正コードの実装を返し `QECC` ます。</span><span class="sxs-lookup"><span data-stu-id="51683-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>