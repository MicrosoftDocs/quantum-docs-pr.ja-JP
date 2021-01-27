---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 81abe75e2a315fe9a994147242f3c8c9bde586ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824717"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="de287-102">SteaneCodeEncoderImpl 操作</span><span class="sxs-lookup"><span data-stu-id="de287-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="de287-103">名前空間: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="de287-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="de287-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de287-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de287-105">Steane コードエンコーダーとデコーダーの両方を実装するために使用されるプライベート操作。</span><span class="sxs-lookup"><span data-stu-id="de287-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="de287-106">入力</span><span class="sxs-lookup"><span data-stu-id="de287-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="de287-107">データ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="de287-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="de287-108">入力 qubit である1つの qubit を保持する配列。</span><span class="sxs-lookup"><span data-stu-id="de287-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="de287-109">スクラッチ: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="de287-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="de287-110">冗長性を追加する6つの qubits を保持する配列。</span><span class="sxs-lookup"><span data-stu-id="de287-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="de287-111">出力: [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="de287-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

