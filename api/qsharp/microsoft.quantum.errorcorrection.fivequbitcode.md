---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: Fivvldb Bitcode 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712341"
---
# <a name="fivequbitcode-function"></a><span data-ttu-id="d4417-102">Fivvldb Bitcode 関数</span><span class="sxs-lookup"><span data-stu-id="d4417-102">FiveQubitCode function</span></span>

<span data-ttu-id="d4417-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="d4417-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="d4417-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d4417-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d4417-105">⟦5、1、3⟧のコードエンコーダーを表す QECC 値と、インプレースより隣人測定値を返します。</span><span class="sxs-lookup"><span data-stu-id="d4417-105">Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.</span></span>

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a><span data-ttu-id="d4417-106">出力: [Qecc](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span><span class="sxs-lookup"><span data-stu-id="d4417-106">Output : [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)</span></span>

<span data-ttu-id="d4417-107">型を指定して、クォンタムエラー修正コードの実装を返し `QECC` ます。</span><span class="sxs-lookup"><span data-stu-id="d4417-107">Returns an implementation of a quantum error correction code by specifying a `QECC` type.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4417-108">解説</span><span class="sxs-lookup"><span data-stu-id="d4417-108">Remarks</span></span>

<span data-ttu-id="d4417-109">このコードは、次の2つのホワイトペーパーで個別に検出されました。</span><span class="sxs-lookup"><span data-stu-id="d4417-109">This code was found independently in the following two papers:</span></span>

- <span data-ttu-id="d4417-110">C.</span><span class="sxs-lookup"><span data-stu-id="d4417-110">C.</span></span> <span data-ttu-id="d4417-111">H.</span><span class="sxs-lookup"><span data-stu-id="d4417-111">H.</span></span> <span data-ttu-id="d4417-112">Bennett、d. DiVincenzo、j.。</span><span class="sxs-lookup"><span data-stu-id="d4417-112">Bennett, D. DiVincenzo, J. A.</span></span> <span data-ttu-id="d4417-113">Smolin と W. K。</span><span class="sxs-lookup"><span data-stu-id="d4417-113">Smolin and W. K.</span></span> <span data-ttu-id="d4417-114">Wootters、"Mixed state 結び付き and クォンタム error 修正、" Phys, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 および</span><span class="sxs-lookup"><span data-stu-id="d4417-114">Wootters, "Mixed state entanglement and quantum error correction," Phys. Rev. A, 54 (1996) pp. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 and</span></span>
- <span data-ttu-id="d4417-115">R.</span><span class="sxs-lookup"><span data-stu-id="d4417-115">R.</span></span> <span data-ttu-id="d4417-116">Laflamme、C. Miquel、J. P。</span><span class="sxs-lookup"><span data-stu-id="d4417-116">Laflamme, C. Miquel, J. P.</span></span> <span data-ttu-id="d4417-117">ラパスと W. H.</span><span class="sxs-lookup"><span data-stu-id="d4417-117">Paz and W. H.</span></span> <span data-ttu-id="d4417-118">Zurek、"完全なクォンタムエラー修正コード" Phys. Lett.</span><span class="sxs-lookup"><span data-stu-id="d4417-118">Zurek, "Perfect quantum error correction code," Phys. Rev. Lett.</span></span> <span data-ttu-id="d4417-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span><span class="sxs-lookup"><span data-stu-id="d4417-119">77 (1996) pp. 198-201; https://arxiv.org/abs/quant-ph/9602019</span></span>