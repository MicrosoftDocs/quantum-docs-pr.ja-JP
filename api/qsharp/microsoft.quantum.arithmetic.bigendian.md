---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian ディアンユーザー定義型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843389"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="589d9-102">BigEndian ディアンユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="589d9-102">BigEndian user defined type</span></span>

<span data-ttu-id="589d9-103">名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="589d9-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="589d9-104">パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="589d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="589d9-105">ビッグエンディアンの順序で符号なし整数をエンコードするレジスタ。</span><span class="sxs-lookup"><span data-stu-id="589d9-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="589d9-106">Qubit with index は、 `0` 符号なし整数の最上位ビットをエンコードします。</span><span class="sxs-lookup"><span data-stu-id="589d9-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="589d9-107">解説</span><span class="sxs-lookup"><span data-stu-id="589d9-107">Remarks</span></span>

<span data-ttu-id="589d9-108">`BigEndian` `BE` ドキュメントでは、のように省略します。</span><span class="sxs-lookup"><span data-stu-id="589d9-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>