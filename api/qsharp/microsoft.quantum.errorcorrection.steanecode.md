---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712182"
---
# <a name="steanecode-function"></a><span data-ttu-id="167b8-102">SteaneCode 関数</span><span class="sxs-lookup"><span data-stu-id="167b8-102">SteaneCode function</span></span>

<span data-ttu-id="167b8-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="167b8-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="167b8-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="167b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="167b8-105">⟦7、1、3⟧ Steane code encoder およびデコーダーを、インプレースより隣人測定値と共に表す CSS 値を返します。</span><span class="sxs-lookup"><span data-stu-id="167b8-105">Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a><span data-ttu-id="167b8-106">出力: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="167b8-106">Output : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="167b8-107">⟦7、1、3⟧ Steane code のエンコーディングとエラー修正を実行するために、関連するすべてのデータを収集する CSS 型のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="167b8-107">An object of CSS type which collects all relevant data to perform encoding and error correction for the ⟦7, 1, 3⟧ Steane code.</span></span>

## <a name="remarks"></a><span data-ttu-id="167b8-108">解説</span><span class="sxs-lookup"><span data-stu-id="167b8-108">Remarks</span></span>

<span data-ttu-id="167b8-109">このコードは、次のホワイトペーパーに記載されています。</span><span class="sxs-lookup"><span data-stu-id="167b8-109">This code was found in the following paper:</span></span>

- <span data-ttu-id="167b8-110">A.</span><span class="sxs-lookup"><span data-stu-id="167b8-110">A.</span></span> <span data-ttu-id="167b8-111">Steane、「複数のパーティクル干渉と量子エラー修正」、Proc。</span><span class="sxs-lookup"><span data-stu-id="167b8-111">Steane, "Multiple Particle Interference and Quantum Error Correction", Proc.</span></span> <span data-ttu-id="167b8-112">Roy.</span><span class="sxs-lookup"><span data-stu-id="167b8-112">Roy.</span></span> <span data-ttu-id="167b8-113">Lond。</span><span class="sxs-lookup"><span data-stu-id="167b8-113">Soc. Lond.</span></span> <span data-ttu-id="167b8-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span><span class="sxs-lookup"><span data-stu-id="167b8-114">A452 (1996) pp. 2551; https://arxiv.org/abs/quant-ph/9601029.</span></span>