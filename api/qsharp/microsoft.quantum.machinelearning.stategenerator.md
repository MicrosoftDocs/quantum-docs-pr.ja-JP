---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator ユーザー定義型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211561"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="46c92-102">StateGenerator ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="46c92-102">StateGenerator user defined type</span></span>

<span data-ttu-id="46c92-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="46c92-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="46c92-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="46c92-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="46c92-105">指定された入力をシーケンシャルな分類子に準備する操作を記述します。</span><span class="sxs-lookup"><span data-stu-id="46c92-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="46c92-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="46c92-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="46c92-107">NQubits: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46c92-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46c92-108">エンコードされた入力が定義されている qubits の数。</span><span class="sxs-lookup"><span data-stu-id="46c92-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="46c92-109">準備: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  が形容詞 + Ctl である</span><span class="sxs-lookup"><span data-stu-id="46c92-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="46c92-110">Qubits のリトルエンディアンレジスタでエンコードされた入力を準備する操作 `NQubits` 。</span><span class="sxs-lookup"><span data-stu-id="46c92-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>