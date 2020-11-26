---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 3cdcd18f06bf43d109c9f5e69f319f9d33b96bfc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222747"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="6e2b4-102">LittleEndianAsBigEndian 関数</span><span class="sxs-lookup"><span data-stu-id="6e2b4-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="6e2b4-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6e2b4-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6e2b4-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e2b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e2b4-105">Qubit の `LittleEndian` 順序を逆にして、qubit レジスタを `BigEndian` qubit レジスタに変換します。</span><span class="sxs-lookup"><span data-stu-id="6e2b4-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="6e2b4-106">入力</span><span class="sxs-lookup"><span data-stu-id="6e2b4-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="6e2b4-107">入力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6e2b4-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6e2b4-108">形式での qubit レジスタ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="6e2b4-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="6e2b4-109">出力: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="6e2b4-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="6e2b4-110">形式での qubit レジスタ `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="6e2b4-110">Qubit register in `BigEndian` format.</span></span>