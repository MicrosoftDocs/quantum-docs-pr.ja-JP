---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722397"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="63f0a-102">StateGenerator ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="63f0a-102">StateGenerator user defined type</span></span>

<span data-ttu-id="63f0a-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="63f0a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="63f0a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63f0a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63f0a-105">指定された入力をシーケンシャルな分類子に準備する操作を記述します。</span><span class="sxs-lookup"><span data-stu-id="63f0a-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="63f0a-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="63f0a-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="63f0a-107">NQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="63f0a-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="63f0a-108">エンコードされた入力が定義されている qubits の数。</span><span class="sxs-lookup"><span data-stu-id="63f0a-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="63f0a-109">準備: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容詞 + Ctl</span><span class="sxs-lookup"><span data-stu-id="63f0a-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="63f0a-110">Qubits のリトルエンディアンレジスタでエンコードされた入力を準備する操作 `NQubits` 。</span><span class="sxs-lookup"><span data-stu-id="63f0a-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>