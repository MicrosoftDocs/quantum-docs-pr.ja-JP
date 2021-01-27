---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843365"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="41f0e-102">BigEndianAsLittleEndian 関数</span><span class="sxs-lookup"><span data-stu-id="41f0e-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="41f0e-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="41f0e-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="41f0e-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41f0e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41f0e-105">Qubit の `BigEndian` 順序を逆にして、qubit レジスタを `LittleEndian` qubit レジスタに変換します。</span><span class="sxs-lookup"><span data-stu-id="41f0e-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="41f0e-106">入力</span><span class="sxs-lookup"><span data-stu-id="41f0e-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="41f0e-107">入力: [Bigendian ディアン](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="41f0e-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="41f0e-108">形式での qubit レジスタ `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="41f0e-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="41f0e-109">出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="41f0e-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="41f0e-110">形式での qubit レジスタ `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="41f0e-110">Qubit register in `LittleEndian` format.</span></span>